0x09. Web infrastructure design


Concepts

For this project, we expect you to look at these concepts:

    DNS
    Monitoring
    Web Server
    Network basics
    Load balancer
    Server

Resources

Read or watch:

    Network basics concept page
    Server concept page
    Web server concept page
    DNS concept page
    Load balancer concept page
    Monitoring concept page
    What is a database
    What’s the difference between a web server and an app server?
    DNS record types
    Single point of failure
    How to avoid downtime when deploying new code
    High availability cluster (active-active/active-passive)
    What is HTTPS
    What is a firewall





Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x09-web_infrastructure_design
    File: 0-simple_web_stack

1. Distributed web infrastructure
mandatory
Score: 0.0% (Checks completed: 0.0%)

On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com.

Requirements:

    You must add:
        2 servers
        1 web server (Nginx)
        1 application server
        1 load-balancer (HAproxy)
        1 set of application files (your code base)
        1 database (MySQL)
    You must be able to explain some specifics about this infrastructure:
        For every additional element, why you are adding it
        What distribution algorithm your load balancer is configured with and how it works
        Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
        How a database Primary-Replica (Master-Slave) cluster works
        What is the difference between the Primary node and the Replica node in regard to the application
    You must be able to explain what the issues are with this infrastructure:
        Where are SPOF
        Security issues (no firewall, no HTTPS)
        No monitoring

Please, remember that everything must be written in English to further your technical ability in a variety of settings.
Add URLs here:

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x09-web_infrastructure_design
    File: 1-distributed_web_infrastructure

2. Secured and monitored web infrastructure
mandatory
Score: 0.0% (Checks completed: 0.0%)

On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com, it must be secured, serve encrypted traffic, and be monitored.

Requirements:

    You must add:
        3 firewalls
        1 SSL certificate to serve www.foobar.com over HTTPS
        3 monitoring clients (data collector for Sumologic or other monitoring services)
    You must be able to explain some specifics about this infrastructure:
        For every additional element, why you are adding it
        What are firewalls for
        Why is the traffic served over HTTPS
        What monitoring is used for
        How the monitoring tool is collecting data
        Explain what to do if you want to monitor your web server QPS
    You must be able to explain what the issues are with this infrastructure:
        Why terminating SSL at the load balancer level is an issue
        Why having only one MySQL server capable of accepting writes is an issue
        Why having servers with all the same components (database, web server and application server) might be a problem

Please, remember that everything must be written in English to further your technical ability in a variety of settings.
Add URLs here:

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x09-web_infrastructure_design
    File: 2-secured_and_monitored_web_infrastructure

3. Scale up
#advanced
Score: 0.0% (Checks completed: 0.0%)

Readme

    Application server vs web server

Requirements:

    You must add:
        1 server
        1 load-balancer (HAproxy) configured as cluster with the other one
        Split components (web server, application server, database) with their own server
    You must be able to explain some specifics about this infrastructure:
        For every additional element, why you are adding it

Please, remember that everything must be written in English to further your technical ability in a variety of settings.
Add URLs here:

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x09-web_infrastructure_design
    File: 3-scale_up
 
