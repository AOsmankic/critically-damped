<h1>AirCrack</h1>

## Summary
Aircrack-ng is a suite of tools that help assess WiFi network Security. It allows you to monitor your wireless traffic aswell as crack keys for WEP and WPA WiFi protocols.

## Requirements
* Since this is a tool for wireless networks, it requires a wireless network card that can enter monitoring mode (pineapple)
* Computer
* Aircrack-ng installation


## Tools
#### airmon-ng 
Tool for monitoring on the network interface

Usage: `airmon-ng`
Description: Identify wireless cards available to the system
Expected output: 

Usage: `airmon-ng start {NIC}`
Description: Start monitoring on interface {NIC}


#### airodump-ng
Tool for capturing wireless frames

Usage: `airodump-ng {NIC}`
Description: List networks available to the network card {NIC}

#### aireplay-ng
Tool for injecting and replaying network frames (packets)

#### aircrack-ng
The primary cracking tool used to crack keys


 Usage: `aircrack-ng {cap_file}`
 Description: attempt to crack the key in the given cap file. Useful for WEP

 Usage: `aircrack-ng -w {wordlist} {cap_file} -e {SSID}`
 Description: attempt to crack the password for the given {cap_file} by supplying a {wordlist} and the network {SSID}. Useful for WPA2-PSK


 



## Tags

Tag Name | Tag Value
-------- | --------
Classification | Attack, Monitoring, Cracking
Cost | Free
Type | Open Source
Compatibility | Linux, Windows
Usage | Terminal
Website | https://www.aircrack-ng.org/


