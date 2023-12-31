---
sidebar_position: 9
---

# The Craft of Network Scanning 

---



### **What is Active Scanning?**

Active scan, is scan in real time so the target may find the scanner.

### What are the pros and cons of Active Scanning?

**Pros** :- Active scanning has several benefits. It can detect more vulnerabilities than passive scanning, as it actively attempts to exploit any weaknesses it finds. It can also detect hidden vulnerabilities.

**Cons** :- Active scanning also has some drawbacks. It can be time consuming, as it requires more resources than passive scanning. Additionally, it can be disruptive to the system or network. The target or the entitles may find out that they have been active scan.

## **TTL Probs**

The **TTL** is determined by the remote host. The ping you see in the shell is the **echo-reply**. The initial **TTL** is set by the OS. Linux uses 64, Windows 128 and Routers 255. Every Hop reduces the TTL by at least 1

For example: If you ping a Linux Host and there are 20 Hops between, then the TTL is 64-20 = 44.

## **Network** **Scanning**

- Scanning is Active Information Gathering, find the network running, the operating system, application and software running, services running on a pc
- Network Scan: Scanning a network to find the number of systems connected to it. We can find potential targets in this stage
- Host Discovery: Net discover [ Which use ARP Protocols to recognizes the network]
- Route Discovery: Nmap
- Protocol and ports
- TCP/UDP
- DNS, HOST FILE
- Communication through Netcat, NMAP

## **Netcat and** **NetDiscover**

### **What is Netcat?**

-  **_Netcat_** : Is a software utility it can be a Server OR a Client.

### **Syntax & Command**

>#netstate -altp [ to see availability]

>#nc -lp 1234 [ any random port, l mean listing p means port]

|Listing and Using Random Port which is specified.|
|---|
|![Listing_AND_Port_Randoms](./cybersecurity_img/Active_Scanning/Netcad/Listing%20and%20Using%20Random%20Port.png)|


### **Syntax & Command**

>#nc (linux-ip-addr) 127.0.0.1 (random port ) 1234 ( start Server)

>#nc 127.0.0.1 1234

>#nc -lp 1234

|Getting reply form Server|
|---|
||
|![Getting_Reply_From_Server](./cybersecurity_img/Active_Scanning/Netcad/Getting%20reply%20form%20Server.png)|


## ***Network Scan Using NetDiscover***

### **What is Netdiscover?**
 
- Netdiscover Which use ARP Protocols to recognizes the network and network machines vendous 

|**netdiscover**|
|-------|
|**Syntax & Command** |
|![netdiscover1](./cybersecurity_img/Active_Scanning/Netdiscover/netdiscover.png)|

- Netdiscover Which use ARP Protocols to recognizes the network and network machines vendors.

|netdiscover|
|---|
|Syntax & Command|
|![netdiscover2](./cybersecurity_img/Active_Scanning/Netdiscover/netdiscover2.png)|
|netdiscover -r [ -r means Range]|
|netdiscover -r [ network id and mask] (Example: 192.168.50.0/24)|


|# ifconfig [ check your interface eth/fa]|
|---|
| Syntax Commands  |
|![ifconfig](./cybersecurity_img/Active_Scanning/Netdiscover/ifcnofig.png)|




## **Network Scanning Using Nmap**

### **What is Nmap?**

-  Nmap (Network Mapper) is a free and open-source tool used to discover hosts and services of devices

###  **Why Use Nmap For Hacking**

-  Nmap is a powerfull tool that can used to gather information about target systems. It can to identify open ports/services.

## **Pre-requisities**

Before you can use Nmap, you will need a basic understanding of the following:

- TCP/IP networking
- Command-line interface (CLI)
- Operating systems (Windows, Linux, macOS)

## **Installing Nmap**
 

|Nmap can be installed on various operating systems|
|---|
|Windows: https://nmap.org/download.html#windows|
| Linux: sudo apt-get install nmap|
| macOS: brew install nmap|

### **Basic Nmap Scanning**




