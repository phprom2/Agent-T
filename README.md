
# Agent-T
Write-Up of Agent T room : https://tryhackme.com/room/agentt

First, we scan the machine with nmap :

<a href="https://imgbb.com/"><img src="https://i.ibb.co/S5MSZJK/Screenshot-2023-08-23-15-09-44.png" alt="Screenshot-2023-08-23-15-09-44" border="0"></a>

Only one port is open and we can see an interesting thing, the version of php : __8.1.0-dev__
The room had CVE in theses tags, so we can search on the web if someone of them exist for this version.

Great : 

<a href="https://ibb.co/RgLVJxS"><img src="https://i.ibb.co/NFwHG83/Screenshot-2023-08-23-15-12-18.png" alt="Screenshot-2023-08-23-15-12-18" border="0"></a>

Now we search the exploit with __searchsploit -m "code"__
The script is copied in our directory.
Now we launch it :

<a href="https://imgbb.com/"><img src="https://i.ibb.co/qCJxvPd/Screenshot-2023-08-23-15-34-58.png" alt="Screenshot-2023-08-23-15-34-58" border="0"></a>

Now we have an root acces to the machine but we can't navigate like we want in the machine.

Since 1H im trying to setup a reverse shell without success, so i found a python script exploiting the RCE and doing it for we : https://github.com/flast101/php-8.1.0-dev-backdoor-rce.git

Launch it and don't forget to setup your listener :

<a href="https://imgbb.com/"><img src="https://i.ibb.co/Vv7MBzL/Screenshot-2023-08-23-15-36-51.png" alt="Screenshot-2023-08-23-15-36-51" border="0"></a>

We have the reverse shell :

<a href="https://imgbb.com/"><img src="https://i.ibb.co/0Y88PRH/Screenshot-2023-08-23-15-37-17.png" alt="Screenshot-2023-08-23-15-37-17" border="0"></a>

And we can grab the flag :

<a href="https://imgbb.com/"><img src="https://i.ibb.co/x5SDj5z/Screenshot-2023-08-23-15-38-45.png" alt="Screenshot-2023-08-23-15-38-45" border="0"></a>

Thanks for reading ;).
