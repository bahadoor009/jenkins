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











--------------------------------------------------------------------------------

Install TOMCAT In QA & Production Server<br>

1) Select QA Server and connect<br>

2) Copy the SSH Command<br>

3) Open GIT Bash & paste the SSH Command<br>

Press Yes<br>

4) Update the apt repository <br>
sudo apt-get update<br>

5) Install tomcat8<br>
sudo apt-get install -y tomcat8<br>

After this we need to install one more package<br>
sudo apt-get install -y tomcat8-admin<br>

6) Check the tomcat is intall or not<br>

Copy the public IP of the QA Server then paste in the browser and in the end enter :8080 <br>

qa_server_public_ip:8080<br>

Setting the path of tomcat in jenkins<br>

7) enter linux command in QA Server  -   cd /etc/tomcat8/<br>

8) enter linux command in QA Server  -   ls<br>

9) You will find the file tomcat-users.xml<br>

10) Open the file -- sudo vim tomcat-users.xml<br>

11) In the end we need to add one statement <br>
<user username="training" password="bahadoor" roles="manager-script,manager-status,manager-gui"/><br>

save and quit <br>

press esc <br>

type :wq <br>

press enter<br>

12) When ever we do any changes done in any service we need to restart the service<br>
sudo service tomcat8 restart<br>

13) After this the same above 12 steps we need to do in the prod server also.<br>

Prod Instance<br>
<user username="learning" password="bahadoor" roles="manager-script,manager-status,manager-gui"/><br>

--------------------------------------------------------------------------------------------


First Start All the AWS Machines.<br>

Connect Dev Server<br>

Start the Jenkins <br>

java -jar jenkins.war <br>

<b>Stage 1 : Continuous Download START CI-CD</b><br>

1) Create New item as free style project<br>

2) Click on source code managment <br>

3) Select GIT<br>

4) Enter the URL of github reposiditory<br>
https://github.com/sunildevops77/maven.git<br>

5) Click on apply and save<br>

6) Run the Job<br>

7) Check the console output.<br>

8) Connect to the dev server<br>

9) Go to the location where code is downloaded<br>
sudo su -<br>

cd path of the folder<br>

ls<br>

<b>Stage 2 : Continuous Build</b><br>

Convert the java files in to artifact ( .war file)

10) Click on configure of the same job<br>

11) Go to Build Section<br>

12) Click on add build step<br>

13) Click on Invoke top level maven targets<br>

14) Enter the goal as  package<br>

15) click on apply and save<br>

16) Run the Job<br>

17) Click on number & click on console output<br>

18) Copy the path of the war file and check the file in the linux machine<br>
sudo su -<br>

cd path<br>

ls<br>

<b>Stage 3 :Continuous Deployment</b><br> 

Now we need to deploy the war file into the QA Server.<br>

19) For this we need to install "deploy to container" plugin.<br>
 
Go to Dasboard<br>

Click on manage jenkins<br>

Click on manage plugins<br>

Click on avaiable section<br>

Search for plugin ( deploy to container )<br>

Select that plugin and click on install without restart.<br>

20) Click on post build actions of the development job<br>

21) Click on add post build actions<br>

22) Click on deploy war/ear to container<br>