### **Syntax & Command**
|Nmap has a wide range of command-line Commands & syntax|
|---|---|
|sS:|TCP SYN scan (Send SYN Packet)|
|sT:|TCP connect scan (3 way handshake)|
|sU:|UDP scan (Send UDP Packet)|
|sN|Null TCP (no TCP Header)|
|sF|Fin Scan (Send FIN Packet)|
|sX|Xmas Scan (Send TCP Flags Like RST,PSH,FIN)|
|sA|TCP ACK (To determine the Firewall is statefull or Stateless)|
|sW|TCP Windows Scan (Same TCP ACK Scan Get information about windows)|
|sZ|SCTP Echo Scan (Use the SCTP Protocol )|
|sO|Protocal Scan (Determine which Protocal is allow to end target)|
|-b|BounceBack FTP Scan (Use NSE Script FTP Anonymous and Null Sessions)|
|p:|Specify port range|
|O:|OS detection|
|A:|Aggressive scan|
|sV:|Service version detection|
|sC:|Script scanning using the default NSE scripts|
|Pn:|Treat all hosts as online (skip host discovery)|
|n:|Do not resolve hostnames|
|f:|Fragment packets|
|T0:|Paranoid timing (slowest)|
|T5:|Insane timing (fastest)|
|v:|Verbose output|
|oA:|Output in all formats (standard, XML, and grepable)|

### **Basic scan**

>  nmap (IP Address)  or nmap (website.com)

### **Host Discovery**

### **What is Host Discovery?**

The first step in nmap scaning is to find out the network's hosts

### **Syntax & Command**

>   nmap -sn (IPAddrs) or (IP Range)

### **Port Scanning**

### **What is Port Scanning**

Ones the hosts is discovered need to find what open ports are in those hosts

> nmap -p (port_range) (host)

### **Operating System Detection**

Nmap scan can also detect the OS of those hosts

>  nmap -O (host)

### **Handy options**

|   |   |
|---|---|
|sS|#nmap -sS [target-ipaddr] - Stealthy SYN scan|
|sU|#nmap –sU [target-ipaddr] -UDP Scan|
|sV|#nmap -sV[target-ipaddr] - version scan, will make complete connection, grab banner, and version info|
|A|#nmap -A[target-ipaddr] - A single argument aggressive scan. Which includes version and OS information, default script execution, and more.|
|oA|#nmap –oA [target-ipaddr]  [filename] - Print nmap output to file name|
|Pn|#nmap –Pn [target-ipaddr] - disable ping. Most big companies will have ping diabled on most external entities|
|n|#nmap -n[target-ipaddr] - disable DNS resolution, helps speed up scan|

### **Specify ports**

>   Top Ports >> # nmap [IP Address] --top-ports

|When firewall is On|
|---|
|   |
|![Title: When firewall is ON](./cybersecurity_img/Active_Scanning/nmap/whenfirewallisoff.png)|

|When Firewall is Off|
|---|
|![When Firewall is off](./cybersecurity_img/Active_Scanning/nmap/whenfirewallison.png)|

|Wireshark|
|---|
|![when firewall is off and on wiresharks](./cybersecurity_img/Active_Scanning/nmap/wiresharkforfirewallofonpacket.png)|



|All Ports|
|---|
| #nmap –p- [IP Address] by default is use TCP Stealth Scan|
|![All Ports ](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-p-.png)|

|  UDP Ports  |
|---|
|nmap –sU [IP Address]|
|Syntax & Command|
|![](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sU.png)|


|WireSharks|
|---|
||
|![UDP SCAN -sU ](./cybersecurity_img/Active_Scanning/specific_port_scan/nmapudp-su_wireshark1.png) |
|![UDP SCAN -sU ](./cybersecurity_img/Active_Scanning/specific_port_scan/nmapudp-su_wireshark2.png) |

| In real scenario Wireshark  |
|---|
|![](./cybersecurity_img/Active_Scanning/specific_port_scan/In_real_scenario_Wireshark.png)|

|TCP Ports (Connect Scan)|
|---|
|nmap -sT (IP Address)|
|![nmap -sT (IP Address)](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sT_P%20Address.png)|

|Wireshark for Nmap|
|---|
|![nmap -sT (IP Address) Wireshark](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sT_P%20Address_wireshark.png)|

|Quick TCP Scan|
|---|
|nmap -sC -sV -vv -oA quick (target-ip-addrs)|
|![nmap -sC -sV -vv -oA quick](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sC_-sV_-vv_-oA_quick_scan.png)|

|Quick UDP Scan|
|---|
|nmap -sU -sV -vv -oA quick_udp (target-ipaddress)|
|![nmap -sU -sV -vv -oA quick_udp](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sU_-sV_-vv_-oA_quick_udp.png)|

|Full TCP Scan|
|---|
|nmap -sC -sV -p- -vv -oA full (Target-IP Address)|
|![nmap -sC -sV -p- -vv -oA full](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sC%20_sV_-p-_-vv_-oA_full_TCP.png)|

