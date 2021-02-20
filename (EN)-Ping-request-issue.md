### Highlevel
1. The ICMP protocol must be enabled into your internet router as well as your Firewall.

2. The router should accept Ping requests (ICMP requests) from WAN port. If it does, you dont have to configure windows firewall.

3. In the case you're not behind a router device, the machine's firewall should be responding to incoming ICMP Requests.

### Troubleshooting
Does https://www.ipaddressguide.com/ping gets 3 responses from your Internet IP address?
It should respond:

PING <internet_ip_address> (<internet_ip_address>) 56(84) bytes of data.  
64 bytes from <internet_ip_address>: icmp_seq=1 ttl=94 time=126 ms  
64 bytes from <internet_ip_address>: icmp_seq=2 ttl=94 time=126 ms   
64 bytes from <internet_ip_address>: icmp_seq=3 ttl=94 time=126 ms  

--- <internet_ip_address> ping statistics ---  
3 packets transmitted, 3 received, 0% packet loss, time 2003ms  
rtt min/avg/max/mdev = 126.280/126.479/126.846/0.259 ms  

If not, then there is a firewall rule within the computer and/or the router.

(3rd party firewall? antivirus?)
You should read your software manual regarding this issue. We will cover only windows firewall in this how to.

## Windows firewall: How to Allow ICMP Requests:

Goto Control Panel, System & Security, Windows Firewall.
Select Advanced settings, choose Inbound Rules in left pane.  
Click Inbound Rules, scroll down until you find **File and Printer Sharing (Echo Request - ICMPv4-In)** rule.  
Right click-> Properties  
on **General** tab:  
under General category check **Enable**  
Under Action select **Allow the connection**  
Apply changes.  

switch to **Scope** tab
under Remote IP Address click add  
select **Prefefined set of Computers** and select **Internet**  
click Ok then Apply and Ok  

## Routers: Allow WAN Ping.  

Usually routers have an option under admin pages that can be turned on or off for this option.
D-Link routers have removed the option, on some models, Allow WAN ping from administrative page.  
An walkaround is to enable Virtual Server and point it to your computer IP address.  
Under protocol type you should be able to manually write the protocol number which for ICMP is 1.