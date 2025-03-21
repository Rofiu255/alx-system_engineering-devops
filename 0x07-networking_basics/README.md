alx-system_engineering-devops
0x07-networking_basics



Resources and keywords

Read or watch:

    OSI model
    Different types of network
    LAN network
    WAN network
    Internet
    MAC address
    What is an IP address
    Private and public address
    IPv4 and IPv6
    Localhost
    TCP and UDP
    TCP/UDP ports List
    What is ping /ICMP
    Positional parameters (https://adminschoice.com/bash-positional-parameters/)



Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:
OSI Model

    What it is
    How many layers it has
    How it is organized

What is a LAN

    Typical usage
    Typical geographical size

What is a WAN

    Typical usage
    Typical geographical size

What is the Internet

    What is an IP address
    What are the 2 types of IP address
    What is localhost
    What is a subnet
    Why IPv6 was created

TCP/UDP

    What are the 2 mainly used data transfer protocols for IP (transfer level on the OSI schema)
    What is the main difference between TCP and UDP
    What is a port
    Memorize SSH, HTTP and HTTPS port numbers
    What tool/protocol is often used to check if a device is connected to a network




Tasks
0. OSI model
mandatory
Score: 50.0% (Checks completed: 100.0%)

OSI (Open Systems Interconnection) is an abstract model to describe layered communication and computer network design. The idea is to segregate the different parts of what make communication possible.

It is organized from the lowest level to the highest level:

    The lowest level: layer 1 which is for transmission on physical layers with electrical impulse, light or radio signal
    The highest level: layer 7 which is for application specific communication like SNMP for emails, HTTP for your web browser, etc

Keep in mind that the OSI model is a concept, it’s not even tangible. The OSI model doesn’t perform any functions in the networking process. It is a conceptual framework so we can better understand complex interactions that are happening. Most of the functionality in the OSI model exists in all communications systems.



Questions:

What is the OSI model?

    Set of specifications that network hardware manufacturers must respect
    The OSI model is a conceptual model that characterizes the communication functions of a telecommunication system without regard to their underlying internal structure and technology
    The OSI model is a model that characterizes the communication functions of a telecommunication system with a strong regard for their underlying internal structure and technology

How is the OSI model organized?

    Alphabetically
    From the lowest to the highest level
    Randomly

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 0-OSI_model





1. Types of network
mandatory
Score: 50.0% (Checks completed: 100.0%)

LAN connect local devices together, WAN connects LANs together, and WANs are operating over the Internet.

Questions:

What type of network a computer in local is connected to?

    Internet
    WAN
    LAN

What type of network could connect an office in one building to another office in a building a few streets away?

    Internet
    WAN
    LAN

What network do you use when you browse www.google.com from your smartphone (not connected to the Wifi)?

    Internet
    WAN
    LAN

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 1-types_of_network



2. MAC and IP address 

Questions:

What is a MAC address?

    The name of a network interface
    The unique identifier of a network interface
    A network interface

What is an IP address?

    Is to devices connected to a network what postal address is to houses
    The unique identifier of a network interface
    Is a number that network devices use to connect to networks

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 2-MAC_and_IP_address

3. UDP and TCP 

Let’s fill the empty parts in the drawing above.

Questions:

    Which statement is correct for the TCP box:
        It is a protocol that is transferring data in a slow way but surely
        It is a protocol that is transferring data in a fast way and might loss data along in the process
    Which statement is correct for the UDP box:
        It is a protocol that is transferring data in a slow way but surely
        It is a protocol that is transferring data in a fast way and might loss data along in the process
    Which statement is correct for the TCP worker:
        Have you received boxes x, y, z?
        May I increase the rate at which I am sending you boxes?

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 3-UDP_and_TCP




4. TCP and UDP ports
mandatory
Score: 50.0% (Checks completed: 100.0%)

Once packets have been sent to the right network device using IP using either UDP or TCP as a mode of transportation, it needs to actually enter the network device.

If we continue the comparison of a network device to your house, where IP address is like your postal address, UDP and TCP ports are like the windows and doors of your place. A TCP/UDP network device has 65535 ports. Some of them are officially reserved for a specific usage, some of them are known to be used for a specific usage (but nothing is officially declared) and the rest are free of use.

While the full list of ports should not be memorized, it is important to know the most used ports, let’s start by remembering 3 of them:

    22 for SSH
    80 for HTTP
    443 for HTTPS

Note that a specific IP + port = socket.

Write a Bash script that displays listening ports:

    That only shows listening sockets
    That shows the PID and name of the program to which each socket belongs


Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 4-TCP_and_UDP_ports


5. Is the host on the network
mandatory
Score: 50.0% (Checks completed: 100.0%)

The Internet Control Message Protocol (ICMP) is a protocol in the Internet protocol suite. It is used by network devices, to check if other network devices are available on the network. The command ping uses ICMP to make sure that a network device remains online or to troubleshoot issues on the network.

Write a Bash script that pings an IP address passed as an argument.

Requirements:

    Accepts a string as an argument
    Displays Usage: 5-is_the_host_on_the_network {IP_ADDRESS} if no argument passed
    Ping the IP 5 times

Example:

sylvain@ubuntu$ ./5-is_the_host_on_the_network 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=63 time=12.9 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=63 time=13.6 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=63 time=7.83 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=63 time=11.3 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=63 time=7.57 ms

--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4006ms
rtt min/avg/max/mdev = 7.570/10.682/13.679/2.546 ms
sylvain@ubuntu$
sylvain@ubuntu$ ./5-is_the_host_on_the_network
Usage: 5-is_the_host_on_the_network {IP_ADDRESS}
sylvain@ubuntu$ 

It is interesting to look at the time value, which is the time that it took for the ICMP request to go to the 8.8.8.8 IP and come back to my host. The IP 8.8.8.8 is owned by Google, and the quickest roundtrip between my computer and Google was 7.57 ms which is pretty fast, which is a sign that the network path between my computer and Google’s datacenter is in good shape. A slow ping would indicate a slow network.

Next time you feel that your connection is slow, try the ping command to see what is going on!

Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x07-networking_basics
    File: 5-is_the_host_on_the_network