|Host Discovery|
|---|
|The First Step in Nmap scan is to find networks host|
|nmap -sn (Target-ipaddress)|
|![nmap -sn](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sn.png)|


## **Banner Grabbing**

Banner grabbing collect information using devices banner >> #nmap -sV -v -p- [IP Address]
- OS SCAN -guess provides a faster, more aggressive scan, which is useful when Nmap retrieves close to 100% OS detection. However, aggressive scanning may result in missing some ports. 
- OS SCAN -limit is an option used to limit what targets to scan. This option is useful when you have a large range of IPs to scan.

### **Syntax & Command**


|nmap -sV -v -p- [IP Address]|
|---|
|![](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-sV_-v_-p-_bannergrabbing.png)|

|sudo nmap -O -sV [IP Address]|
|---|
|nmap -O -sV [IP Address]|
|![](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap_-O_-sV_banner_grabbing.png)|

## **Port Knock**

### **Syntax & Command**
This allows the command to quickly check the status of the specified ports on the target host and skip the ping process. 

|nmap -Pn --host-timeout 201ms --max-retries 0 -p 7000,8000,9000 [Target-IP]|
|---|
|![](./cybersecurity_img/Active_Scanning/specific_port_scan/nmap%20-Pn%20--host-timeout%20201ms%20--max-retries_port_knock.png)|


## **NSE -Nmap Scripting Engine**

## **What is NSE?**
Nmap Scripting Engine (NSE) allows users to run custom scripts. Which is stored in /usr/share/nmap/scripts 
NSE is LUA based Language.
There are many Services that Nmap has default scripts.



### **Let's  look any script...**
The  author of this script is 
Defaults Scripts

|author = {"Eddie Bell", "Rob Nicholls", "Ange Gutek", "David Fifield"}|
|---|
|![Insideinscript](./cybersecurity_img/Active_Scanning/nse/insidescript.png)|
|When open the script there are some variable defined which is the prerequisiteof script like ftp port etc which is …|
|![Inside_scripty_ftp](./cybersecurity_img/Active_Scanning/nse/insidescriptftd1.png)|
|As below see the functions|
|portrule = shortport.port_or_service({21,990}, {"ftp","ftps"})|
|To do this function it required Login which is anonymous login here |
|![Inside_Script_ftp2](./cybersecurity_img/Active_Scanning/nse/insidescriptftd2.png)|


|Wiresharks|
|---|
|![Wiresharks_ftp_script](./cybersecurity_img/Active_Scanning/nse/inside_script_wiresharks.png)|


- As see Is open ASCII mode Data connection for file list…

- After this the LIST will let 

|$LIST as this fuctions is in variable to send the cmd LIST to FTP Server , What is List it is name speech, it get the list details of ftp server.|
|---|
|![inside_scripts_ftd_3](./cybersecurity_img/Active_Scanning/nse/insidescriptftd3.png)|


|LIST on Linux |
|---|
|![inside_script_ftp_4](./cybersecurity_img/Active_Scanning/nse/insidescriptftd4.png)|

|Wiresharks|
|---|
|![Inside_script_ftp_wiresharks](./cybersecurity_img/Active_Scanning/nse/inside_script_ftp_wiresharks.png)|

|This is the output get because of LIST|
|---|
|![Inside-Scripty_ftp_results](./cybersecurity_img/Active_Scanning/nse/insidescriptftdresults.png)|


## **FTP Scans**

``` 
nmap 192.168.100.130 -p 21 -sVT --script=ftp-anon.nse 
```

|Syntax & Commands|
|---|
|-S TCP|
|-v for Version|
|-T For time template which by defaults is 3|


|Wiresharks|
|---|
|First Nmap uses the ARP Address to resolve the ip-addr, Then its send 3 way handshake and again send 3 way handshake.|
|![FTP_Wireshark_Scan](./cybersecurity_img/Active_Scanning/ftp_scan/ftp_scan_wiresharks.png)|
|As you can see the Nmap uses the login credentials|
|![FTP_Wireshark_scan_use_default_scan](./cybersecurity_img/Active_Scanning/ftp_scan/ftp_scan_nse_script_default_Scan.png)|


## **FTP Nmap Scan Use all Script**

|Syntax & Commands|
|---|
|![FTP_Scan_using_all_ports](./cybersecurity_img/Active_Scanning/ftp_scan/frp_scans_using_all_ports.png)|


