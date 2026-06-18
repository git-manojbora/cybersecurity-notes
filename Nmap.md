# Nmap Notes

## What is Nmap?

Nmap (Network Mapper) is a network scanning tool used to discover hosts, open ports, services, and gather information about a target system.
It is widely used by network administrators and penetration testers.

## Host Discovery

Host discovery is used to find which devices are alive on a network.

### ICMP Scan

nmap -sn 192.168.1.0/24

* Performs host discovery only.
* No port scanning is done.
* Used to find active devices on a network.

### ARP Scan

nmap -sn -PR 192.168.1.0/24

* Uses ARP requests for host discovery.
* Works only on the local LAN.
* More reliable on the same subnet.

## Basic Port Scan

nmap 192.168.1.1

*Scans the top 1000 most common ports of the target.

## Service Version Detection

nmap -sV 192.168.1.1

*Used to identify the running services and their versions.

Example:
* Apache 2.4
* OpenSSH 9.0
* MySQL 8.0

## Operating System Detection

nmap -O 192.168.1.1

*Attempts to identify the operating system running on the target machine.

## Aggressive Scan

nmap -A 192.168.1.1

Performs:

* OS detection
* Version detection
* Script scanning
* Traceroute

## Scan Specific Ports

nmap -p 22,80,443 192.168.1.1

*Scans only ports 22, 80, and 443.

## Scan All Ports

nmap -p- 192.168.1.1

*Scans all 65535 ports.

## Save Output to a File

nmap -oN result.txt 192.168.1.1

Saves the scan results in normal format.

## Useful Flags

 Flag - Purpose                   
 -----    ------------------------- 
 = -sn    -Host discovery only       
 = -sV    -Service version detection 
 = -O     -OS detection              
 = -A     -Aggressive scan           
 = -p     -Scan specific ports       
 = -p-    -Scan all ports            
 = -oN    -Save output to a file     


### Note

Always perform scans only on systems or networks that you own or have explicit permission to test OR 
you can perform in -[  scanme.nmap.org ] 
