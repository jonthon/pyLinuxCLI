# PyLinuxCLI

DESCRIPTION:
-----------

This module implements low level Linux CLI. It uses ```pty``` and ```socket``` low level interfaces. There are two versions of CLI in 
this module: local (```startlocalterminal```) and remote (```StartTerminalServer``` and ```StartSocketTerminal```). It only works on 
Linux systems that have IO blocking support. 

This module's remote CLI is ideal for portability use. Run server interface on remote machine, and start client interface on desired 
device (ie. laptop, phone (with termux app), tablet (with termux app), etc).


USAGE:
-----

To start the local CLI, call ```startlocalterminal``` and pass in prog name (ie. bash, sh, python3, etc). To start remote CLI first call 
```StartTerminalServer``` on a server machine, then call ```StartSocketTerminal``` on client device. Pass hostname ('' on server) and 
port number to both server and client terminal interfaces. Also, optionally pass prog name on client terminal interface (default is 
```sh```). 

Since terminal interfaces in this module are low level and from scratch, the output is raw. ```localoutput``` function can be customized 
to filter out the prog input that reappears in the prog output.


EXAMPLES:
--------
- Local CLI:

```
jon@jons-linux:~$ python3 pylinuxcli.py
$ date
date
Fri 09 Jun 2023 04:38:26 PM EDT
$ 

$ cal 
cal 
     June 2023        
Su Mo Tu We Th Fr Sa  
             1  2  3  
 4  5  6  7  8  9 10  
11 12 13 14 15 16 17  
18 19 20 21 22 23 24  
25 26 27 28 29 30     
                      
$        
```
