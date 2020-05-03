_**Windows firewall: How to open Ports:**_

- Goto Control Panel, System & Security, Windows Firewall.

- Select Advanced settings, choose Inbound Rules in left pane.

- Right click Inbound Rules, select New Rule.

- Add TCP, "31400-31409" & click Next.

- Select "Allow the connection" in next window, choose Next.

- Select the network type & choose Next.

- Name it "Pi Network" & click Finish.


_**Checking if the ports are open or listening:**_

- Open the Command Prompt under Windows. (https://www.howtogeek.com/235101/10-ways-to-open-the-command-prompt-in-windows-10/)

- Type in "**netstat -aon**" or "netstat -aon | findstr 3140"

- Check if the ports 31400 until 31409 are "listening".