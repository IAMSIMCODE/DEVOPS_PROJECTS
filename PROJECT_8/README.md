# Automating Load Balancer Configuration With Shell Scripting

Streamliine your load balancer with ease using shell scripting and CICD on Jenkins

This project demonstrate how to automate the setup and maintenance of your load balancer using a freestyle job, enhancing efficiency and reducing manual effort. 


## Automate the deployment of webservers

We will automate the entire process, we will do that by writing a shell script that when ran, all that we would have manually do will be do automatically. Automation helps to speed up the deployment of services and reduce the chances of making errors. 

## Deploying and Configuring the Webservers 

All the process we need to deploy our webservers has been codified in the shell script below: 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/Script1.png)
![Alt text](images/script2.png)


Follow the steps below to run the script: 

Step 1: Provision an EC2 instance running ubuntu 22.04 

![Alt text](images/ubunturunning.png)


Step 2: Open port 8000 to allow traffic from anywhere using the security group 

![Alt text](images/inboundrule.png)

Step 3: Connect to the webserver via the terminal using SSH

![Alt text](images/copyssh.png)

![Alt text](images/connectTerm.png)

Step 4: Create a file, open in your code editor and paste the script above, save and close the code editor

![Alt text](images/copyCodeBelow.png)

![Alt text](images/OpenScriptFile.png)

Save the file and exit...

Step 5: Change the permission on the file to make it an executable using the command below

![Alt text](images/copyCodeBelow.png)

![Alt text](images/ChmodCom.png)

Step 6: Run the shell script using the command below 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/runScriptcom.png)

![Alt text](images/RunScriptComm1.png)

![Alt text](images/WelcomScren.png)


# Deployment of Nginx as a Load Balancer Using Shell Script

## Automate the Deployment of Nginx as a Load Balancer Using Shell Script 

Having successfully deployed and configured two webservers, we will move on to the load balancer.

Provision an EC2 instance running ubuntu 22.04, open port 80 to anywhere using the security group and connect to the load balancer via the terminal. 


All the steps to implement Load Balancer with Nginx has been codified in the script below:

Read the instructions carefully in the script to learn how to use the script 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/nginxScript1.png)
![Alt text](images/nginxScript2.png)

### Steps to run the shell script 

1. On your terminal, open a file nginx.sh using the command below 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/openNginxinVim.png)


2. Copy and paste the script above inside the file

3. Close the file using the command below 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/saveVim.png)


4. Change the file permisssion to make it an executable using the command below 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/changePervim.png)

5. Run the script with the command below 

![Alt text](images/copyCodeBelow.png)

![Alt text](images/RunscriptFinal.png)

### Verifying the setup 

#### WEBSERVER1
![Alt text](images/WelcomScren.png)


#### WEBSERVER2


![Alt text](images/welcomeScnServer2.png)


#### LOADBALANCER

![Alt text](images/LBSCREN.png)


#### THANK YOU!













