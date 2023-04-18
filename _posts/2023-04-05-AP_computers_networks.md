---
toc: true
comments: true
layout: post
title: Computers and Networks (Unit 4)
description: Add Definitions from Unit 4 Computer Systems and Networks
image: /images/apcsp.png
categories: []
type: ap
week: 29
---

## Requirements
> Work through College Board Unit 4... blog, add definitions, and pictures.  Be creative, for instance make a story of Computing and Networks that is related to your PBL experiences this year.


### How a Computer Works
> As we have learned, a computer needs aa program to do something smart.  The sequence of a program initiates a series of actions with the computers Central Processing Unit (CPU). This component is essentially a binary machine focussing on program instructions provided.  The CPU retrieives and stores the data it acts upon in Random Access Memory (RAM). Between the CPU, RAM, and Storage Devices a computer can work with many programs and large amounts of data.

List specification of your Computer, or Computers if working as Pair/Trio
- Processor GHz:
- Memory in GB:
- Storage in GB:
- OS:

Define or describe usage of Computer using Computer Programs. Pictures are preferred over a lot of text.  Use your experience.
- Input devices
- Output devices
- Program File
- Program Code
- Processes
- Ports
- Data File
- Inspect Running Code
- Inspect Variables


![Computer Hardware]({{site.baseurl}}/images/cpu.jpeg)


### The Internet
> Watch/review College Board Daily Video for 4.1.1

- Essential Knowledge
    - A computing device is a physical artifact that can run a program. Some examples include computers, tablets, servers, routers, and smart sensors.
    - A computing system is a group of computing devices and programs working together for a common purpose.
    - A computer network is a group of interconnected computing devices capable of sending or receiving data.
    - A computer network is a type of computing system. 
    - A path between two computing devices on a computer network (a sender and a receiver) is a sequence of directly connected computing devices that begins at the sender and ends at the receiver.
    - Routing is the process of finding a path from sender to receiver.
    - The bandwidth of a computer network is the maximum amount of data that can be sent in a fixed amount of time.
    - Bandwidth is usually measured in bits per second

- Complete Vocabulary Matching Activity.  Incorporate this into your learnings from year.  To analyze measure path and latency use `traceroute` and `ping` commands from Linux Terminal.  
    - Path 
    - Route
    - Computer System
    - Computer Device
    - Bandwidth
    - Computer Network

> Watch/review College Board Daily Video 4.1.2

- Complete True of False Questions

- Essential Knowledge
    - The internet is a computer network consisting of interconnected networks that use standardized, open (nonproprierary) communication protocols.
    - Access to the internet depends on the ability to connect a computing device to an internet connected device.
    - A protocol is an agreed-upon set of rules that specify the behavior of a system.
    - The protocols used in the internet are open, which allows users to easily connect additional computing devices to the internet.
    - Routing on the internet is usually dynamic; it is not specified in advance
    - The scalability of a system is the capacity for the system to change in size and scale to meet new demands.
    - The internet was designed to be scalable
    - Information is passed through the internet as a data stream. Data streams contain chunks of data, which are encapsulated in packets. 
    - Packets contain a chunk of data and metadata used for routing the packet between the origin and the destination on the internet, as well as for data reassembly.
    - Packets may arrive at the destination in order, out of order, or not at all
    - IP, TCP and UDP are common protocols used on the internet.
    - The world wide web is a system of linked pages, programs, and files.
    - HTTP is a protocol used by the world wide web
    - The world wide web uses the internet

- Go over AP videos, vocabulary, and essential knowledge.  Draw a diagram showing the internet and its many levels. A preferred diagram would using your knowledge of frontend, backend, deployment, etc.  Picture would highlight vocabulary by illustration. The below illustration have some ideas

![Full Stack]({{site.baseurl}}/images/fullstack.png)


- Often we draw pictures of machines communicating over the Internet with arrows.  However, the real communication goes through protocol layers and the machine and then is transported of the network.   For College Board and future Computer Knowledge you should become familiar with the following ...

```
     User Machine  <---> Frontend Server <---> Backend Server
    +-----------+         +-----------+         +-----------+
    |  Browser  |         |  GH Page  |         |   Flask   |
    +-----------+    ^    +-----------+    ^    +-----------+
    |    HTTP   |    |    |    HTTP   |    |    |    HTTP   |
    +-----------+    |    +-----------+    |    +-----------+
    |    TCP    |    |    |    TCP    |    |    |    TCP    |   
    +-----------+    |    +-----------+    |    +-----------+
    |     IP    |    V    |     IP    |    V    |     IP    |
    +-----------+         +-----------+         +-----------+
    |  Network  |  <--->  |  Network  |  <--->  |  Network  |
    +-----------+         +-----------+         +-----------+
```

The "http" layer is an application layer protocol in the TCP/IP stack, used for ***communication between web browsers and web servers***. It is the protocol used for transmitting data over the World Wide Web.

The "transport" layer (TCP) is responsible for providing reliable data transfer between applications running on different hosts.  The TCP protocol segments the data into smaller ***chunks called "segments"***. Each segment contains a sequence number that identifies its position in the original stream of data, as well as other control information such as source and destination port numbers, and checksums for error detection.

The "ip" layer is responsible for packetizing data received from the TCP layer of the protocol stack, and then ***encapsulating the data into IP packets***. The IP packets are then sent to the lower layers of the protocol stack for transmission over the network.

