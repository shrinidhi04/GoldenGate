![](images/500/Lab500_image100.PNG)

Update August 17 2018

## CONNECT AND INTERACT WITH ADMINCLIENT
## Introduction

In this lab, you will take a look at how to connect and interact with the Microservices AdminClient. using Goldengate 12.3 micro services web interface in a Ravello environment.


Steps:
1. Open a command terminal (Figure 8-1).
Right mouse click -> Open Terminal

![](images/500/Lab500_image101.png)

2. Navigate to the Oracle GoldenGate 12.3 Home /bin directory (Figure 8-2).
$ cd /opt/app/oracle/product/12.3.0.1/oggcore_1/bin

![](images/500/Lab500_image102.png)

3. Start the AdminClient (Figure 8-3).
$ ./adminclient

![](images/500/Lab500_image103.png)

4. Connect to Oracle GoldenGate without a deployment (Figure 8-4).
OGG 1> connect http://ogg123rs:16000 as oggadmin password
welcome1

![](images/500/Lab500_image104.png)

Notice that you are not connected and that AdminClient provides you a list of deployment you can attempt to connect to.

5. Connect to an Oracle GoldenGate deployment (Figure 8-5).
OGG 2> connect http://ogg123rs:16000 deployment Atlanta_1
as oggadmin password welcome1

![](images/500/Lab500_image105.png)

6. Perform an “info all” command and other GoldenGate commands to see what
AdminClient can do

OGG Atlanta_1 3> info all

![](images/500/Lab500_image106.png)

Note: checkout the RLWRAP function as well (arrow up and down while in AdminClient)


At this point, you should have a fully functional Admin Client environment. 




![](images/500/Lab502_image100.PNG)

Update August 16, 2018

## Working with REST API
## Introduction

In this lab, you will take a look at how to pull a list of services from Oracle GoldenGate using the REST APIs. Replace <port> with the port number of the service you want to access.

Steps:
1. Open a command window (right mouse click – Open Terminal)

2. Try running the following CURL command.
curl -u oggadmin:welcome1 -H "Content-Type: application/json" -H "Accept:
application/json" -X GET
http://localhost:<port>/services/v2/deployments/SanFran_1/services/distsrvr/logs |
python -mjson.tool

3. Retrieve Log locations using the following CURL command
curl -u oggadmin:welcome1 -H "Content-Type:application/json" -H
"Accept:application/json" -X GET http://localhost:<port>/services/v2/logs | python - mjson.tool

![](images/800/Lab800_image101.png)

Appendix:

A: Run Swingbench
Steps:
1. Open a command terminal and navigate to the Swingbench bin directory (Figure A-1)
$ cd /opt/app/oracle/product/swingbench/bin


![](images/900/Lab900_image102.png)


2. Execute the swingbench command (Figure A-2)
$ ./swingbench

![](images/900/Lab900_image103.png)

3. Once Swingbench starts, select the SOE_Server_Side_V2 configuration file.

![](images/900/Lab900_image104.png)

4. Once Swingbench is open, update the Password, Connect String, and Benchmark Run
Time (Figure A-4)
Password: welcome1
Connect String: //ogg123rs/pdb1
Benchmark Run Time: 10 mins

![](images/900/Lab900_image105.png)

5. Execute Swingbench (Figure A-5)

![](images/900/Lab900_image106.png)

At this point you should see activity on the table by looking at the Extract/Replicats.
Correct any problems that may arise due.

At this point, you should have a fully functional REST Api environment. 



![](images/500/Lab503_image100.PNG)

Update August 16, 2018

## Working with mySQL
## Introduction

In this lab, you will take a look at how to pull a list of services from Oracle GoldenGate using mySQL.

Steps:
1. Connect to mySQL using Putty

![](images/500/Lab503_image101.png)
