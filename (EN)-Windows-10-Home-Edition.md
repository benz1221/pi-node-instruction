This guide only applies for **Windows 10 Home Edition**.

In this guide, we will install and setup all the necessary programs and settings for running a Pi Node. For Windows 10 Home Edition, you will need to install Docker Toolbox **not** Docker Desktop.

Virtualization does **not** need to be enabled for Windows 10 Home Edition users. Do **not** enable virtualization in your BIOS. If you already have, un-do it. If you don't know what I'm talking about, good. Don't worry about it.

The community will continue to update these guides as we learn better how to streamline this process. In the meantime, if the directions aren't clear, a basic Google search may help.

# STEP 1
You need to assign your PC a local static IP using your router and forward ports 31400-31409 to it. I can't say how to do this for your specific router, but searching 
(https://www.portforward.com "Port Forward") is a place to start.

# STEP 2
You also need to create rules in Windows Defender Firewall. You want an inbound and outbound rule allowing traffic on TCP (and probably UDP too) for 31400-31409 for Public, Private, and Domain networks (at least that's what I did).

# STEP 3
Install **Docker Toolbox**. There is a link provided in the Pi Node app, or use this one: (https://github.com/docker/toolbox/releases/download/v19.03.1/DockerToolbox-19.03.1.exe). Make sure you check to include all the options. When installation completes, you should have 3 icons on your Desktop for Docker Quickstart Terminal, Oracle VM VirtualBox, and Kitematic.

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

#STEP 6
Open the Pi Network Node app now. Go to Node, Continue, and check that it can see Docker, the daemon, and check the ports are open.
*Sometimes it gets stuck trying to check ports and you have to click "Check now" multiple times.*

# Additional Comments
If at any time you get errors from Kitematic or Oracle VM Virtual Box, make sure all instances of docker, Pi Network, VBoxHeadless, VBoxNetDHCP, and VirtualBox Interface have been closed from Task Manager before restarting Kitematic (and Oracle VM Virtual Box if on that step). Or just restart your computer.

*This is free advice for my fellow Pi Network pioneers. I am in no way responsible for what you do with this advice. I am in no way liable if this causes some sort of network security risk or any other sort of issue.*