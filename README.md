# Network Pentesting Tools
![Git-Hub-Mark](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/github.png)

- [Nmap](https://github.com/0x-Jayanta/HPTI-SEP23-109#1-nmap---network-mapper)
- [T-Shark](https://github.com/0x-Jayanta/HPTI-SEP23-109#2-tshark)
- [NetCat](https://github.com/0x-Jayanta/HPTI-SEP23-109#3-netcat)
- [Wireshark](https://github.com/0x-Jayanta/HPTI-SEP23-109#4-wireshark)
- [TCP-Dump](https://github.com/0x-Jayanta/HPTI-SEP23-109#5-tcp-dump)
- [Hping](https://github.com/0x-Jayanta/HPTI-SEP23-109#6-hping---a-network-scanning-and-testing-tool)
- [Rust Scan](https://github.com/0x-Jayanta/HPTI-SEP23-109#7-rustscan---fast-port-scanner)
- [Mass Scan](https://github.com/0x-Jayanta/HPTI-SEP23-109#8-masscan---mass-ip-port-scanner)
- [Zen Map](https://github.com/0x-Jayanta/HPTI-SEP23-109#9-zenmap---network-discovery-and-security-auditing-tool)
- [SMB Client](https://github.com/0x-Jayanta/HPTI-SEP23-109#10-smbclient---smbcifs-network-client)
- [Enum4Linux](https://github.com/0x-Jayanta/HPTI-SEP23-109#11-enum4linux---smb-enumeration-tool)
- [SNMP Walk](https://github.com/0x-Jayanta/HPTI-SEP23-109#12-snmpwalk---snmp-network-discovery-tool)
- [MACOF](https://github.com/0x-Jayanta/HPTI-SEP23-109#13-macof---mac-address-flooding-tool)
- [DNS Spoof](https://github.com/0x-Jayanta/HPTI-SEP23-109#14-dnsspoof---dns-spoofing-tool)
- [Ettercap](https://github.com/0x-Jayanta/HPTI-SEP23-109#15-ettercap---network-sniffing-and-man-in-the-middle-attack-tool)
- [Metasploit](https://github.com/0x-Jayanta/HPTI-SEP23-109#16-metasploit-framework---penetration-testing-and-exploitation-tool)
- [Nessus](https://github.com/0x-Jayanta/HPTI-SEP23-109#17-nessus---comprehensive-vulnerability-scanning-and-assessment-tool)
- [Hydra](https://github.com/0x-Jayanta/HPTI-SEP23-109#18-hydra---fast-and-flexible-password-cracking-tool)
- [Medusa](https://github.com/0x-Jayanta/HPTI-SEP23-109#19-medusa---versatile-network-password-cracking-tool)
- [Aircrack-NG](https://github.com/0x-Jayanta/HPTI-SEP23-109#20-aircrack-ng---a-powerful-wi-fi-network-security-toolkit)

## 1) Nmap - Network Mapper
Nmap is a network scanning tool used for discovering devices, open ports, services, and sometimes even the operating system on a computer network. It's commonly used by network administrators and security professionals for various network-related tasks, including security assessments and system monitoring.

[Download Link](https://nmap.org/download)

Most Linux distributions include Nmap in their official repositories. You can install it using your distribution's package manager. For example, on Debian or Ubuntu, you can run:

```bash
sudo apt-get update
sudo apt-get install nmap
```
Check Version:
```bash
nmap --version 
OR
nmap -V
```
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/nmap.png)

#### Basic Scan (Ping Scan):
```bash
nmap -sn <target>
```
#### TCP SYN Scan:
```bash
nmap -sS <target>
```
#### TCP Connect Scan:
```bash
nmap -sT <target>
```
#### Version Detection:
```bash
nmap -sV <target>
```
#### Operating System Detection:
```bash
nmap -O <target>
```
#### Service Script Scan:
```bash
nmap -sC <target>
```
#### Aggressive Scan:
```bash
nmap -A <target>
```
#### UDP Scan:
```bash
nmap -sU <target>
```
#### Scan a Range of Hosts:
```bash
nmap <start_ip>-<end_ip>

nmap 192.168.1.1-254
```
#### Output to a File:
```bash
nmap -oN <output_file> <target>
```

## 2) TShark
Tshark is a command-line network protocol analyzer, also known as a packet sniffer. It allows you to capture and analyze network traffic in real-time. It's similar to Wireshark but operates entirely from the command line. Tshark is a powerful tool for network troubleshooting, security analysis, and protocol debugging.

[Download Link](https://tshark.dev/setup/install/)

Installing Tshark on Linux Operating System:
```shell
sudo apt install tshark
```
Check version:

```shell
tshark --version 
```
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/tshark.png)

## Basic Tshark Commands for Network Packet Analysis

### Capture Network Traffic

Capture packets on a specific network interface:

```shell
tshark -i <interface>
```
### Capture packets and write them to a file
```shell
tshark -i <interface> -w <output_file>
```
### Read and display packets from a saved capture file

```shell
tshark -r <input_file>
```
### Filter Packets:

Apply display filters to narrow down packet analysis:

```shell
tshark -i <interface> -Y "http"
```
### Statistics and Summary

Generate statistics for a capture file:

```shell
tshark -r <input_file> -qz io,stat,0,<column_name>

tshark -r <input_file> -qz io,stat,0,ip
```


## 3) NetCat
Netcat, often referred to as "nc," is a versatile command-line networking utility on Linux and other Unix-like systems. It serves multiple purposes, including:

1. **Network Connection:** Netcat can establish, listen for, and manage network connections, making it useful for various network tasks.

2. **Port Scanning:** It can be used for basic port scanning to check which ports are open on a target system.

3. **File Transfer:** Netcat can transmit data between systems, making it handy for file transfer or as a makeshift chat client.

4. **Remote Shell Access:** It can create reverse or bind shell connections, enabling remote command execution.

5. **Proxying:** Netcat can act as a network proxy, redirecting traffic between different systems.

Netcat's simplicity and versatility make it a valuable tool for network troubleshooting, testing, and exploitation, but it should be used responsibly and only in authorized and ethical contexts.

[Download Link](hhttps://nmap.org/ncat/) 🔗


Installing NetCat on Linux Operating System:
```shell
sudo apt install netcat
```

### TCP Server (Listen for Incoming Connections)
```shell
nc -l -p <port>
nc -l -p 1234
```
![Netcat](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/netcat.png)

### UDP Server (Listen for Incoming Connections)
```shell
nc -u -l -p <port>
nc -u -l -p 1234
```
### Reverse Connection (Client) Mode
Reverse TCP Connection
```shell
nc -v <target> <port>
nc -v example.com 12345
```
### File Transfer
Send a File
```shell
nc -w 3 example.com 12345 < file.txt
```
Receive a File
```shell
nc -l -p 12345 > received_file.txt
```

## 4) Wireshark
Wireshark is a powerful open-source network packet analyzer that allows you to capture, inspect, and analyze network traffic in real-time. It provides detailed information about network protocols, helping you troubleshoot network issues, monitor network activity, and perform security analysis.

### Installation

You can install Wireshark on various operating systems:

- **Linux:** Use your distribution's package manager, such as `apt` or `yum`. For example:

  ```shell
  sudo apt-get update
  sudo apt-get install wireshark
  ```

## Basic Usage

👉 **Start Wireshark:** Open Wireshark from your applications menu or by running the following command in your terminal:

    ```shell
    wireshark
    ```

👉 **Select Network Interface:** After launching Wireshark, you'll be prompted to select a network interface to capture traffic from. Choose the appropriate interface for your analysis.
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/w1.png)

👉 **Capture Packets:** Once you've selected the network interface, click the "Start" button in the Wireshark interface to begin capturing packets. Wireshark will start capturing and displaying network traffic in real-time.
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/w2.png)

👉 **Stop Capture:** To stop the capture, simply click the "Stop" button in the Wireshark interface. This will halt the packet capture process.
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/w3.png)

👉 **Analyze Packets:** Wireshark will display captured packets in its main window. You can analyze these packets by inspecting the details, applying filters to narrow down the displayed packets, and using various tools and features provided by Wireshark for in-depth analysis.

👉 **Save Capture:** To save your captured traffic for further analysis or sharing, go to the "File" menu in Wireshark and select "Save As." Choose a file format and provide a filename to save your capture data.
![App Screenshot](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/w4.png)


## 📜 Wireshark Cheatsheet 📜
![Image](https://cdn.comparitech.com/wp-content/uploads/2019/06/Wireshark-Cheat-Sheet-1.jpg.webp)

                                           Source:- comparitech


# 5) TCP-Dump
`Tcpdump` is a powerful command-line packet analyzer available on various Unix-like operating systems, including Linux. It allows you to capture and analyze network traffic in real-time or from a previously captured file. `tcpdump` is a valuable tool for network troubleshooting, monitoring, and security analysis. Here are some common uses and commands for `tcpdump`

![TCP Dump](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/tcpdump.png)

1. **Capture Packets in Real-Time:**
   ```
   sudo tcpdump -i <interface>
   ```
   Replace `<interface>` with the network interface you want to capture packets from (e.g., eth0, wlan0).

2. **Capture Packets to a File:**
   ```
   sudo tcpdump -i <interface> -w <output_file>
   ```
   This command captures packets from the specified interface and saves them to the specified output file for later analysis.

3. **Display Captured Packets Verbosely:**
   ```
   sudo tcpdump -i <interface> -v
   ```
   This option provides more detailed information about captured packets, including the packet header.

4. **Filter Packets by Protocol:**
   ```
   sudo tcpdump -i <interface> icmp
   ```
   Replace `icmp` with the protocol you want to filter. You can use protocols like `tcp`, `udp`, `http`, or `ssh`.

5. **Capture Packets with a Specific Port:**
   ```
   sudo tcpdump -i <interface> port <port_number>
   ```
   Replace `<port_number>` with the specific port you want to capture packets for.

6. **Capture Packets with Source/Destination IP:**
   ```
   sudo tcpdump -i <interface> src <source_ip>
   sudo tcpdump -i <interface> dst <destination_ip>
   ```
   Use these commands to filter packets based on their source or destination IP address.

7. **Display Hexadecimal and ASCII Dump:**
   ```
   sudo tcpdump -i <interface> -XX
   ```
   This option displays both the hexadecimal and ASCII representation of packet data.

8. **Read Packets from a Capture File:**
   ```
   tcpdump -r <input_file>
   ```
   This allows you to analyze previously captured packets from a file.

9. **Limit the Number of Packets to Capture:**
   ```
   sudo tcpdump -i <interface> -c <count>
   ```
   Replace `<count>` with the number of packets you want to capture before `tcpdump` exits.

10. **Save Captured Packets as a PCAP File:**
    ```
    sudo tcpdump -i <interface> -w <output_file>.pcap
    ```
    This command saves the captured packets in the PCAP (Packet Capture) format, which is widely supported by network analysis tools.

# 6) Hping - A Network Scanning and Testing Tool


**Hping** is a powerful and flexible network scanning and testing tool for analyzing and manipulating network protocols. It is designed to provide network professionals, system administrators, and security experts with a versatile set of tools for network exploration, packet crafting, and network testing.

## Key Features

- **Active Scanning**: Conduct active network scanning to discover hosts, services, and open ports on a network.

- **Packet Crafting**: Create and send custom packets with specific characteristics, making it useful for crafting custom network traffic.

- **Advanced Ping**: Perform advanced ping operations such as TCP, UDP, and ICMP ping with various options and modes.

- **Traceroute**: Visualize the network path taken by packets from source to destination.

- **Firewall Testing**: Test firewall rules and configurations by sending different types of packets to target systems.

- **Fragmentation and MTU Discovery**: Examine fragmentation and Maximum Transmission Unit (MTU) issues on a network.

## Installation

```shell
sudo apt install hping3
```

## Usage

**1. TCP Ping:**
```bash
hping3 -c 1 -V -S -p 80 <target_host>
```
![hping](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/hping.png)

**2. UDP Ping:**
```bash
hping3 -c 1 -V -2 -p 53 <target_host>
```
**3. ICMP Ping:**
```bash
hping3 -c 1 -V -1 <target_host>
```
**4. Traceroute:**
```bash
hping3 --traceroute <target_host>
```
**5. SYN Scan:**
```bash
hping3 -S -p 80 <target_host>
```
**6. Simple DOS attack:**
```bash
hping3 -S --flood -V -p 80 <target_host>
```

# 7) RustScan - Fast Port Scanner

**RustScan** is a lightning-fast, highly configurable port scanner written in Rust. It is designed to be efficient and easy to use, making it an ideal choice for network professionals, penetration testers, and security enthusiasts who need to quickly discover open ports on target hosts.

## Key Features

- **Speed and Efficiency**: RustScan is built for speed, allowing you to scan ports quickly, making it suitable for both large and small networks.

- **Configurability**: Customize your scans with a wide range of options, including port ranges, rate limiting, and output formats.

- **Banner Grabbing**: RustScan can retrieve banners from open ports, providing additional information about the services running on the target.

- **IPv6 Support**: Scan both IPv4 and IPv6 addresses seamlessly.

- **Concurrency**: Utilize the power of Rust's async I/O to scan multiple hosts or ports simultaneously.

## Installation

Install RustScan using Cargo:

```shell
cargo install rustscan
```

## Usage

**1. Scan a Single Host:**

Scan a single host (e.g., example.com) for common ports (1-65535):
```shell
rustscan -a google.com
```
![rustscan](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/rustscan.png)

**2. Scan a Host Range:**

Scan a range of IP addresses (e.g., 192.168.1.1-10) for common ports:
```shell
rustscan 192.168.1.1-10
```

**3. Scan Specific Ports:**

Scan a host (e.g., example.com) for specific ports (e.g., 80, 443, 22):
```shell
rustscan example.com -p 80,443,22
```

**4. Scan Using Custom Output Format:**

Scan a host (e.g., example.com) and save the results in JSON format:
```shell
rustscan example.com -- -oJ output.json
```

**5. Enable Banner Grabbing:**

Scan a host (e.g., example.com) and retrieve banners from open ports:
```shell
rustscan example.com -b
```

# 8) Masscan - Mass IP Port Scanner


**Masscan** is a high-speed, high-performance mass IP port scanner designed for large-scale network scanning operations. It's a powerful tool that allows network professionals, security analysts, and researchers to quickly discover open ports on large IP ranges and hosts.

## Key Features

- **Speed and Efficiency**: Masscan is optimized for speed and can scan large networks in a short amount of time.

- **Customizable Scanning**: Configure the scanner to scan specific IP ranges, ports, and scan rates to suit your needs.

- **Banner Grabbing**: Retrieve banners from open ports to identify the services running on target hosts.

- **IPv4 and IPv6 Support**: Masscan supports both IPv4 and IPv6 addresses, making it versatile for different network environments.

- **Flexible Output**: Generate output in various formats, including XML and JSON, for easy integration with other tools and reporting.

## Installation

```shell
sudo apt-get install masscan
```

## Usage

**1. Basic Scan:**

To perform a basic scan of a range of IP addresses, use the following command:

```shell
masscan -p <port_range> <target>
```
![rustscan](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/masscan.png)

**2. Banner Grabbing:**

Masscan can also perform banner grabbing to identify services running on open ports. Use the `-b` option for banner grabbing:
```shell
masscan -p <port_range> --banner <target>
```
**3. Output to a File:**
Save the scan results to a file (e.g., results.txt) using the -oL option:

```shell
masscan -p <port_range> <target> -oL results.txt
```

# 9) Zenmap - Network Discovery and Security Auditing Tool

**Zenmap** is a graphical user interface (GUI) for Nmap, the renowned open-source network scanning tool. It provides an intuitive and user-friendly interface to interact with Nmap's robust scanning and auditing capabilities. Zenmap is suitable for both beginners and experienced network professionals.

## Key Features

- **User-Friendly Interface**: Zenmap's GUI simplifies the process of configuring and launching Nmap scans, making it accessible to users of all skill levels.

- **Network Discovery**: Discover hosts, services, and open ports on local and remote networks.

- **Security Auditing**: Perform vulnerability assessment and security auditing by identifying open ports, services, and potential vulnerabilities.

- **Profile Management**: Save and load scan profiles for efficient scanning of frequently visited networks.

- **Interactive Results**: View and analyze scan results interactively with detailed information about discovered hosts and services.

## Installation

**Linux (Debian/Ubuntu):**

### Step_1
```bash
wget https://nmap.org/dist/zenmap-7.94-1.noarch.rpm
```
### Step_2
```bash
sudo apt install alien
```
### Step_3
```bash
sudo alien --to-deb zenmap-7.94-1.noarch.rpm
```
### Step_4
```bash
sudo chmod 777 zenmap_7.91-2_all.deb && sudo apt install ./zenmap_7.91-2_all.deb
```
### Step_5
```bash
sudo zenmap
```
![Zenmap Logo](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/zenmap.png)

## Usage
👉 Launch Zenmap from your applications menu or command line.

👉 Use the GUI to configure your scan options, such as the target hosts, scan profile, and scan type.

👉 Click the "Scan" button to start the scan.

👉 Review and analyze the scan results using Zenmap's user-friendly interface.

![Scan Output](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/zenmap-output.png)

# 10) SMBclient - SMB/CIFS Network Client

**SMBclient** is a command-line utility that provides a means to access and interact with resources shared using the Server Message Block (SMB) or Common Internet File System (CIFS) protocol. It is a versatile tool for network enumeration, file sharing, and interaction with Windows-based network resources.

## Key Features

- **Access Windows Shares**: Connect to and access shared folders, printers, and resources on Windows-based machines.

- **File Transfer**: Upload and download files and directories between your local system and remote SMB/CIFS shares.

- **Authentication**: Authenticate to remote SMB/CIFS servers with various authentication methods, including username/password and anonymous access.

- **Directory Listing**: List the contents of remote directories and shares to gather information about available resources.

- **Interactive Mode**: Use an interactive shell to navigate and interact with remote SMB/CIFS shares.
## Installation
```shell
sudo apt install smbclient
```
![smbclient](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/smbclient.png)
## Usage

### Connecting to a Remote Share:

To connect to a remote SMB/CIFS share, use the following command:

```bash
smbclient //server/share -U username
```
Replace server with the target server's hostname or IP address, share with the name of the shared resource, and username with the appropriate credentials.

### Listing Remote Files and Directories:
Once connected, you can list the contents of a remote directory as follows:
```bash
smb:> dir
```
### Downloading Files:
Download a file from the remote share to your local system:
```bash
smb:> get filename
```
### Uploading Files:
Upload a file from your local system to the remote share:
```bash
smb:> put localfile
```
### Interactive Mode:
Enter interactive mode to navigate and interact with the remote share:
```bash
smb:> interactive
```

# 11) Enum4linux - SMB Enumeration Tool

**Enum4linux** is a command-line tool designed for SMB enumeration on Windows-based networks. It is a valuable asset for penetration testers and network administrators, providing the ability to extract valuable information from Windows systems, such as user and group lists, share information, and more.

## Key Features

- **User Enumeration**: Enumerate Windows users and their details, including usernames, full names, and SID values.

- **Group Enumeration**: Gather information about Windows groups, including group names and associated SIDs.

- **Share Enumeration**: Discover shared resources on remote Windows systems, including share names and descriptions.

- **Password Policy Enumeration**: Retrieve password policy information, including password complexity requirements and lockout policies.

- **SNMP Information**: Retrieve SNMP information, including community strings, from Windows hosts.

## Usage

### Basic Usage:

To perform a basic enumeration of a target Windows system, use the following command:

```bash
enum4linux -a <target>
```
Replace <target> with the IP address or hostname of the target Windows system.
### User Enumeration:
Enumerate Windows users on a target system:
```bash
enum4linux -u <target>
```
### Group Enumeration:
Enumerate Windows groups on a target system:
```bash
enum4linux -g <target>
```
### Share Enumeration:
Enumerate shared resources on a target system:
```shell
enum4linux -s <target>
```

# 12) SNMPwalk - SNMP Network Discovery Tool

**SNMPwalk** is a command-line utility used for querying devices and network equipment that support the Simple Network Management Protocol (SNMP). It enables network administrators, security professionals, and system engineers to gather valuable information from SNMP-enabled devices, such as routers, switches, printers, and servers.

## Key Features

- **SNMP Queries**: Perform SNMP queries to retrieve information from network devices, including system information, interfaces, CPU and memory usage, and more.

- **OID Tree Exploration**: Explore the SNMP OID (Object Identifier) tree structure to discover available data points and metrics on SNMP-enabled devices.

- **Community String Authentication**: Authenticate to SNMP-enabled devices using SNMP community strings, providing access to different levels of information.

- **MIB Support**: Use Management Information Base (MIB) files to translate numeric OIDs into human-readable labels for easier interpretation.

## Usage

### Basic Usage:

To perform a basic SNMPwalk on a target device, use the following command:

```bash
snmpwalk -v <version> -c <community_string> <target>
```
`version`: SNMP version (e.g., 1, 2c, 3).

`community_string`: SNMP community string (e.g., public, private).

`target` IP address or hostname of the SNMP-enabled device.



# 13) MACOF - MAC Address Flooding Tool

**macof** is a command-line tool designed to flood a network with fake MAC addresses. This technique is commonly used in network penetration testing and security assessment to disrupt network operations, overwhelm switches, and potentially trigger security mechanisms that detect and respond to suspicious traffic.

## Key Features

- **MAC Flooding**: Generates and sends a large number of random MAC addresses to flood a network segment.

- **Switch Testing**: Tests the behavior of switches in response to MAC address flooding, including MAC address table saturation.

- **Penetration Testing**: Used by penetration testers to evaluate the security of network infrastructure and identify vulnerabilities related to MAC address handling.

- **Security Awareness**: Raises awareness about the potential risks associated with MAC address flooding and helps network administrators implement appropriate security measures.
## Installation
```shell
sudo apt-get install dsniff
```

## Usage

### Basic Usage:

To perform MAC address flooding on a network segment, use the following command:

```bash
sudo macof -i <interface> -d <destination> -n <times>
```
![macof Logo](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/macof.png)

# 14) dnsspoof - DNS Spoofing Tool

**dnsspoof** is a command-line tool that enables DNS spoofing attacks on a network. It allows network professionals, security analysts, and penetration testers to manipulate DNS (Domain Name System) responses, redirecting DNS queries to malicious or alternative servers. DNS spoofing can be used for various purposes, including phishing, traffic interception, and network reconnaissance.

## Key Features

- **DNS Spoofing**: Intercept DNS requests and provide malicious or alternative DNS responses.

- **Phishing Attacks**: Redirect users to fake websites to steal sensitive information, such as login credentials.

- **Traffic Analysis**: Capture DNS queries and responses for analysis or interception.

- **Network Reconnaissance**: Manipulate DNS responses to gather information about network infrastructure.

## Usage

### Basic Usage:

To perform DNS spoofing on a network, use the following command:

```bash
dnsspoof -i <interface> -f <hosts_file>
```
`interface`: Specify the network interface to listen for DNS requests and send spoofed responses.

`hosts_file:` Provide a file with DNS spoofing rules to define target domains and their corresponding IP addresses.

### Example Hosts File:
Here's an example of a hosts_file you could create:
```bash
www.google.com 192.168.1.100
mail.google.com 192.168.1.101
```
This rule means that when a device on the network queries for **www.google.com,** dnsspoof will respond with the IP address 192.168.1.100.

### Running dnsspoof:
1) Identify the network interface you want to listen on. You can use the ifconfig or ip addr command to list available network interfaces.

2) Create a hosts_file containing the DNS spoofing rules.

3) Run dnsspoof with the chosen network interface and the path to the hosts_file:
```shell
sudo dnsspoof -i eth0 -f /etc/hosts
```
![dns Spoof](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/dnsspoof.png)


# 15) Ettercap - Network Sniffing and Man-in-the-Middle Attack Tool

**Ettercap** is a powerful and feature-rich network sniffing and man-in-the-middle (MITM) attack tool used for network analysis, traffic interception, and security assessment. It allows network professionals, penetration testers, and security analysts to capture and analyze network traffic, perform MITM attacks, and conduct various network security tests.

## Key Features

- **Packet Capture**: Capture network packets to analyze traffic passing through a network interface.

- **MITM Attacks**: Intercept and manipulate network traffic between two parties, potentially revealing sensitive information.

- **Protocol Analysis**: Analyze various network protocols to understand communication.

- **Traffic Redirection**: Redirect network traffic to another host for inspection or manipulation.

- **SSL/TLS Decryption**: Decrypt SSL/TLS-encrypted traffic for analysis and inspection.
## Installation
```shell
sudo apt-get install ettercap-graphical
```

## Usage

### Basic Usage:

To start using Ettercap in text mode, run:

```bash
sudo ettercap -G
```
![Ettercap Logo](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/ettercap.png)

### Using the Ettercap GUI:

Once the Ettercap GUI is launched, you'll have access to a graphical interface that makes it easier to perform network analysis and man-in-the-middle attacks.

#### 1. Interface Selection:

- In the GUI, you'll see a list of available network interfaces. Select the network interface you want to use for network analysis and click "OK."

#### 2. Target Selection:

- After selecting the network interface, you can choose your targets. Click "Hosts" in the menu, and then select "Scan for hosts" to scan the network for available hosts.

- Once hosts are discovered, you can select one or more hosts as your targets by clicking on them.

#### 3. Attack Options:

- Click "Mitm" in the menu to access man-in-the-middle attack options. Here, you can choose various attack methods, such as ARP poisoning or DNS spoofing, to intercept traffic between hosts.

#### 4. Start the Attack:

- Click "Start" in the menu to begin the selected attack. Ettercap will start intercepting and analyzing network traffic between the specified hosts.

#### 5. Packet Analysis:

- The Ettercap GUI provides real-time packet analysis. You can view captured packets, including their source and destination addresses, protocols, and contents.

#### 6. Plugins and Filters:

- Ettercap supports plugins and filters that can be accessed through the GUI. These can help you customize and extend the tool's functionality.

#### 7. SSL/TLS Decryption:

- If you're intercepting SSL/TLS-encrypted traffic, you can configure SSL dissection options in the GUI to decrypt and analyze the encrypted data.

#### 8. Stop the Attack:

- When you're done with your analysis or MITM attack, click "Stop" in the menu to halt the attack and close Ettercap gracefully.


# 16) Metasploit Framework - Penetration Testing and Exploitation Tool
**Metasploit Framework** is a widely-used open-source penetration testing and exploitation tool that enables security professionals, ethical hackers, and penetration testers to assess and exploit vulnerabilities in systems, applications, and networks. It offers a comprehensive suite of tools for reconnaissance, exploitation, post-exploitation, and reporting.

## Key Features

- **Exploit Modules**: Access a vast repository of exploit modules targeting known vulnerabilities in various systems and software.

- **Payloads**: Generate and deliver malicious payloads to compromised systems for post-exploitation activities.

- **Post-Exploitation Modules**: Execute post-exploitation activities, such as privilege escalation, lateral movement, and data exfiltration.

- **Integration**: Integrate with other security tools and frameworks for seamless workflow.

- **Reporting**: Generate detailed reports to document findings and vulnerabilities.

## Usage

### Basic Usage:
Metasploit console provides a command-line interface for accessing various modules and features.

To start using Metasploit, launch the interactive console by running:

```bash
msfconsole
```
![msfconsole](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/msfconsole.png)


## Port scanning using Metasploit
In Metasploit, you can perform port scanning using the `auxiliary/scanner/portscan/tcp `module. This module allows you to scan a range of IP addresses and ports to identify open ports and potential targets. 

Here's the basic command to perform a TCP port scan using Metasploit:
```shell
use auxiliary/scanner/portscan/tcp
set RHOSTS 192.168.1.1-192.168.1.254
set PORTS 80,443,8080
set THREADS 10
set TIMEOUT 500
set VERBOSE true
set STOP_ON_SUCCESS true
run
```
![MSF Output](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/MSF.png)

# 17) Nessus - Comprehensive Vulnerability Scanning and Assessment Tool

**Nessus** is a widely-used and powerful vulnerability scanning and assessment tool designed to help organizations identify, assess, and remediate security vulnerabilities in their IT infrastructure. Trusted by security professionals, IT teams, and compliance auditors, Nessus provides a comprehensive solution for improving cybersecurity posture.

## Key Features

- **Vulnerability Scanning**: Automatically scans networks, systems, applications, and devices for known vulnerabilities and misconfigurations.

- **Plugin Architecture**: Offers a vast library of security plugins for detecting vulnerabilities and compliance issues.

- **Compliance Auditing**: Assists in compliance checks against industry standards and regulatory frameworks, such as PCI DSS, CIS, and more.

- **Customization**: Allows users to create custom policies, scan templates, and configuration profiles to suit specific requirements.

- **Detailed Reporting**: Generates comprehensive reports with detailed information on vulnerabilities, severity levels, and recommended remediation steps.

- **Scalability**: Scales to handle large and complex environments, making it suitable for enterprises and organizations of all sizes.

- **Integration**: Supports integration with other security tools and frameworks through APIs, making it a valuable part of a broader security ecosystem.

## Usage

### Basic Usage:

To start using Nessus, follow these basic steps:

1. **Installation**: Refer to the installation section to install Nessus on your system.

2. **Configuration**: Set up Nessus by configuring scan policies, targets, and credentials for scanning.

3. **Scanning**: Initiate vulnerability scans against defined targets and policies.

4. **Analysis**: Review scan results to identify vulnerabilities, prioritize them, and assess their impact.

5. **Reporting**: Generate detailed reports with findings, recommendations, and compliance checks.

6. **Remediation**: Take action to address identified vulnerabilities and compliance issues.

For advanced options and customization, please refer to the Nessus documentation or resources.

## Installation

### Prerequisites:

- Nessus is available for Windows, Linux, and macOS.

### Installation Steps:

1. Download the Nessus installer from the [official Tenable website](https://www.tenable.com/products/nessus).

2. Follow the installation instructions for your specific operating system.

3. Launch Nessus and access it through a web browser.

4. Activate Nessus by providing the activation code or using a trial license.

## Usage
It seems like you're describing a scenario where you want to perform a basic vulnerability scan using a tool like Nessus on a virtual machine (VM) with a known IP address. Here's a step-by-step guide based on your description:

**Assumptions**:
- You have already installed Nessus on your host computer.
- You have identified the IP address of your target VM.

### 1. Launch Nessus:

- Open your web browser and navigate to the Nessus web interface. This is typically accessible at `https://localhost:8834` or using the IP address and port of your Nessus server.

- Log in with your Nessus credentials.

### 2. Create a New Basic Scan:

- In the Nessus web interface, click on "Scans" in the left navigation panel.

- Click the "New Scan" button to create a new scan.

### 3. Configure the Scan:

- **General Settings**:
  - Give the scan a descriptive name.
  - Optionally, provide a description.

- **Scan Template or Policy**:
  - Choose a scan template or policy that aligns with your scanning needs. You can create custom policies if necessary.

- **Targets**:
  - In the "Targets" section, input the IP address of your target VM. You can specify a single IP address, a range of IP addresses, or even a subnet, depending on your requirements.

- **Schedule**:
  - Configure the scan schedule if needed. For a one-time scan, you can leave this section as is.

- **Notifications**:
  - Configure email notifications if you want to receive alerts when the scan completes or when vulnerabilities are found.

- **Advanced**:
  - You can configure advanced scan settings and options here, such as port scanning preferences and credential settings if the VM requires authentication for scanning.

### 4. Save the Scan Configuration:

- After configuring the scan settings, click the "Save" button to save the scan configuration.

### 5. Launch the Scan:

- In the list of scans, find the scan you just configured and click on it to select it.

- Click the "Launch" button to start the scan.

### 6. Monitor and Review Results:

- Nessus will begin scanning the target VM. You can monitor the progress of the scan within the Nessus web interface.

- Once the scan is complete, you can review the results, including identified vulnerabilities, in the Nessus web interface.

### 7. Remediate Vulnerabilities:

- Based on the scan results, prioritize and address vulnerabilities on your VM. Implement security patches, reconfigure settings, or take other actions as needed to enhance the security of the VM.

![Nessus Logo](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/Nessus.jpg)

# 18) Hydra - Fast and Flexible Password Cracking Tool

**Hydra**, also known as THC-Hydra, is a versatile and powerful password cracking tool used by security professionals, penetration testers, and ethical hackers to test and assess the security of authentication systems. It is designed to perform brute-force and dictionary attacks against various network protocols and services.

## Key Features

- **Protocol Support**: Hydra supports a wide range of network protocols and services, including SSH, FTP, HTTP, RDP, Telnet, SMB, and many more.

- **Flexible Attack Modes**: Offers multiple attack modes, including brute-force, dictionary-based, and hybrid attacks, making it adaptable to different scenarios.

- **Multi-Threaded**: Utilizes multi-threading and parallelism to improve cracking speed and efficiency.

- **Customizable**: Allows users to create custom wordlists and rules for password generation.

- **Session Resumption**: Supports the resumption of interrupted attack sessions, saving time and resources.

- **Logging and Reporting**: Provides detailed logs and reports of cracking attempts and results.

- **Community Contributions**: Hydra benefits from a vibrant community of users and contributors, constantly expanding its capabilities and supported services.
## Installation

### Prerequisites:

- Hydra is available for various Linux distributions and platforms.

### Installation:
```shell
sudo apt install hydra 
```

## Usage

### Basic Usage:

To start using Hydra, follow these basic steps:

1. **Installation**: Refer to the installation section to install Hydra on your system.

2. **Choose a Target Protocol**: Identify the network protocol or service you want to target (e.g., SSH, FTP, HTTP).

3. **Configure the Attack**: Specify the target host, port, and attack parameters. You can customize attack mode, wordlists, and other options.

4. **Start the Attack**: Launch the attack using the specified options and watch Hydra attempt to crack passwords.

5. **Review Results**: Analyze the results to identify successfully cracked passwords and access accounts.

6. **Remediation**: Based on the results, take action to strengthen password security, such as implementing stronger password policies.

For advanced options and customization, please refer to the Hydra documentation or resources.

### To perform ftp attack, you can use a command like the following:
```shell
hydra -l username -p password ftp://target-ip
```
### SSH Username And Password Brute force
```shell
 hydra -L user.txt -P pass.txt 192.168.29.229 ssh -t 5
```
![hydra](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/hydra.png)


# 19) Medusa - Versatile Network Password Cracking Tool
**Medusa** is a powerful and versatile network password cracking tool used by cybersecurity professionals, penetration testers, and ethical hackers to assess the security of network services and authentication mechanisms. It is designed to perform brute-force and dictionary attacks against various network protocols and services.

## Key Features

- **Protocol Support**: Medusa supports a wide range of network protocols and services, including SSH, FTP, Telnet, HTTP, RDP, VNC, and more.

- **Flexible Attack Modes**: Offers multiple attack modes, including brute-force, dictionary-based, and hybrid attacks, allowing for adaptation to different scenarios.

- **Parallelism**: Utilizes parallelism and concurrency to improve cracking speed and efficiency.

- **Customizable**: Allows users to create custom wordlists and rules for password generation.

- **Session Resumption**: Supports the resumption of interrupted attack sessions, saving time and resources.

- **Logging and Reporting**: Provides detailed logs and reports of cracking attempts and results.

- **Community-Driven**: Medusa benefits from an active community of users and contributors, constantly enhancing its capabilities and expanding its supported services.
## Installation
```shell
sudo apt install medusa
```

## Usage

### Basic Usage:

To start using Medusa, follow these basic steps:

1. **Installation**: Refer to the installation section to install Medusa on your system.

2. **Choose a Target Protocol**: Identify the network protocol or service you want to target (e.g., SSH, FTP, HTTP).

3. **Configure the Attack**: Specify the target host, port, and attack parameters. Customize attack mode, wordlists, and other options as needed.

4. **Start the Attack**: Launch the attack using the specified options and observe Medusa's attempts to crack passwords.

5. **Review Results**: Analyze the results to identify successfully cracked passwords and compromised accounts.

6. **Remediation**: Based on the results, take action to strengthen password security, such as implementing stronger password policies.

For advanced options and customization, please refer to the Medusa documentation or resources.

## SSH Brute Force Attack:
```shell
medusa -h target_ip -u username -P passwords.txt -M ssh
```
![ssh](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/medusa.png)

This command attempts to brute-force SSH access to the target IP using the specified username and a list of passwords from the passwords.txt file.

## FTP Dictionary Attack:
```shell
medusa -h target_ip -U usernames.txt -P passwords.txt -M ftp -T 5
```
This command performs a dictionary attack against an FTP server running on the target IP. It uses a list of usernames from usernames.txt and a list of passwords from passwords.txt. The -T option specifies a maximum of 5 login attempts per second.

## HTTP Brute Force Attack:
```shell
medusa -h target_ip -u admin -P passwords.txt -M http -m DIR:/admin -T 10
```
This command attempts to brute-force HTTP authentication for the /admin directory on the target IP. It uses the username admin and a list of passwords from passwords.txt. The -m option specifies the directory to target, and the -T option sets a maximum of 10 login attempts per second.


# 20) Aircrack-ng - A Powerful Wi-Fi Network Security Toolkit

**Aircrack-ng** is a comprehensive and versatile Wi-Fi network security toolkit designed for assessing and improving the security of wireless networks. It includes a collection of tools for capturing, analyzing, and cracking Wi-Fi network encryption keys. Aircrack-ng is widely used by security professionals, penetration testers, and ethical hackers.

## Key Features

- **Wi-Fi Security Assessment**: Aircrack-ng provides tools for auditing the security of Wi-Fi networks, including WEP, WPA, and WPA2 networks.

- **Packet Capture**: Capture Wi-Fi packets from wireless interfaces to analyze network traffic and identify vulnerabilities.

- **Cracking Tools**: Aircrack-ng includes tools for cracking encryption keys, such as WEP keys (Wired Equivalent Privacy) and WPA/WPA2 pre-shared keys, through various attack methods.

- **Deauthentication Attack**: Perform deauthentication attacks to disconnect clients from a Wi-Fi network, facilitating the capture of handshake packets.

- **Extensive Hardware Support**: Aircrack-ng supports a wide range of Wi-Fi adapters and chipsets for packet capture and injection.

- **Cross-Platform**: Available for Linux, macOS, Windows, and other platforms, making it accessible to a broad audience.

- **Community-Driven**: Aircrack-ng is actively maintained and benefits from contributions from the Wi-Fi security community.

## Installation

### Prerequisites:

- Aircrack-ng is available for various operating systems, including Linux, macOS, and Windows.

### Installation Steps:

1. Download the Aircrack-ng package from the [official Aircrack-ng website](https://www.aircrack-ng.org/).

2. Follow the installation instructions provided for your specific operating system.

3. Once installed, you can run Aircrack-ng tools from the command line.

## Usage

### Basic Usage:

To start using Aircrack-ng, follow these basic steps:

1. **Installation**: Refer to the installation section to install Aircrack-ng on your system.

2. **Capture Packets**: Use tools like `airodump-ng` to capture Wi-Fi packets from wireless interfaces. Identify target networks and clients.

3. **Deauthentication Attack**: Optionally, perform a deauthentication attack (`aireplay-ng`) to capture the WPA/WPA2 handshake between a client and an access point.

4. **Crack Encryption Key**: Use tools like `aircrack-ng` to attempt to crack the captured encryption key. Provide the captured packets and dictionary or brute-force options.

5. **Analyze Results**: Review the results to determine if the encryption key was successfully cracked.

6. **Security Recommendations**: Based on the results, provide recommendations for improving network security, such as using stronger encryption protocols and complex passwords.

For advanced options and customization, please refer to the Aircrack-ng documentation or resources.

## Output

![Aircrack-ng Logo](https://raw.githubusercontent.com/0x-Jayanta/HPTI-SEP23-109/main/images/aircrack-ng.png)
