# Tweaking

## 1. Using the Logging Module

### 1.1 Logging Overview

* LOG_ERROR
* LOG_WARN
* LOG_DEBUG
* LOG_INFO
* LOG_FUNCTION
* LOG_LOGIC
* LOG_ALL

### 1.2 Enabling Logging

```sh
export NS_LOG=UdpEchoClientApplication=level_all
```

```sh
ubuntu@ubuntu-desktop:~/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29$ ./waf --run scratch/first
Waf: Entering directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Waf: Leaving directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Build commands will be stored in build/compile_commands.json
'build' finished successfully (11.661s)
UdpEchoClientApplication:UdpEchoClient(0xc480a0)
UdpEchoClientApplication:SetDataSize(0xc480a0, 1024)
UdpEchoClientApplication:StartApplication(0xc480a0)
UdpEchoClientApplication:ScheduleTransmit(0xc480a0, +0.0ns)
UdpEchoClientApplication:Send(0xc480a0)
At time 2s client sent 1024 bytes to 10.1.1.2 port 9
At time 2.00369s server received 1024 bytes from 10.1.1.1 port 49153
At time 2.00369s server sent 1024 bytes to 10.1.1.1 port 49153
UdpEchoClientApplication:HandleRead(0xc480a0, 0xc49a20)
At time 2.00737s client received 1024 bytes from 10.1.1.2 port 9
UdpEchoClientApplication:StopApplication(0xc480a0)
UdpEchoClientApplication:DoDispose(0xc480a0)
UdpEchoClientApplication:~UdpEchoClient(0xc480a0)
```


```sh
export 'NS_LOG=UdpEchoClientApplication=level_all|prefix_func'
```

Output:

```sh
ubuntu@ubuntu-desktop:~/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29$ ./waf --run scratch/first
Waf: Entering directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Waf: Leaving directory `/home/ubuntu/projects/ns3/tarballs/ns-allinone-3.29/ns-3.29/build'
Build commands will be stored in build/compile_commands.json
'build' finished successfully (12.101s)
UdpEchoClientApplication:UdpEchoClient(0x1178bc0)
UdpEchoClientApplication:SetDataSize(0x1178bc0, 1024)
UdpEchoClientApplication:StartApplication(0x1178bc0)
UdpEchoClientApplication:ScheduleTransmit(0x1178bc0, +0.0ns)
UdpEchoClientApplication:Send(0x1178bc0)
UdpEchoClientApplication:Send(): At time 2s client sent 1024 bytes to 10.1.1.2 port 9
At time 2.00369s server received 1024 bytes from 10.1.1.1 port 49153
At time 2.00369s server sent 1024 bytes to 10.1.1.1 port 49153
UdpEchoClientApplication:HandleRead(0x1178bc0, 0x11804d0)
UdpEchoClientApplication:HandleRead(): At time 2.00737s client received 1024 bytes from 10.1.1.2 port 9
UdpEchoClientApplication:StopApplication(0x1178bc0)
UdpEchoClientApplication:DoDispose(0x1178bc0)
UdpEchoClientApplication:~UdpEchoClient(0x1178bc0)
```

```sh
export 'NS_LOG=UdpEchoClientApplication=level_all|prefix_func:UdpEchoServerApplication=level_all|prefix_func'
```


```sh
export 'NS_LOG=UdpEchoClientApplication=level_all|prefix_func|prefix_time:UdpEchoServerApplication=level_all|prefix_func|prefix_time'
```


### 1.3 Adding Logging to your code

Add to source code:

```c++
NS_LOG_COPONENT_DEFINE("FirstScriptExample")

NS_LOG_INFO ("Creating Topology")
```

```sh
# Compile
./waf

# Set NS_LOG 
export 'NS_LOG='
```

```sh
# Set NS_LOG 
export 'NS_LOG=FirstScriptExample=info'

# Run it
./waf --run "scratch/myfirst"
```

## 2 Using Command Line Arguments

### 2.1 Overiding Default Attribute

```sh
./waf --run "scratch/myfirst --PrintHelp"
```

### 2.2 Hooking your own value

## 3 Using the Tracing System

### 3.1 ASCII Tracing

### 3.2 PCAP Tracing


```sh
tcpdump -nn -tt -r myfirst-0-0.pcap 
```