VulnScan 
•	The basic way of running Nmap scripts is by using the -sC option, running the default scripts.
>>#nmap -sV -sC [target-ipaddr]

•	To run a specific script against a target, the name of the script must be specified in the command. 
>>#nmap -sV --script http-sql-injection.nse [target-ipaddr]

As well as specifying the name of the script, it is sometimes necessary to specify arguments to achieve the desired behaviour
>>#nmap --script http-wordpress-brute.nse --script-args ‘passdb=passwords.txt’ [target-ipadddr]
>>#nmap -sV --script mysql-dump-hashes [target-ipaddr] --script-args='username=root,password=abc123'

Run all NSE scripts against found ports
`$nmap -Pn -sV -O -pT:{TCP ports found},U:{UDP ports found} --script *vuln* $ip`


## **Nmap Traceroute**

- Which check the hosts are there in-between the source to destination...

|Syntax & Commands|
|---|
|![Nmap_Traceroute](./cybersecurity_img/Active_Scanning/nmap_traceroute/nmap_traceroute1.png)|


## **Aggresive Scans**

- As the name say the scan Aggressively which is  -A , -traceroute, -sC Defualt script scan, -Sv  Service Scan,  -O OS Prob

|Syntax & Commands|
|---|
|![Aggresive_Scan](./cybersecurity_img/Active_Scanning/aggresive_scan/aggresive_scan.png)|


## **Save The Output**

•	-O for the Output.
•	-oN to specific output in Nmap format

|Syntax & Commands|
|---|
|![Save_The_output_1](./cybersecurity_img/Active_Scanning/savetheoutpu/save_the_output1.png)|
|-oX  use combine with other tools |
|![saave_the_output2](./cybersecurity_img/Active_Scanning/savetheoutpu/save_the_output2.png)|
|-Os is for script kiddie which replace randoms alphabtes which randoms signs.|
|![save_the_output_3](./cybersecurity_img/Active_Scanning/savetheoutpu/save_the_output3.png)|
|-oG the grapabale, its provide the simiplyfied output which can be easy filter.|
|![save_the_output4](./cybersecurity_img/Active_Scanning/savetheoutpu/save_the_output4.png)|


## **Timing Templates**


Its start from -T0 to T5
T0 is easy slow scan which is harder to detects
As the T number increase 
The scan and chances of getting detect will increase.

|Syntax & Commands|
|---|---|
|T0|paranoid timing|
|T1 | sneaky timing|
|T2 | polite timing|
|T3 |normal timing|
|T4 | aggressive timing|
|T5 | insane timing|

|T5|
|---|
|![Save_the_output_T5](./cybersecurity_img/Active_Scanning/savetheoutpu/save_the_output_T5.png)|


## **Vulnerability Assessment (Nessus)**


### **What is Nessus?** 
Nessus is an automation tool which provides the enumeration and scanning in Graphical mode. 


### **How does Nessus work?**
In the backend   Its uses the open sources traditional service like nmap, netdiscover  etc but provides the output in Simple graphical format. In addition to the Nessus Vulnerability Scan, we also utilized a network port scan. With the results of this scan, we can see the internal footprint of open ports and services.


## Nessus Installation Script