23) Enter the path of the war file (or)<br>
 we can give **/*.war in war/ear files.<br>

24) Context path: qaenv<br>

25) Containers : select tomcat 8<br>

Credentials : Click on add<br>

select jenkins<br>

enter tomcat user name and password<br>

Click on add<br>

Select credentials.<br>

give the private ip of the QA server.<br>

http://private_ip:8080

26) Click on apply and save<br>

27) Run the job<br>

28) To access the home page<br>

public_ip_Qa_server:8080/qaenv<br>
















After testing completed we need to clone the testing code form github<br>
https://github.com/sunildevops77/TestingNew.git<br>


Step 1: Connect to Devserver from git bash<br>
Step 2: Start Jenkins    ( java  -jar  jenkins.war )<br>
Step 3: Create new item  ( Name - testing )<br>
	Source code management tab,  Git<br>
Repository URL - https://github.com/sunildevops77/TestingNew.git<br>

Apply -- Save<br>

Step 4: Run the job.<br>
Step 5: Check the path of the files which are downloaded.<br>
	/home/ubuntu/.jenkins/workspace/testing<br>
Step 6: Configure the same job ( testing )<br>
	Build -- Add build Step  -- Execute shell<br>
 	( Command: java -jar  testing.jar )<br>
	Command:   echo " Testing passed"<br>



Now both are independent job.<br>
To call testing job  after development job is completed<br>

Go to first job ( demo ) --  configure <br>
Post build actions -- add post build action -- build other project -<br> 
Projects to build - testing ( name of the job)<br>

-----------------------------------------------------------------------------


Copying artifacts from development job to testing job<br>

The artifacts (war) created by the development job should be passed to the testing job so that the testing job can deploy that into tomcat in the prod environment.<br>


Install Plugins<br>

1) Go to Jenkins dashboard<br>

2) Go to manage jenkins<br>

3) Click on Manage plugins<br>

4) Search for "Copy Artifact"  plugin<br>

5) Install the plugin<br>

Stage 5 : Continous Delivery<br>

1) Go to Development job <br>

2) Go to Configure<br>

3) Go to Post build actions tab<br>

4) Click on add post build action<br>

5) Click on Archive the artifacts<br>

6) Enter **/*.war<br>

7) Click on apply and save<br>

8) Go to testing Job<br>

9) Click on configure<br>

10) Go to Build section<br>

11) Click on add build steps<br>

12) Click on copy artifacts from another project<br>

13) Enter Development as project name<br>

14) For Deployment Go to Post build actions section<br>

15) Click on add post build action<br>

16) Click on deploy war/ear to a container<br>

17) Enter **/*.war in war/ear files<br>

18) Context path : prodenv<br>

19) Click on add container <br>

20) Select tomcat 8<br>

21) Select your Credentials<br>

22) Enter private ip:8080 of the prod server<br>

23) Click on Apply and save<br>



----------------------------------------------------------------------

1) enter linux command in Prod Server  -   cd /etc/tomcat8/

2) enter linux command in prod Server  -   ls

3) You will find the file tomcat-users.xml

4) Open the file -- sudo vim tomcat-users.xml

5) In the end we need to add one statement 
<user username="learning" password="sunilsunil" roles="manager-script,manager-status,manager-gui"/>

6)  we need to restart the service
sudo service tomcat8 restart




# Creating users in Jenkins

1 Open the dashboard of jenkins

2 click on manage jenkins

3 click on manage users

4 clcik on create users

5 enter user credentials

Creating roles and assgning
==============================
1 Install "role based authorization strategy" plugin

+++++++++++++++++++++++++

6 go to dashboard-->manage jenkins
7 click on configure global security
8 check enable security checkbox
9 go to authorization section-->click on role based    strategy  radio button
10 apply-->save

++++++++++++++++++++++++++


11 go to dashboard of jenkins
12 click on manage jenkins
13 click on manage and assign roles
14 click on mange roles
15 go to global roles and create a role "employee"
16 for this employee in overall give read access
   		 in view section give all access



17 go to project roles-->Give the role as developer
   and patter as Dev.* (ie developer role can access
   only those jobs whose name start with Dev)
18 similarly create another role as tester and assign    the pattern as "Test.*"
19 give all permisiinons to developrs and tester
20 apply--save


21 click on assign roles
22 go to global roles and add user1 and user2 
23 check user1 nad user2 as employees
24 go to item roles
25 add user1 and user2
26 check user1 as developer and user2 as tester
27 apply-->save

Restart Jenkins
http://13.233.127.59:8080/restart

If we login into jenkins as user1 we can access on the development related jobs and user2 can access only the testing related jobs



++++++++++++++++++++++++++++++


























































