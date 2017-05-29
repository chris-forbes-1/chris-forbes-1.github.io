---
layout: post
title:  "Checking remote ports using python"
date:   2017-05-29
excerpt: "Overeager admins will sometimes remove telnet from remote linux servers, this script lets you check remote ports without telnet installed"
tag:
- python
- networking
- linux
- script
comments: true
---
Every now and then whilst setting up a new server for the first time I find myself having to check whether or not the new server can reach our app/db server. 
Depending on who has set it up, there is at least a 10% chance the admin has remote tools ```telnet``` or ```nc``` so after a little reading I came up with a handy little python
scripts using tools which cannot be removed from a linux server: Python

```python 
import socket
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

sock.connect_ex(('<remote address>>, <port>))

```


This will log a "0" in to your console if the remote port is open, quite handy no?

You can look up any other error codes from [here](http://www.ioplex.com/~miallen/errcmpp.html)