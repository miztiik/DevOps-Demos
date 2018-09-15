# Jenkins Plugins You Can’t Live Without

Jenkins advantage is its extensibility with plugines. Its plugins number upwards of over 1500. These plugins support the automation of various development tasks and were primarily developed to satisfy the need for CI and CD. The development tasks that all these plugins support include but are not limited to running tests, static code analysis, building projects, and deployment, among many, many other capabilities.

### Follow this article in **[Youtube](https://youtu.be/p_PqPBbjaZ4)**

  ![Jenkins Plugins](https://raw.githubusercontent.com/miztiik/DevOps-Demos/master/setup-jenkins-plugins/images/jenkins-plugins.png)

**Generic Plugins**
-------------------

1. ### **[Dashboard View Plugin](https://plugins.jenkins.io/dashboard-view)**

   The ‘Dashboard view plugin’ provides a new Jenkins dashboard that allows you to monitor the status of all the tasks. Ideally, this also has time tracking capabilities for the duration taken by each job and also shows the entire time execution. These are fundamentals that help you manage Jenkins.

1. ### **[View Job Filters Plugin](https://plugins.jenkins.io/view-job-filters)**

   The ‘View Job Filters plugin’ is an out-of-the-box method to build different views for all your Jenkins jobs. Whether it’s build status or trends and triggers, with the ‘View Job Filters plugin,’ you will find all these filtering options in addition to many others.

1. ### **[Folders Plugin](https://plugins.jenkins.io/cloudbees-folder)**

   The ‘Folders plugin’ is a great method for grouping your Jenkins tasks. This fact this plugin has been downloaded over 120,000 times speaks volumes about its usefulness. Furthermore, organize your CI server can be arranged perfectly with the nestable folders available in this plugin.

1. ### **[Green balls](https://wiki.jenkins.io/display/JENKINS/Green+Balls)**
   Jenkins uses blue balls to mark successful builds. However, people prefer green balls for this plugin, which changes the ball color, to be one of the most popular plugins out there.

1. ### **[Restarting safely](https://wiki.jenkins.io/display/JENKINS/SafeRestart+Plugin)**
   Jenkins needs to restart every now and then, oftentimes when installing or updating plugins. This plugin allows you to put new jobs on hold and reboot the server once your running jobs are finished. The reboot can be scheduled from both the Jenkins configuration page and the main dashboard.

**Monitoring**
--------------

1. ### **[Monitoring Plugin](https://plugins.jenkins.io/monitoring)**

   The ‘Monitoring Plugin’ uses JavaMelody to keep track of Jenkins. This plugin allocates charts for CPU, HTTP response time, memory, and much more. It further provides information on HTTP periods, logs accounts, head dumps, and other data. With this plugin, you can check the status/progress of jobs under consideration and view statistics that will help you proactively manage Jenkins via the interface.

1. ### **[Disk-Usage Plugin](https://plugins.jenkins.io/disk-usage)**

   The ‘Disk-Usage Plugin’ provides for the calculation of disk usage in periods of 60 minutes. You can see a list of projects with space occupied on the disk and at the same time, schedule the calculation of disk usage.

**Performance Enhancers**
-------------------------

1. ### **[Performance Plugin](https://plugins.jenkins.io/performance)**

   Use this plugin in both Jenkins pipelines and GUI jobs. The tool provides report capturing capabilities through a whole range of favorite testing tools like JMeter, JUnit or Taurus. You can watch your project’s performance via trend reports and graphs, and set your build status to either right, unstable or failed.

1. ### **[Performance Publisher Plugin](https://plugins.jenkins.io/perfpublisher)**

   An outstanding feature of Performance Published plugin is that it is designed to work with every testing tool by generating trend and global reports for test result analysis. It computes stats, underlines regressions and modifications, and creates any number of trend graphs, but you need to generate the XML files with your own testing tool.

**Scaling Jenkins Setup**
-------------------------

Setting up Jenkins is straightforward for immediate CI functionality and to run automated tests on its own. But as you run more jobs on your Jenkins server, it will quickly become apparent that one instance is not enough even assuming they might run in parallel to each other. For these occurrences, Jenkins provides the “master/slaves” mode.

There are numerous ways to configure the Jenkins’ master and slaves. The best recommendation is to allocate new slaves’ instances only when they are necessary and to exclude them when it’s not convenient having them.

The next two plugins are great for handling Jenkins server scalability.

1. ### **[Kubernetes Plugin](https://plugins.jenkins.io/kubernetes)**

   The ‘Kubernetes plugin’ works, surprisingly, with Kubernetes. So, if you plan to use Kubernetes for your infrastructure, this plugin is the way forward for setting up and tearing down Jenkins’ agents. While moving to Kubernetes is not the easiest process, the results are worth it.

1. ### **[Self-Organizing Swarm Modules Plugin](https://plugins.jenkins.io/swarm)**

   The decision for using this plugin or the one above lies simply with, are you using Docker Swarm or Kubernetes? This plugin offers just another method to spin up and pull down Jenkins slaves.

1. ### **[Amazon ECS Container Service](https://plugins.jenkins.io/amazon-ecs)**

   Use the ‘Amazon ECS Container Service’ plugin to manage Jenkins cloud slaves and deploy Docker-based applications on a cluster.

1. ### **[Azure Container Service](https://plugins.jenkins.io/azure-acs)**

   Your new AKS (rebranding by Azure) cluster orchestration plugin to run a container as an agent through Jenkins.

**Tests Analysis Plugins**
--------------------------

Jenkins is the ultimate companion for performing your tests as part of CI. However, Jenkins doesn’t provide any way of studying test results after execution, which is an essential aspect of testing.

1. ### **[Test Results Analyzer](https://plugins.jenkins.io/test-results-analyzer)**

   The Test Results plugin is preferable as it offers greater visibility on tests results and execution trend patterns as well as allowing easy installation. The ‘Tests Result Analyzer’ gives many different graphical representations and a quite detailed matrix table that will direct you to the outcome of each test for all the builds you’ve had. A reliable method of identifying unstable tests.

1. ### **[Bootstrapped-multi-test-result-report plugin](https://plugins.jenkins.io/bootstraped-multi-test-results-report)**

   The ‘bootstrapped-multi-test-result-report plugin’ enables you to build HTML reports based on tests’ results. A major advantage of this plugin is its ability to make interactive reports that enable you to see the overall picture of all outcomes as well as detailed results of steps statuses.

**Pipeline / Flow**
-------------------

1. ### **[Job DSL plugin](https://plugins.jenkins.io/job-dsl)**

   This plugin allows users to describe tasks, handle scripts, and update Jenkins jobs. With Job DSL you can define jobs by bare minimum programmatic form with the help from templates. You also gain various jobs views such as ‘BuildMonitorView’, ‘BuildPipelineView’, ‘CategorizedJobsView’, and many others. These views provide high visibility of the status of selected Jenkins jobs.

1. ### **[Build Pipeline Plugin](https://plugins.jenkins.io/build-pipeline-plugin)**

   This plugin provides a view of the jobs that make up your build pipeline, upstream and also downstream. Furthermore, it allows you to define manual triggers for specific tasks that may need intervention before their execution. Build Pipeline Plugin is a game changer for Jenkins’ users because it makes pipelines scriptable as well as providing an incredibly powerful avenue in which to develop complex DevOps pipelines.

1. ### **[Maven Plugin](https://github.com/jenkinsci/maven-plugin)**
   Maven is much loved for the providing an easy to use standard project build layout. This helps developers save time at the start of projects by allowing them to jump straight in at the deep end and not to have to worry about this aspect of familiarizing themselves with the project.

   This plugin lets Jenkins monitor Maven builds to allow for automatic archiving of reports and help with parallel or incremental module builds etc. It is easy to set up and doesn’t require much in the way of Jenkins configuration.

1. ### **[Multijob Plugin](https://plugins.jenkins.io/jenkins-multijob-plugin)**

   This plugin allows you to express complex tasks and then organize them according to their structures in the Jenkins. You can use this plugin whenever you need to clean up the mess for chain definitions with upstream or downstream jobs. You may also use it when you need to create a hierarchy of tasks to be executed sequentially.

   Upon its installation, you can create ‘Multijob’ projects, and also define phases that can hold more than one job in addition to executing jobs in parallel to each other.

1. ### **[Pipeline Plugin](https://plugins.jenkins.io/workflow-aggregator)**

   'Pipeline' attempts to automate your continuous delivery pipeline and performs other complex tasks in Jenkins using traditional plugins and freestyle projects.

1. ### **[JIRA Plugin for Jenkins](https://github.com/jenkinsci/jira-plugin)**
   Basically this plugin integrates JIRA to Jenkins. We find it very useful because we use JIRA all the time and we absolutely need it to work through a project in an organized way between the team.

  It’s practical because you can display Jenkins builds inside JIRA. It will help you in maintaining a proper, organized way of working on a lengthy project and you will minimize the mistakes that occur without JIRA. 

**Source Control Management (SCM)**
-----------------------------------

SCM allows for the referencing of multiple repositories in a Jenkins job.

1. ### **[SCM Sync Configuration Plugin](https://plugins.jenkins.io/scm-sync-configuration)**

   This plugin syncs configuration files stored in the SCM hub and keeps track of any changes. It makes it possible for you to revert whenever you make an undesirable move. It also offers the option of using the repository as a reference to return to earlier positions manually.

1. ### **[Git Plugin](https://plugins.jenkins.io/git)**

   Provides access to GitHub as an SCM which acts as a repository browser for many other providers.

1. ### **[GitHub Integration Plugin](https://plugins.jenkins.io/github-pullrequest)**

   This is the most fundamental plugin needed for integrating Jenkins with GitHub projects.With this plugin, you can schedule your build, pull code and data files from GitHub repositories to Jenkins, and automatically trigger each build as needed.

**Look & Feel**
-----------------------------------

1. ### **[Blue Ocean Plugin](https://plugins.jenkins.io/blueocean)**
   Jenkins didn’t have any major UI/UX upgrades until last year, when they introduced the Blue Ocean plugin, which significantly improves Jenkins visualization and clarity. Therefore, if you use an older version of Jenkins, you can install the ‘Blue Ocean plugin’ as a separate plugin, while in the latest versions you will get it out of the box.

1. ### **[Simple Theme Plugin](https://plugins.jenkins.io/simple-theme-plugin)**
    The _Simple Theme plugin_ allows adding a custom CSS to your Jenkins server. By having this ability in place, you can find a couple of custom Jenkins themes as well as implement your own (for example, with a company logo).


## Conclusion
There are hundreds of plugins that might be useful for your current project. You may think that your current CI service is adequate and does not need additional plugins, sometimes it is worthwhile to go over all plugins availableat [Jenkins’](https://jenkins.io/). You may find some more plugins thta are necessary for your project.

### Other References
 - [x] [Install and Configure Jenkins in AWS EC2](https://youtu.be/-0dkiteJEuE)
 - [x] [Configure Users & Groups in Jenkins](https://youtu.be/jZOqcB32dYM)
 - [x] [Secure your Jenkins Server](https://youtu.be/19FmJumnkDc)
 - [x] [Jenkins Plugin Installation](https://youtu.be/p_PqPBbjaZ4)
 - [x] [Jenkins Master-Slave Configuration](https://youtu.be/hwrYURP4O2k)

##### References
1. [Jenkins plugins Gist](https://gist.github.com/jet47/f47a7e542295c238fff4)