The "network" layer is responsible for ***routing data packets between networks*** using the Internet Protocol (IP). This layer handles tasks such as packet addressing and routing, fragmentation and reassembly, and ***network congestion*** control.


### Fault Tolerance
> Watch both Daily videos for 4.2

- Complete the network activity, summarize your understanding of fault tolerance.

### Parallel and Distributed Computing
> Review previous lecture on Parallel Computing and watch Daily video 4.3.  Think of ways to make something in you team project to utilize Cores more effectively.  Here are some thoughts to add to your story of Computers and Networks...

- What is naturally Distributed in Frontend/Backend architecture?  

- Analyze this command in Docker: ```ENV GUNICORN_CMD_ARGS="--workers=1 --bind=0.0.0.0:8086"```.   Determine if there is options are options in this command for parallel computing within the server that runs python/gunicorn.  Here is an [article](https://medium.com/building-the-system/gunicorn-3-means-of-concurrency-efbb547674b7)


> Last week we discussed parallel computing on local machine.  There are many options.  Here is something to get parallel computing work with a tool called Ray.
- Review this [article](https://www.anyscale.com/blog/writing-your-first-distributed-python-application-with-ray)...  Can you get parallel code on images to work more effectively?  I have not tried Ray.

- Code example from ChatGPT using squares.  This might be more interesting if nums we generated to be a lot bigger.

```python
import ray

# define a simple function that takes a number and returns its square
def square(x):
    return x * x

# initialize Ray
ray.init()

# create a remote function that squares a list of numbers in parallel
@ray.remote
def square_list(nums):
    return [square(num) for num in nums]

# define a list of numbers to square
nums = [1, 2, 3, 4, 5]

# split the list into two parts
split_idx = len(nums) // 2
part1, part2 = nums[:split_idx], nums[split_idx:]

# call the remote function in parallel on the two parts
part1_result = square_list.remote(part1)
part2_result = square_list.remote(part2)

# get the results and combine them
result = ray.get(part1_result) + ray.get(part2_result)

# print the result
print(result)

```

# Hacks

## Answering Questions

Fault Tolerance: Fault tolerance is when a network still works and all the computers in the computer system are still connected even when a connection is removed. The more connections that can be removed, the more fault tolerant the network is.

List specification of your Computer, or Computers if working as Pair/Trio
- Processor GHz: The number of cycles the CPU executes per second. This number is measured in GHz (gigahertz).
- Memory in GB: Memory (measured in GB (gigabytes)) is data stored by the computer for it to be stored and accessed later.
- Storage in GB: Storage is used to store data and the data is stored in GB (gigabytes).
- OS: A software that supports a computer's basic functions. This is different for different computers made by different companies. Example: MacOS

Define or describe usage of Computer using Computer Programs. Pictures are preferred over a lot of text.  Use your experience.
- Input devices: An input device is a device that provides information by a user. Some examples are a keyboard and a mouse.
- Output devices: An output device is a device that displays an output in a certain form. An example of an output device is a speaker.
- Program File: A program file is a file or directory that is used to store a program that is to be run.
- Program Code: Instructions that are given to a machine to create a computer program.
- Processes: A process run on a computer to complete a specific task.
- Ports: A virtual point where network connections start and end. Different programs use different ports.
- Data File: A data file contains contains various data about a certain topic (data can be in different forms such as lists and strings).
- Inspect Running Code: This allows you to debug your code for any errors
- Inspect Variables: Where debuggers can be used to check the values of variables.

Vocab:
- Path: A path is a used to identify a location or directory.
- Route: A route is the way information is sent along a path.
- Computer System: A computer system can accept inputs, store data, and provide outputs.
- Computer Device: A computer device is a device that can be connected to the internet to transmit and accept data.
- Bandwidth: Bandwidth is the maximum amount of data that can be transferred at one time.
- Computer Network: A computer network is when many different computers and connected and can send information to each other in the form of packets.

## 4.2 Videos Practice Problems

### Video 1

![]({{site.baseurl}}/images/network1.png "Problem 1")

Answer: Yes, this network is fault tolerant because there are at least 2 connections on each computer which means that if any connection is removed, every computer would be able to connect with any other computer.

![]({{site.baseurl}}/images/network2.png "Problem 2")

Answer: No, this network is not fault tolerant as computer F doesn't have at least 2 connections. This means that removing the one connection to computer F will make it so none of the computers can communicate with computer F.

![]({{site.baseurl}}/images/network3.png "Problem 3")

Answer: No, this network is not fault tolerant because computer A only have 1 connections and removing this connections will make it so that none of the other computers can communicate with it.

### Video 2

![]({{site.baseurl}}/images/network4.png "Problem 4")

Answer: The answer is answer C because even though it's true that only one route will be taken at a time, this is not an example of a benefit of a fault tolerant network like the other examples. Also, this can be true with networks that are not fault tolerant too.

![]({{site.baseurl}}/images/network5.png "Problem 5")

Answer: A connection from A to B would make this network fault tolerant because then each computer will have at least 2 connections. This way, when any connection is removed, every computer will still have access to every other computer.

## 4.1.2 Video True or False

![]({{site.baseurl}}/images/TrueorFalse.png "Questions")

1. T
2. F
3. F
4. T
5. F
6. F
7. T