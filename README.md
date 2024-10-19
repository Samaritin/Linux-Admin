# Linux Admin

**Overview:** This lab focused on managing and configuring Linux services and applying firewall rules to secure a system.

**Skills Developed:** Linux service management (Figlet, Lighttpd), firewall setup, and configuration for service security.

**Tools Used:** Figlet, Lighttpd, Firewall rules.

---

**Lab Details**

Introduction
Administrative privileges in the Linux distribution are the ability to make major changes to the system. This is can be the operating system, downloading software to the system, and allowing who has access to files within the system as well. This lab will allow the introduction of what administrative privileges can do. 


Results and Analysis
To begin this lab, the individual will start by installing the figlet banner maker. This software package allows the user to create large characters. The user will use the ‘sudo apt-get install figlet’ command. Utilizing the ‘sudo’ command will allow the user to escalate the command into the root or admin privilege. If the user does not use the ‘sudo’ command the output will result in a ‘permissions denied’. Therefore, the user does not have authorization to make changes to the system. There are some packages and software where typing in ‘sudo’ will not always just be enough but the user will need to type in the root password for further authentication to allow the changes to be made to the distribution. Although, figlet is not one of those packages just utilizing the ‘sudo’ command itself will install the package. The figure below will show the installation. 
Figure 1: figlet installation 

![image](https://github.com/user-attachments/assets/628e6d0f-d79d-4f55-8208-69256873c88f)


Next the user will use the figlet software to type out the name or initials. Using the command ‘figlet -c JakeLB’ will display the banner in the center of the terminal with the examiners name and part of the last name. The figure below will display the results. 
Figure 2: Banner of name 

![image](https://github.com/user-attachments/assets/b639dfe2-7416-4a32-b42d-9eb33f08d254)


Next the user will use the ‘sudo’ command to remove the figlet package. This command can be utilized for other packages as well. However, again the user may have to type in the designated password for further authentication to remove the software from the Linux distribution. 
Figure 3: Uninstallation of figlet 

![image](https://github.com/user-attachments/assets/32c8c8b0-0f2a-49ac-bef3-876425894623)


The next step in the lab is to use the previous commands. However, these commands will be to install the software lighttpd. Once it is installed using the command ‘sudo apt-get install lighttpd’. To start lighttpd the user will then use the command ‘systemctl start lighttpd’ then the user will have to enable the software by entering ‘systemctl enable lighttpd’. It is good to check the status of the package to make sure it is running. The user can do this by entering ‘systemctl status lighttpd’ and it will display an active(running) message in green to show the user that lighttpd is running.  Once the user knows lighttpd is running, the user can take the IP address of the ubuntu machine and type that into the web browser of their choice into the Kali Linux machine. The default placeholder should display in the web browser of the Kali Linux machine which is shown in Figure 4 below. 
Figure 4: Lighttpd default web browser 

![image](https://github.com/user-attachments/assets/3fed7f16-81eb-4704-bed1-cd6c0c3ebae5)


The next step is to run the placeholder on a different port. In this case the port 443 was used. To change the port the user must go into the configuration of lighttpd and set the port to something different other than 80. To change this the user will run ‘sudo (nano or vim depending on choice) /etc/lighttpd/lighttpd.conf’. Below in Figure 5 is displayed where to change the port number in the configuration. 


Figure 5: Changing port of default page 

![image](https://github.com/user-attachments/assets/ea6f3e96-cc40-4c54-ac38-692d13ac6b11)


Once the port number has been changed in the configuration, the individual will use the same steps to see the default page in the web browser as before. It is good to close out of the previous browser used from before to make sure that the display does not result in an error. The user will type in the same IP address as the other machine and the default page for lighttpd will appear. 
Next the user will not allow access to port 80 using the uncomplicated firewall(UFW) dependency. The user can see what applications the ufw is currently linked to by running ‘sudo ufw app list’. To see further information about one of the applications the user can run sudo ufw app info ‘Lighttpd HTTP/S’ this will tell the user what port and protocols the app is running. If this is the port and protocol the individual wishes to deny the user will use the ufw rule set that’s implemented into the program by running ‘sudo ufw deny ‘Lighttpd HTTP’ and ‘sudo ufw deny ‘Lighttpd Full’. This is because both rule sets for the server use port 80. Therefore, we want to use the firewall to close off any access to port 80 and filter all traffic to the ports we want. Additionally, to further make sure the port is not used the user can run ‘sudo ufw deny 80’ and the port will be denied by the firewall completely. The screenshot below shows the rule set for the firewall and the status of the rules. 
Figure 6: UFW rule sets 

![image](https://github.com/user-attachments/assets/85043e07-a9bf-4a37-91ee-a6f787a79db8)


Then if the user wants to allow traffic by this port with the web server. The user will have to utilize the ‘sudo ufw allow’ command. The user will have to change each one of these rules that says deny and make the action state ‘ALLOW’. The screenshot below will display the ufw allowing all traffic on port 80. 
Figure 7: UFW allowing all traffic 

![image](https://github.com/user-attachments/assets/3bb32ce1-2305-46b6-b58b-6bbe3ed27859)



Conclusion
These are the basic introduction to administrative privileges that cyber professionals would utilize. The use of firewalls is essential to cyber professionals and filtering traffic to specific ports for monitoring of malware and attacks on the servers. This makes intrusion detection and prevention much easier for the software and the individual monitoring the traffic. Using basic administrative commands such as sudo apt-get at the beginning of the lab is a must for any cyber professional and being able to update programs due to the evitable changes that come in this industry. These are just introductory steps and can be further examined at a much deeper depth. 

