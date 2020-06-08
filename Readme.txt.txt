1. Please write a simple CLI application in the language of your choice that does the following:
Print the numbers from 1 to 10 in random order to the terminal.

Answer:
a. Linux/mac os

1. Please download the random.sh file on to current working directory or under /tmp
2. Open shell terminal/ CLI
3. Change the permisson of the file 
$ sudo chmod 700 random.sh

4. Instruction to execute the random.sh file
This script will allow you to type any start number and any end number, so it works dynamically. In our case it should be 1 to 10
start number:1
end number: 10

5. Imagine you have placed the file under /tmp directory
execute the file
$ sh /tmp/ramdom.sh
Please enter the Start-Number: 1
Please enter the End-Number: 10


============================================

2.  Imagine a server with the following specs:

- 4 times Intel(R) Xeon(R) CPU E7-4830 v4 @ 2.00GHz

- 64GB of ram

- 2 tb HDD disk space

- 2 x 10Gbit/s nics

The server is used for SSL offloading and proxies around 25000 requests per second.
Please let us know which metrics are interesting to monitor in that specific case and how would you do that?  What are the challenges of monitoring this?

Answer:
=======
Key metrics that are important to monitor are:

1. Load on the server. CPU utilization, since 25k/sec request's we should keep an eye on the CPU utilization
2. Memory utilization
3. Disk I/O
4. Error logs
5. APM (Application performance monitoring, i.e JVM, Heap, Threads utilization)
6. Network (Amount of traffic coming in and out of routers)
7. Monitor SSL cretificate expiry
8. Monitoring malware attacks
9. SSL offloading basically two ways and which may need to be monitored.
    SSL Termination
    SSL Bridging
Above parameters can be monitored through any of the monitoring tools. eg: (wily, zabbix, splunk)

Key challenge would be to monitor server performace, when the load on server is high, performace will take a hit. 
During this situation we can set an alerts.
1. when CPU utilization reaches 80% we can set an warning alert.
2. when CPU utilizaton reaches 90% we can set a critical alret. This is where we can think of scaling the server by adding additional resources.

Note: We can think of creating a load balancer to avoid perfromance issues, by ditributing traffice across nodes.

Challenge monitoring:
======================
1. In my view, monotoring the SSL offloading would be key challange.
Looking at the huge number of request i.e 25k/sec, We have to monitor these requests to check for malwares
2. Monitoring DDoS attacks, have to look for increase in vloume of legitimate  SSL traffic that could result in DDoS.

  


