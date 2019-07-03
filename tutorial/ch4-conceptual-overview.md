# Conceptual Overview

## 1. Key Abstractions

### 1.1 Node

[Node - Doxygen](https://www.nsnam.org/doxygen/classns3_1_1_node.html)

### 1.2 Application

[Application - Doxygen](https://www.nsnam.org/doxygen/classns3_1_1_application.html)

### 1.3 Channel

* Channel
    * CsmaChannel
    * PointToPointChannel
    * WifiChannel

### 1.4 Net Device

* NetDevice
    * CsmaNetDevice
    * PointToPointNetDevice
    * WifiNetDevice

### 1.5 Topology Helpers


## 2 A First ns-3 Script

```sh
cd ~/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29

./waf -d debug --enable-examples --enable-tests configure
```


### 2.6 Topology Helpers

[ns-3 Doxygen](https://www.nsnam.org/doxygen/index.html)
#### NodeContainer


#### PintToPointHelper


#### NetDeviceContainer


#### InternetStackHelper


#### IpV4AddressHelper

### 2.7 Applications

#### UdpEchoServerHelper


#### UdpEchoClientHelper


### 2.9 Building your script

```sh
cd ~/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29

cp examples/tutorial/first.cc scratch/

./waf --run scratch/first
```

Example run:

```sh
ubuntu@ubuntu-desktop:~/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29$ ./waf --run scratch/first
Waf: Entering directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Waf: Leaving directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Build commands will be stored in build/compile_commands.json
'build' finished successfully (11.086s)
At time 2s client sent 1024 bytes to 10.1.1.2 port 9
At time 2.00369s server received 1024 bytes from 10.1.1.1 port 49153
At time 2.00369s server sent 1024 bytes to 10.1.1.1 port 49153
At time 2.00737s client received 1024 bytes from 10.1.1.2 port 9
```