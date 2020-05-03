# Highlevel

The ports need to be opened on your internet router as well as your Firewall. The router should point to your machine. The machine's firewall should be allowing *incoming connection to Docker*, at least for the port range 31400-31409.

# Troubleshooting

**Does [http://127.0.0.1:31400](http://127.0.0.1:31400) work locally for you?**
It should respond "OK FROM PORT 31400". If not, then there is a problem within the computer and not the router. Either the port listener docker container is not running, or some firewall is blocking your port. 

**Test if your computer ports are open using external tools.** 
E.g. [yougetsignal.com/tools/open-ports/](http://yougetsignal.com/tools/open-ports/) and placing port 31400 in the port field

**Find your external IP address here** [yougetsignal.com/tools/open-ports/](http://yougetsignal.com/tools/open-ports/) 
Try visiting Your external IP address followed by :31400 on your browser to see if you get a response. For example http://123.45.67.89:31400 (but place your IP in the numbers)