```bash
#!/bin/bash
if [[ $(id -u) -ne 0 ]] ; then
    echo "Please run as root"
    exit 1
fi

echo "//=============================================================="
echo "   Nessus 10.5.1 DOWNLOAD, INSTALL, and CRACK   - Zen 20230123"
echo "   special thanks to John Doe for showing this works on Debian"
echo "//=============================================================="

echo " o making sure we have prerequisites.."
sudo apt-get update &>/dev/null
sudo apt-get install curl dpkg expect -y &>/dev/null

echo " o stopping old nessusd in case there is one!"
/bin/systemctl stop nessusd.service &>/dev/null

echo " o downloading Nessus.."
curl -A Mozilla --request GET \
  --url 'https://www.tenable.com/downloads/api/v2/pages/nessus/files/Nessus-10.5.2-debian10_amd64.deb' \
  --output 'Nessus-10.5.2-debian10_amd64.deb' &>/dev/null

{ if [ ! -f Nessus-10.5.2-debian10_amd64.deb ]; then
  echo " o nessus download failed :/ exiting. get a copy of it from t.me/pwn3rzs"
  exit 0
fi }

echo " o installing Nessus.."
chmod +x Nessus-10.5.2-debian10_amd64.deb &>/dev/null
dpkg -i Nessus-10.5.2-debian10_amd64.deb &>/dev/null

# Look, I tried to just make changes and run but it doesn't work. If you can optimize
# what I'm doing here, let me know. But this was it for me; it had to be run once :/

echo " o starting service once FIRST TIME INITIALIZATION (we have to do this)"
/bin/systemctl start nessusd.service &>/dev/null

echo " o let's allow Nessus time to initialize - we'll give it like 20 seconds..."
sleep 20

echo " o stopping the nessus service.."
/bin/systemctl stop nessusd.service &>/dev/null

echo " o changing nessus settings to Zen preferences (freedom fighter mode)"
echo "   listen port: 11127"
/opt/nessus/sbin/nessuscli fix --set xmlrpc_listen_port=11127 &>/dev/null

echo "   theme:       dark"
/opt/nessus/sbin/nessuscli fix --set ui_theme=dark &>/dev/null

echo "   safe checks: off"
/opt/nessus/sbin/nessuscli fix --set safe_checks=false &>/dev/null

echo "   logs:        performance"
/opt/nessus/sbin/nessuscli fix --set backend_log_level=performance &>/dev/null

echo "   updates:     off"
/opt/nessus/sbin/nessuscli fix --set auto_update=false &>/dev/null
/opt/nessus/sbin/nessuscli fix --set auto_update_ui=false &>/dev/null
/opt/nessus/sbin/nessuscli fix --set disable_core_updates=true &>/dev/null

echo "   telemetry:   off"
/opt/nessus/sbin/nessuscli fix --set report_crashes=false &>/dev/null
/opt/nessus/sbin/nessuscli fix --set send_telemetry=false &>/dev/null

echo " o adding a user you can change this later (u:admin, p:admin)"
cat > expect.tmp<<'EOF'
spawn /opt/nessus/sbin/nessuscli adduser admin
expect "Login password:"
send "admin\r"
expect "Login password (again):"
send "admin\r"
expect "*(can upload plugins, etc.)? (y/n)*"
send "y\r"
expect "*(the user can have an empty rules set)"
send "\r"
expect "Is that ok*"
send "y\r"
expect eof
EOF
expect -f expect.tmp &>/dev/null
rm -rf expect.tmp &>/dev/null

echo " o downloading new plugins.."
curl -A Mozilla -o all-2.0.tar.gz \
  --url 'https://plugins.nessus.org/v2/nessus.php?f=all-2.0.tar.gz&u=4e2abfd83a40e2012ebf6537ade2f207&p=29a34e24fc12d3f5fdfbb1ae948972c6' &>/dev/null

{ if [ ! -f all-2.0.tar.gz ]; then
  echo " o plugins all-2.0.tar.gz download failed :/ exiting. get a copy of it from t.me/pwn3rzs"
  exit 0
fi }

echo " o installing plugins.."
chmod +x all-2.0.tar.gz &>/dev/null
/opt/nessus/sbin/nessuscli update all-2.0.tar.gz &>/dev/null

echo " o fetching version number.."
# I have seen this not be correct for the download. Hrm. But, it works for me.
vernum=$(curl https://plugins.nessus.org/v2/plugins.php 2> /dev/null)

echo " o building plugin feed..."
cat > /opt/nessus/var/nessus/plugin_feed_info.inc <<EOF
PLUGIN_SET = "${vernum}";
PLUGIN_FEED = "ProfessionalFeed (Direct)";
PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";
EOF

echo " o protecting files.."
chattr -i /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc &>/dev/null
cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc &>/dev/null

echo " o let's set everything immutable..."
chattr +i /opt/nessus/var/nessus/plugin_feed_info.inc &>/dev/null
chattr +i -R /opt/nessus/lib/nessus/plugins &>/dev/null

echo " o but unsetting key files.."
chattr -i /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc &>/dev/null
chattr -i /opt/nessus/lib/nessus/plugins  &>/dev/null

echo " o starting service.."
rm -r all-2.0.tar.gz &>/dev/null
/bin/systemctl start nessusd.service &>/dev/null

echo " o Let's sleep for another 20 seconds to let the server have time to start!"
sleep 20

echo " o Monitoring Nessus progress. Following line updates every 10 seconds until 100%"
zen=0
while [ $zen -ne 100 ]
do
 statline=`curl -sL -k https://localhost:11127/server/status|awk -F"," -v k="engine_status" '{ gsub(/{|}/,""); for(i=1;i<=NF;i++) { if ( $i ~ k ){printf $i} } }'`
 if [[ $statline != *"engine_status"* ]]; then echo -ne "\n Problem: Nessus server unreachable? Trying again..\n"; fi
 echo -ne "\r $statline"
 if [[ $statline == *"100"* ]]; then zen=100; else sleep 10; fi
