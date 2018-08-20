![](images/500/Lab500_image100.PNG)

Update August 20 2018

## CONNECT AND INTERACT WITH ADMINCLIENT
## Introduction

In this lab, you will take a look at how to connect and interact with the Microservices AdminClient. using Goldengate 12.3 micro services web interface in a Ravello environment.


Steps:
1. Open a command terminal
Right mouse click -> Open Terminal

![](images/500/Lab500_image101.PNG)

![](images/500/Lab500_image102.PNG)

2. Navigate to the Oracle GoldenGate 12.3 binary directory
cd /opt/app/oracle/product/12.3.0.1/oggcore_1/bin

![](images/500/Lab500_image103.PNG)

3. Start the AdminClient
./adminclient

![](images/500/Lab500_image104.PNG)

4. Connect to Oracle GoldenGate without a deployment

OGG 1> connect http://hostname:16000 as oggadmin password welcome1
![](images/500/Lab500_image104a.png)

Notice that you are not connected and that AdminClient provides you a list of deployment you can attempt to connect to.

5. Connect to an Oracle GoldenGate deployment.
OGG 2> connect http://hostname:16000 as oggadmin password welcome1

![](images/500/Lab500_image105.png)

Notice that you are not connected and te AdminClient provides you a list of deployments you can attempt to connect to

OGG 2> connect http://hostname:16000 deployment Atlanta_1
as oggadmin password welcome1
![](images/500/Lab500_image106.png)

6. Perform an “info all” command and other GoldenGate commands to see what
AdminClient can do

OGG Atlanta_1 3> info all

![](images/500/Lab500_image107.png)

Note: checkout the RLWRAP function as well (arrow up and down while in AdminClient)


At this point, you should have a fully functional Admin Client environment. 


![](images/500/Lab502_image100.PNG)

## Working with REST API
## Introduction

In this lab, you will take a look at how to pull a list of services from Oracle GoldenGate using the REST APIs. Replace <port> with the port number of the service you want to access.

Steps:
1. Open a command window (right mouse click – Open Terminal)

2. Try running the following CURL command.
curl -u oggadmin:welcome1 -H "Content-Type: application/json" -H "Accept:
application/json" -X GET
http://hostname:<port>/services/v2/deployments/SanFran_1/services/distsrvr/logs |
python -mjson.tool

3. Retrieve Log locations using the following CURL command
curl -u oggadmin:welcome1 -H "Content-Type:application/json" -H
"Accept:application/json" -X GET http://hostname:<port>/services/v2/logs | python - mjson.tool

![](images/502/Lab502_image101.png)

Appendix:

A: Run Swingbench
Steps:
1. Open a command terminal and navigate to the Swingbench bin directory.
cd /opt/app/oracle/product/swingbench/bin

![](images/502/Lab502_image102.png)

2. Execute the swingbench command (Figure A-2)
./swingbench

![](images/502/Lab502_image103.png)

3. Once Swingbench starts, select the SOE_Server_Side_V2 configuration file.

![](images502/Lab502_image104.png)

4. Once Swingbench is open, update the Password, Connect String, and Benchmark Run
Time
Password: welcome1
Connect String: //hostname/pdb1
Benchmark Run Time: 10 mins

![](images/502/Lab502_image105.png)

5. Execute Swingbench

![](images/502/Lab502_image106.png)

At this point you should see activity on the table by looking at the Extract/Replicats.
Correct any problems that may arise due.

At this point, you should have a fully functional REST Api environment. 



![](images/500/Lab503_image100.PNG)

## Working with mySQL
## Introduction

In this lab, you will take a look at how to pull a list of services from Oracle GoldenGate using mySQL.

Steps:
1. Connect to mySQL using Putty

![](images/500/Lab503_image101.png)
