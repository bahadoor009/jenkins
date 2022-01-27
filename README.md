# Learning Objectives

- What is Jenkins?<br>
- What is CI/CD  ( Continuous Integration Continuous Delivery )<br>
- Stages in CI/CD<br>
- Creating CI/CD Infrastructure in AWS<br>
- Installing Jenkins in EC2 Machine<br>
- How to run a sample job in Jenkins?<br>
- Install Tomcat on AWS Environment<br>
- Performing continuous download<br>
- Performing continuous build<br>
- How to install Plug-in<br>
- Performing continuous Deployment<br>
- Importance of Context Path<br>
- Performing continuous download<br>
- Performing continuous build<br>
- How to install Plug-in<br>
- Performing continuous Deployment<br>
- Importance of Context Path<br>
- How to call one job from another job<br>
- Copy Artifact Plugin<br>
- Performing all the five Stages in CI-CD<br>
- How to create new user in Jenkins<br>
- Types of Roles – Global Role Item / Project Role<br>
- Role based authorization Strategy Plugin<br>
- Need for Master Slave configuration<br>
- Establish password-less connection between Master and Slave Machine<br>
- Creating new node in Jenkins<br>
- Run the job in node machine<br>
- What is Pipeline Job?<br>
- Advantages of Pipeline Job<br>
- Build pipeline plug-in<br>
- Generating the Groovy code<br>
- Perform CI/CD Stages using groovy code<br>
- What is multibranch Pipeline?<br>
- Triggering the pipeline job automatically<br>
- Email Integration in Jenkins<br>
- Trigger the job periodically<br>
- Wait for the approval from delivery head, before moving it to production<br>


# What is Jenkins?

Jenkins is a self contained, open source automation server which can be used to automate all  tasks related to building , testing and delivery activities. Jenkins can be installed even on standalone be any machine with a java runtime envirowment (JRE) Installed.

Jenkins is a tool for Implmenting CI-CD (Continuous Integration - Continuous Delivery)

Stages in CI-CD: <br>

Stage 1 : Continuous Download<br>
Stage 2: Continuous Build<br>
Stage 3: Continuous Deployment<br>
Stage 4: Continuous Testing<br>
Stage 5: Continuous Delivery<br>


1-4----Continuous Integration<br>
  5----Continuous Delivery<br>
  
-------------------------------------------------------------------------


# Install Jenkins in AWS Instance

To install Jenkins the first thing we need java file so first we need to install java like we have done in the local instance.<br>

We need to download Java 1.8 or more.<br>

1) Update the apt repository<br>
sudo apt update<br>

2) sudo apt install openjdk-8-jdk -y<br>

3) Check the Java Version<br>
java -version<br>

4) Install Maven & Git<br>
sudo apt-get install -y git  maven<br>

5) Check the Verion of Git & Maven<br>
For Git : git --version<br>
For Maven : mvn --version<br>

6) Download & install Jenkins<br>
Open Jenkins website (https://jenkins.io/download/)<br>

Go to Long Term Support<br>

Select Generic Java Package (.war)<br>

We are selecting generic java package file because jenkins will install on those machine where java is already install. If we have java install in windows machine jenkins will work. Only pre requirement is java needs to be install.

For Windows we just need to click on the file and it will download automatically.

For Linux machine enter command wget and paste the url to download the file.<br>

To get the URL right click on generic java package and click on copy link address.<br>

(wget http://mirrors.jenkins.io/war-stable/latest/jenkins.war)<br>

wget  https://get.jenkins.io/war-stable/2.277.2/jenkins.war<br>

11) Start the Jenkins.war file<br>

java -jar jenkins.war<br>

12) Access Jenkins Home Page<br>

Select DEV Instance & Press Connect.<br>

Copy the Domain Name On 4th point.<br>

Paste the Domain name in the browser and in the end enter :8080 with the default port number.<br>

We can access the jenkins with dev server Public IP.<br>

Copy the public ip of the dev server and paste the ip address in the browser and in the end enter :8080 with the default port number.<br>


13) Unclock Jenkins<br>

When we are installing jenkins it will automatically give you the password in the github terminal.<br>

Copy the password and paste the browser.<br>

You will get the password on the step 11<br>

14) Press Install Suggested Plugins<br>

15) Create First admin user<br>

The first user which we create here is the admin user of the jenkins.<br>

Click on save and continue.<br>

Click on save and finish<br>

# Create Sample Job


Build tab<br>
Click on execute Shell<br>
In Command Box Enter echo " Hello Jenkins"<br>
Click on Console Output<br>

-------------------------------------------------------------------------------------








