
## NodeJS

Download and install nodejs from
https://nodejs.org/en/download/

(windows installer msi)

(you don't need the chocolatey addon option) 

## Create file
In explorer navigate to c:\users\yourname
on the view tab, tick "file name extensions"

on the home tab, "new item", text document
change the name to ports.js 

## Edit File

open notepad, open ports.js
paste the code from this page 

https://nodejs.org/en/docs/guides/getting-started-guide/

change hostname for internal ip of your computer

change port for 31400 

## Run Server
open command prompt
go to c:\users\yourname

`C:\users\yourname> node ports.js`

it should say server running at ......  then information you changed.

## Test Server Inside your computer

In a web browser go to http://ipaddressfromabove:31400

If you get the page hello world, the server is working. 

## Test Server Inside your network

With another computer or mobile phone in your house on your wifiyou can run an intermediate test

In a web browser go to http://ipaddressfromabove:31400

If you get the page hello world, the port is open and working inside your network at least.

 
## Test Server outside your network

Find your external ip at https://www.whatsmyip.org/

Go to this website https://hidester.com/proxy/

Type in the  address http://ipaddress-from-whatsmyip:31400

If you get the hello world page, your port forwarding is working from the outside world. 


 