done

echo -ne '\n  o Done!\n'
echo

echo "        Access your Nessus:  https://localhost:11127/ (or your VPS IP)"
echo "                             username: admin"
echo "                             password: admin"
echo "                             you can change this any time"
echo

read -p "Press enter to continue"
```

## Run the script

```
┌──(root㉿kali)-[/home/hasanrehni/CyberSecurity360]
└─# bash nessus.sh 
//==============================================================
Nessus 10.5.1 DOWNLOAD, INSTALL, and CRACK -Zen 20230123
special thanks to John Doe for showing this works on Debian
//==============================================================
 o making sure we have prerequisites..
 o stopping old nessusd in case there is one!
 o downloading Nessus..
 o installing Nessus..
 o starting service once FIRST TIME INITIALIZATION (we have to do this)
 o let's allow Nessus time to initalize - we'll give it like 20 seconds...
 o stopping the nessus service..
 o changing nessus settings to Zen preferences (freedom fighter mode)
   listen port: 11127
   theme:       dark
   safe checks: off
   logs:        performance
   updates:     off
   telemetry:   off
 o adding a user you can change this later (u:admin,p:admin)
 o downloading new plugins..
 o installing plugins..
 o fetching version number..
 o building plugin feed...
 o protecting files..
 o let's set everything immutable...
 o but unsetting key files..
 o starting service..
 o Let's sleep for another 20 seconds to let the server have time to start!
 o Monitoring Nessus progress. Following line updates every 10 seconds until 100%
 "engine_status":"progress":35
 "engine_status":"progress":100
  o Done!

        Access your Nessus:  https://localhost:11127/ (or your VPS IP)
                             username: admin
                             password: admin
                             you can change this any time

Press enter to continue                                                                                                                                                                                                                   
┌──(root㉿kali)-[/home/hasanrehni/CyberSecurity360]
```

|Default username and password is admin|
|---|
|![Nessus_login_page](./cybersecurity_img/TheCraftofnetworkingscan/Nessus_loginpage.png)|


## Nessus Usage Tips

### Launching a Scan

To initiate a scan, use the following button:
- **New Scan**

### Scan Templates

Nessus offers various scan templates for your convenience.

### Creating Custom Templates

You can create custom templates through the side menu option:
- **Policies**

Navigate to **New Policy** and select where you want to apply it.

|![NewPolciy](./cybersecurity_img/TheCraftofnetworkingscan/Newpolicy.png)|
|---|


### Modifying Plugin Settings and Creating Custom Rules

For plugin settings and custom rule creation, follow these steps:

1. Go to the menu:
   - **Plugin Rules**

2. Navigate to **Plugin Rule** and click **New Rule** to create rules as needed.

|![NewPlugins](./cybersecurity_img/TheCraftofnetworkingscan/NewPlugins.png)|
|---|



## Identifying Active Hosts with Nessus

### Host Discovery Scan

To easily identify active hosts using Nessus, you can use the **Host Discovery** scan template. This scan type allows you to discover hosts and check open ports, making it one of the most useful scan types.

**How to Launch the Host Discovery Scan:**

|![HostDiscoveryScan](./cybersecurity_img/TheCraftofnetworkingscan/hostDiscoveryScan.png)|
|---|


1. Navigate to **New Scan**.

|![NewDiscoveryScan](./cybersecurity_img/TheCraftofnetworkingscan/Newdiscoveryscan.png)|
|---|

2. Click on **Host Discovery** in the 'Scan Templates' section.

3. On the Basic Tab, fill in the information as required.

4. Click on **Save** to save your scan configuration.

5. Launch the scan.

|![Launchthescan](./cybersecurity_img/TheCraftofnetworkingscan/Launchthescan.png)|
|---|

6. Scanning in Progress

|![ScanningProcess](./cybersecurity_img/TheCraftofnetworkingscan/ScannigProcess.png)|
|---|


**Results of Hosts:**

|![Host Results](./cybersecurity_img/TheCraftofnetworkingscan/hostresults.png)|
|---|

**Results of Host Vulnerabilities:**

|![Vulnerability Results](./cybersecurity_img/TheCraftofnetworkingscan/Vulnerablyhost.png)|
|---|

This Host Discovery scan is an effective way to identify active hosts on your network.