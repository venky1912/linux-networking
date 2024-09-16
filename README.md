# Linux Networking Commands

This project contains a collection of essential Linux networking commands, each with descriptions, practical examples, and the results they produce when run in a Linux environment.

## Commands Covered:

1. **ifconfig**  
   - **Description**: Displays or configures network interface parameters.
   - **Example**: 
     ```bash
     ifconfig eth0
     ```
   - **Result**:
     ```bash
     eth0      Link encap:Ethernet  HWaddr 00:0c:29:68:8e:10  
               inet addr:192.168.1.2  Bcast:192.168.1.255  Mask:255.255.255.0
               UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
               RX packets:217 errors:0 dropped:0 overruns:0 frame:0
               TX packets:174 errors:0 dropped:0 overruns:0 carrier:0
     ```

2. **ip**  
   - **Description**: Displays and configures network interfaces and IP addresses.
   - **Example**: 
     ```bash
     ip addr show
     ```
   - **Result**:
     ```bash
     2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
         link/ether 00:0c:29:68:8e:10 brd ff:ff:ff:ff:ff:ff
         inet 192.168.1.2/24 brd 192.168.1.255 scope global eth0
         valid_lft forever preferred_lft forever
     ```

3. **ping**  
   - **Description**: Tests connectivity to another host.
   - **Example**:
     ```bash
     ping google.com
     ```
   - **Result**:
     ```bash
     PING google.com (142.250.72.14) 56(84) bytes of data.
     64 bytes from 142.250.72.14: icmp_seq=1 ttl=56 time=28.1 ms
     64 bytes from 142.250.72.14: icmp_seq=2 ttl=56 time=27.4 ms
     --- google.com ping statistics ---
     2 packets transmitted, 2 received, 0% packet loss, time 1001ms
     ```

4. **netstat**  
   - **Description**: Shows network connections and routing tables.
   - **Example**:
     ```bash
     netstat -tuln
     ```
   - **Result**:
     ```bash
     Active Internet connections (only servers)
     Proto Recv-Q Send-Q Local Address           Foreign Address         State
     tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN
     udp        0      0 0.0.0.0:123             0.0.0.0:*                         
     ```

5. **traceroute**  
   - **Description**: Traces the route packets take to reach a destination.
   - **Example**:
     ```bash
     traceroute example.com
     ```
   - **Result**:
     ```bash
     traceroute to example.com (93.184.216.34), 30 hops max, 60 byte packets
      1  192.168.1.1 (192.168.1.1)  0.466 ms  0.372 ms  0.341 ms
      2  * * *
      3  72.14.198.14 (72.14.198.14)  8.021 ms  8.265 ms  7.931 ms
     ```

6. **nslookup**  
   - **Description**: Queries DNS to resolve domain names to IP addresses.
   - **Example**:
     ```bash
     nslookup example.com
     ```
   - **Result**:
     ```bash
     Server:		8.8.8.8
     Address:	8.8.8.8#53
     
     Non-authoritative answer:
     Name:	example.com
     Address: 93.184.216.34
     ```

7. **dig**  
   - **Description**: Performs DNS lookups and provides detailed information.
   - **Example**:
     ```bash
     dig example.com
     ```
   - **Result**:
     ```bash
     ;; QUESTION SECTION:
     ;example.com.           IN      A
     
     ;; ANSWER SECTION:
     example.com.    86000   IN      A       93.184.216.34
     ```

8. **curl**  
   - **Description**: Transfers data from or to a server.
   - **Example**:
     ```bash
     curl http://example.com
     ```
   - **Result**:
     ```html
     <!doctype html>
     <html>
     <head>
         <title>Example Domain</title>
     </head>
     <body>
         <h1>Example Domain</h1>
         <p>This domain is established to be used for illustrative examples in documents.</p>
     </body>
     </html>
     ```

9. **wget**  
   - **Description**: Downloads files from the web.
   - **Example**:
     ```bash
     wget http://example.com/file.tar.gz
     ```
   - **Result**:
     ```bash
     --2024-09-15 14:52:09--  http://example.com/file.tar.gz
     Resolving example.com... 93.184.216.34
     Connecting to example.com|93.184.216.34|:80... connected.
     HTTP request sent, awaiting response... 200 OK
     Length: 23456789 (23M) [application/x-gzip]
     Saving to: ‘file.tar.gz’
     ```

10. **ss**  
    - **Description**: Displays socket statistics.
    - **Example**:
      ```bash
      ss -tuln
      ```
    - **Result**:
      ```bash
      Netid  State      Recv-Q Send-Q     Local Address:Port       Peer Address:Port              
      tcp    LISTEN     0      128        0.0.0.0:22               0.0.0.0:*                     
      udp    UNCONN     0      0          0.0.0.0:123              0.0.0.0:*                     
      ```

11. **scp**  
    - **Description**: Securely copies files over the network.
    - **Example**:
      ```bash
      scp file.txt user@remote-host:/path/to/destination
      ```
    - **Result**:
      ```bash
      file.txt                           100%   12KB  256KB/s   00:00
      ```

12. **nmap**  
    - **Description**: Scans for open ports and services.
    - **Example**:
      ```bash
      nmap -p 80 example.com
      ```
    - **Result**:
      ```bash
      Starting Nmap 7.60 ( https://nmap.org ) at 2024-09-15 14:55 UTC
      Nmap scan report for example.com (93.184.216.34)
      Host is up (0.034s latency).
      PORT   STATE SERVICE
      80/tcp open  http
      ```

13. **hostname**  
    - **Description**: Displays or sets the system hostname.
    - **Example**:
      ```bash
      hostname
      ```
    - **Result**:
      ```bash
      my-computer
      ```

14. **route**  
    - **Description**: Shows or modifies the IP routing table.
    - **Example**:
      ```bash
      route -n
      ```
    - **Result**:
      ```bash
      Kernel IP routing table
      Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
      0.0.0.0         192.168.1.1     0.0.0.0         UG    0      0        0 eth0
      192.168.1.0     0.0.0.0         255.255.255.0   U     0      0        0 eth0
      ```

15. **ethtool**  
    - **Description**: Displays or changes network interface settings.
    - **Example**:
      ```bash
      ethtool eth0
      ```
    - **Result**:
      ```bash
      Settings for eth0:
          Supported ports: [ TP MII ]
          Supported link modes:   10baseT/Half 10baseT/Full 
                                  100baseT/Half 100baseT/Full 
          Speed: 1000Mb/s
          Duplex: Full
          Auto-negotiation: on
      ```

16. **tcpdump**  
    - **Description**: Captures and analyzes network traffic.
    - **Example**:
      ```bash
      tcpdump -i eth0
      ```
    - **Result**:
      ```bash
      tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
      listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes
      14:56:18.178960 IP 192.168.1.2.53057 > example.com.http: Flags [S], seq 2753540491, win 29200, options [mss 1460,sackOK,TS val 1801292 ecr 0,nop,wscale 7], length 0
      ```

## How to Use

- Each command in this project is explained with an example and its corresponding result. To use any command, simply copy the example and replace it with your own parameters.
- For more information on any command, you can use the `--help` flag (e.g., `ip --help`) or check the official Linux man pages by typing `man <command>`.

## Requirements

- Linux operating system
- Basic understanding of Linux terminal and networking concepts

