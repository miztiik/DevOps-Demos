# Install Jenkins Slaves on AWS EC2
Jenkins is a self-contained Java-based program, ready to run out-of-the-box, with packages for Windows, Mac OS X and other Unix-like operating systems. As an extensible automation server, Jenkins can be used as a simple CI server or turned into the continuous delivery hub for any project.

### Prerequisites
1. Jenkins Master Running [Get help here](https://www.youtube.com/watch?v=KDtS6BzJo3A)
1. EC2 RHEL 7.x Instance - _for Slave Node_ [Get help here](https://www.youtube.com/watch?v=KDtS6BzJo3A)
   - With Internet Access
   - Security Group with Port `8080` open for internet
   - Java v1.8.x 

## Install Java
We will be using open java for our demo, Get latest version from http://openjdk.java.net/install/. Also configure the default `JAVA_HOME` path
```sh
yum install java-1.8*
#yum -y install java-1.8.0-openjdk
```
## Setup Jenkins Slave
```sh
# Create user and add the user to wheel group
useradd jenkins-slave-01
usermod -aG wheel jenkins-slave-01
# Create SSH Keys
sudo su - jenkins-slave-01
ssh-keygen
# The private and public keys should be created on `/home/jenkins-slave-01/.ssh/id_rsa` and `/home/jenkins-slave-01/.ssh/id_rsa.pub`
cd .ssh
cat id_rsa.pub > authorized_keys
chmod 700 authorized_keys

```

### Configuration on Master
```sh
sudo su - jenkins
mkdir -p /var/lib/jenkins/.ssh
cd /var/lib/jenkins/.ssh
touch known_hosts
chmod 700 known_hosts
# Copy the jenkins slave public key to the known_hosts file
echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC37ytaMlEe1z6hIPAW6xcTZ3JMYzMq1wDDNCp8l+zYVeqnBypwkCxxbp0sAVP6R974259BQskSpJd0H88yDjSdDJfmvLwjxHLVLZ1n0xF0/es11v9gfLi
uwkD6Y9FU3dEeId3kgjsb+K21Phjyxrn2khWuVULgQS2VYU+0HECaLmNDvfz02bVe8+axXadc37Y/nwoVHHGDvEq0Sx2imGw46oo93RqpFjTsUasbJ0lwVaNl+dLqRkejRipEiVsY/yQCy6xLbwYnRDmdHE
mb9MeUro7ZV9c+AO90cxj3PK1mVWaGplYEvoTvJsb7a7V50heBhBvdS1RrquO1xDJhSMBz jenkins-slave-01@ip-172-31-3-74.eu-central-1.compute.internal" > known_hosts

```

#### Accessing Jenkins
By default jenkins runs at port `8080`, You can access jenkins at
```sh
http://YOUR-SERVER-PUBLIC-IP:8080
```
#### Configure Jenkins
- The default Username is `admin`
- Grab the default password 
  - Password Location:`/var/lib/jenkins/secrets/initialAdminPassword`
- `Skip` Plugin Installation; _We can do it later_
- Change admin password
  - `Admin` > `Configure` > `Password`
- Configure `java` path
  - `Manage Jenkins` > `Global Tool Configuration` > `JDK`  
- Create another admin user id

### Test Jenkins Jobs
1. Create “new item”
1. Enter an item name – `My-First-Project`
   - Chose `Freestyle` project
1. Under Build section
	Execute shell : echo "Welcome to Jenkins Demo"
1. Save your job 
1. Build job
1. Check "console output"

### Next Step
- [ ] Setup Jenkins to run inside Tomcat Server
