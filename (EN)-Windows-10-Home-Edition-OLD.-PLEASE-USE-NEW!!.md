This guide only applies for **Windows 10 Home Edition**.

In this guide, we will install and setup all the necessary programs and settings for running a Pi Node. For Windows 10 Home Edition, you will need to install Docker Toolbox **not** Docker Desktop.

Virtualization does **not** need to be enabled for Windows 10 Home Edition users. Do **not** enable virtualization in your BIOS. If you already have, un-do it. If you don't know what I'm talking about, good. Don't worry about it.

The community will continue to update these guides as we learn better how to streamline this process. In the meantime, if the directions aren't clear, a basic Google search may help.

# STEP 1
You need to assign your PC a local static IP using your router and forward ports 31400-31409 to it. I can't say how to do this for your specific router, but searching 
[Port Forward](https://www.portforward.com "Port Forward") is a place to start.

# STEP 2
You also need to create rules in Windows Defender Firewall. You want an inbound and outbound rule allowing traffic on TCP for 31400-31409 for Public, Private, and Domain networks (at least that's what I did).

Right-click on your network icon (WiFi or Ethernet plug icon, in the bottom right) and select "Open Network & Internet settings". Look for and click "Windows Firewall" (towards the bottom middle of the screen that popped up).

On the new screen that popped up, select "Advanced settings". You'll need administrator rights on your computer to do this, and a little box will pop up. You'll need to hit "Yes" to continue.

Yet another window will pop up, this one called "Windows Defender Firewall with Advanced Security". Click on "Inbound Rules" toward the top left. Then click "New Rule..." toward the top right. Select "Port" then "Next" then "TCP" (should be the default) then "Specific local ports:". In the field to the right, type in ```31400-31409```, then "Next". Select "Allow the connection" (the default), then "Next", then check "Domain", "Private", and "Public" before hitting "Next" again. Type in a name like "pi node ports" and a description if you like, then "Finish".

Repeat the steps above, except click "Outbound Rules". Note that "Block the connection" is the default and should be changed to "Allow the connection" just like above.

# STEP 3
Install **Docker Toolbox**. There is a link provided in the Pi Node app, or use this one: <https://github.com/bonkonauts/cors-anywhere/releases/download/v0.1.9/AppSetup.zip>. You don't have to "Help Docker improve Toolbox" (just un-check it) but make sure you include "Docker Compose for Windows", "VirtualBox", and "Kitematic for Windows (Alpha)". When installation completes, you should have 3 icons on your Desktop for Docker Quickstart Terminal, Oracle VM VirtualBox, and Kitematic.

*A quick explanation of the icons:*
Docker Toolbox installs Docker, a Linux-based software for running applications in a "container". The "container" safely stores these programs away from the rest of your computer. Docker Toolbox also installs Oracle VM VirtualBox. Kitematic uses this to create a Linux VM (virtual machine) to run Docker inside of.

Windows 10 Home Edition, or at least my PC, does not support Hyper-V, the default Docker virtualization.

When launching Docker the first time from Docker Quickstart Terminal, I got an error about vt-x/amd-x being disabled.

To fix this, you need to edit with Notepad C:\Program Files\Docker Toolbox\start.sh and change the line:
```"${DOCKER_MACHINE}" create -d virtualbox $PROXY_ENV "${VM}"```
to
```"${DOCKER_MACHINE}" create -d virtualbox --virtualbox-no-vtx-check $PROXY_ENV "${VM}"```

Run Docker Quickstart Terminal to ensure there are no errors.

# STEP 4
You should now open Kitematic, which also installed with Docker. It will create the Linux VM. This is more or less the daemon that is referenced in the Pi Node app. If Kitematic is running, the Linux VM will be running and little instances of Docker will be running too (visible in Task Manager).

You do not need to sign up or log in for Kitematic to successfully create the VM.

# STEP 5
The Linux VM cannot reach the Internet by default. To fix this, open Oracle VM VirtualBox.

Right-click the "default" machine (which was created by Kitematic and should be running) and click Settings.

Click Network and it should default to Adapter 1 which is attached to NAT.

Click Advanced and then Port Forwarding.

Click the green + to add a rule. On the new rule, change Host Port to 31400 and Guest Port to 31400.
**Don't change any other values.**

Add an additional rule for each of the ports 31400-31409.

Click Ok, Ok, and then Close Oracle VM VirtualBox.

You can verify that your ports are forwarding correctly by using a tool like this one: <https://www.yougetsignal.com/tools/open-ports/>
The first field will automatically fill in with your external IP address (if you've ever wondered what it was). Put the single port you want to check in the second field (one within 31400-31409 in this case). Then hit "Check".

*Note: A port will appear closed if nothing is listening on that port. Pi Node should be running to check.*

#STEP 6
Open the Pi Network Node app now. Go to Node, Continue, and check that it can see Docker, the daemon, and check the ports are open.
*Sometimes it gets stuck trying to check ports and you have to click "Check now" multiple times.*

# Additional Comments
If at any time you get errors from Kitematic or Oracle VM Virtual Box, make sure all instances of docker, Pi Network, VBoxHeadless, VBoxNetDHCP, and VirtualBox Interface have been closed from Task Manager before restarting Kitematic (and Oracle VM Virtual Box if on that step). Or just restart your computer.

*This is free advice for my fellow Pi Network pioneers. I am in no way responsible for what you do with this advice. I am in no way liable if this causes some sort of network security risk or any other sort of issue.*