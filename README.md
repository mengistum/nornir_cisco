# Network automation codes - originally written for Cisco switches and routers
Network Automation using Nornir3.0 Automation Framework

SUMMARY: There are two scripts included here. The first script runs show commands on Cisco devices, and save the output to a file. The second script runs configuration changes on Cisco devices. 

WHAT YOU WILL NEED: You can download and use these codes for Cisco IOS XE devices. Here is the list of files you will need:

- devices.txt ==> contians the IP addresses of network equipments you need to SSH to. Please modify it to the correct IP addresses you want to SSH to.

- commands\_show.txt ==> list of show commands you need to run --> One command per line. Please modify it with the correct commands you need to run. I have added all the commands I used when I was checking for Phase-2&3 LAN Upgrade.

- commands\_config.txt ==> list of commands to run in "config t" mode --> One command per line. You can enter "do write memory" to save at the end of the configuration change. As Cisco IOS XE devices do not have "commit", please make sure (quadriple check) your commands are correct.

- config.yaml ==> an inventory list containing info about hosts, groups and defa
ults setup. Do NOT modify!

- myfuncs ==> a package containing functions written by MM. Do NOT modify!

- inventory ==> a folder containing list of yaml files. Do NOT modify!

- nr\_show\_cmds.py ==> a python script to run show commands. Do NOT modify (unless you know what you are doing)!

- nr\_config\_changes.py ==> a python script to perform configuration changes on one or more device(s). Do NOT modify (unless you know what you are doing)!


REQUIREMENTS: This script was written and run using the following: 
		python 3.8.7
		nornir 3.0.0 
		nornir_netmiko 0.1.1 
		nornir_utils 0.1.1
			

USAGE: 
1) If you want it to run on Windows OS, Mac OS, or Linux OS, please install all packages listed under REQUIREMENTS section. And run either "nr\_show\_cmds.py" or "nr\_config\_changes.py" script without the quotation marks. You will be prompted to enter files containing devices and commands (simply press ENTER to use the default files), and enter your SSH username and password.

2) You can also run it on a DOCKER environment. Please pull the container to your docker environment as follows: "docker pull useth2020/nornir-show-diff" without the quotation marks. Then, change directory to /src/Nornir (cd /src/Nornir); modify either commands\_show.txt or commands\_config.txt and devices.txt files; and run "python3 nr\_show\_cmds.py" or "python3 nr\_config\_changes.py" without the quotation marks. You will be prompted to enter files containing devices and commands (simply press ENTER to use the default files), and enter your SSH username and password.


OUTPUT: If you enter correct information, the result will be displayed on the terminal. It is also written to a folder created by the script (name starts with "Nornir-" followed by datetime). When you open the folder, it consists of files with the commands names.
