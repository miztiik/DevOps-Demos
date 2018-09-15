# Configure Jenkins Slaves on AWS EC2
Jenkins is a self-contained Java-based program, ready to run out-of-the-box, with packages for Windows, Mac OS X and other Unix-like operating systems. As an extensible automation server, Jenkins can be used as a simple CI server or turned into the continuous delivery hub for any project.

### Follow this article in **[Youtube](https://youtu.be/hwrYURP4O2k)**
![Jenkins Master and Slave Configuration](https://raw.githubusercontent.com/miztiik/DevOps-Demos/master/setup-jenkins-slave/images/Jenkins%20Master%20and%20Slave%20Configuration.png)

### Prerequisites
1. Jenkins Master Running [Get help here](https://youtu.be/-0dkiteJEuE)
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
# Create SSH Keys
sudo su - jenkins-slave-01
ssh-keygen -t rsa -N "" -f /home/jenkins-slave-01/.ssh/id_rsa
# The private and public keys will be created at these locations `/home/jenkins-slave-01/.ssh/id_rsa` and `/home/jenkins-slave-01/.ssh/id_rsa.pub`
cd .ssh
cat id_rsa.pub > authorized_keys
chmod 700 authorized_keys
```

### Configuration on Master
Copy the slave node's public key[`id_rsa.pub`] to Master Node's `known_hosts` file
```sh
mkdir -p /var/lib/jenkins/.ssh
cd /var/lib/jenkins/.ssh
ssh-keyscan -H SLAVE-NODE-IP-OR-HOSTNAME >>/var/lib/jenkins/.ssh/known_hosts
# ssh-keyscan -H 172.31.38.42 >>/var/lib/jenkins/.ssh/known_hosts
chown jenkins:jenkins known_hosts
chmod 700 known_hosts
```

#### Configure the Slave using `Manage Jenkins`
Configure the node as shown here
`Manage Jenkins` > `Manage Nodes` > `New Node`
![Jenkins Master and Slave Configuration](https://raw.githubusercontent.com/miztiik/DevOps-Demos/master/setup-jenkins-slave/images/Slave-Node-Configuration-01.png)
### Test Jenkins Jobs
1. Create “new item”
1. Enter an item name – `My-First-Project`
   - Chose `Freestyle` project
1. Under `General` Section
   - Choose `Restrict where this project can be run`
     - Update your _jenkins slave label_ `Java` 
1. Under Build section
   Execute shell
   ```sh
   #!/bin/bash
   echo "_______________________________"
   echo "|                             |"
   echo "|   Welcome to Valaxy Demo    |"
   echo "|           _nnnn_            |"
   echo "|          dGGGGMMb           |"
   echo "|         @p~qp~~qMb          |"
   echo "|         M|@||@) M|          |"
   echo "|         @,----.JM|          |"
   echo "|        JS^\__/  qKL         |"
   echo "|       dZP        qKRb       |"
   echo "|      dZP          qKKb      |"
   echo "|     fZP            SMMb     |"
   echo "|     HZM            MMMM     |"
   echo "|     FqM            MMMM     |"
   echo "|   __| '.        |\dS'qML    |"
   echo "|   |    '.       | ' \Zq     |"
   echo "|  _)      \.___.,|     .'    |"
   echo "|  \____   )MMMMMP|   .'      |"
   echo "|       '-'       '--' hjm    |"
   echo "_______________________________"
   ```
1. Save your job 
1. Build job
1. Check "console output"

### Other Videos
 - [x] [Install and Configure Jenkins in AWS EC2](https://youtu.be/-0dkiteJEuE)
 - [x] [Configure Users & Groups in Jenkins](https://youtu.be/jZOqcB32dYM)
 - [x] [Secure your Jenkins Server](https://youtu.be/19FmJumnkDc)
 - [x] [Jenkins Plugin Installation](https://youtu.be/p_PqPBbjaZ4)
 - [x] [Jenkins Master-Slave Configuration](https://youtu.be/hwrYURP4O2k)

