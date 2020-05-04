This tutorial is for people that knows their **IPv4 address**, routers **LAN IP** and are using **Zyxel NGB6515** router (not sure about other Zyxel routers, maybe they have the same interface).

In your browser search type in your router's LAN IP and press enter.

![](https://i.imgur.com/AN58wiU.png)

**Log-in** to your router using pre-configured **router password** that is located on the other side of the router (under it) or existing one (if you have changed it).

![](https://i.imgur.com/sFIbgH4.png)

Navigate to **Expert Mode**

![](https://i.imgur.com/4IceNaR.png)

On the left side of Expert Mode search for **Configuration** tab and click on it.

![](https://i.imgur.com/Dwk0vpN.png)

Under the **Configuration** tab search for **NAT** and click on it.

![](https://i.imgur.com/i81GmAH.png)

Once **NAT** option is opened navigate to **Application**

![](https://i.imgur.com/Rs42aUT.png)

Here you can add rules to open ports.

1. Thick **Active**
2. **Service name:** theNameOfThisRule
3. **Port:** use drop down and select TCP and to the right add the port you want to open (ex. 31400)
4. **Server IP Address:** your IPv4 address
5. On the **bottom** of the window you will see two buttons - **Apply** and **Reset**, click on **Apply**

Congratulations, you have successfully opened a port, now you have to do that for all 10 ports that are required by Pi Node.

![](https://i.imgur.com/IrbexQ2.png)

**Don't forget that you will have to add rules to Windows Defender as well (for each port)!**

Hopefully this helped!