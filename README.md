# SIEM Lab

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.
- IDS like SecurityOnion and PFsense for firewall

## Steps
## PFSense Firewall
The First step to setting up the virtual network will be creating an enviroment for the firewall, from pfsense's iso, we set the memory to 2gb, and added 5 adapters with their custom preset to VMNet 2-6.

<img width="324" height="295" alt="image" src="https://github.com/user-attachments/assets/f6c187c5-3e80-4fe7-b30a-d874eeea7327" />

After accepting the copyright eula, we can set the WAN and LAN to em0 and em1 respectively. Make sure to accept the following requirements and set it to the latest version of PFSense

<img width="948" height="489" alt="image" src="https://github.com/user-attachments/assets/4140b9e9-4a77-4211-a633-7cbab902a6f6" />

After rebooting pfsense through the menus, we need to assign the adapters we created earlier, we don't need to set up the vlans during the interface assigning and we can do each em in order of their number (em0, em1, em2, etc)

<img width="829" height="472" alt="image" src="https://github.com/user-attachments/assets/deeff709-61ff-4d9d-94be-3f2d6b5194fa" />

We inputted all available options, we go to the second option to assign ip's, we want to set the lan ip to be usable by the kali linux

<img width="678" height="349" alt="image" src="https://github.com/user-attachments/assets/e06f6412-6bb9-423e-a327-28758061f912" />

Now we want to configure OPT1 and give it a Ipv4 address not using the same method with DHCP as before, we do not need to configure ipv6 or anything after.
Do the exact same for OPT2.

<img width="700" height="338" alt="image" src="https://github.com/user-attachments/assets/e949d272-64ee-43ac-b7cc-8eb88854a5e8" />

For OPT4, we want to give it a different port to view, but overall the same requirements as before, I went with 192.168.4.1 in this. For now, we are done setting up pfsense.
<img width="778" height="461" alt="image" src="https://github.com/user-attachments/assets/6bd1aeaa-b1e0-456a-942e-25ed7c18d9d8" />

## SECURITY ONION / UBUNTU

Start by setting up a general Ubuntu Client, open the command line and get the ip from 'ifconfig', take note of the ip. 192.168.117.134
<img width="803" height="71" alt="image" src="https://github.com/user-attachments/assets/d8125d5b-e7e1-4317-b9af-d6383d23a888" />

Install a Security Onion iso, set the storage to 200gb, make sure to give it enough processors, memory and vmnet4, and vmnet5 to be able to connect to the firewall.

<img width="749" height="480" alt="image" src="https://github.com/user-attachments/assets/ffc691c6-be91-4735-8d35-3ec60b68c4b9" />

In the Security Onion setup, we want to set it to evaluation mode and accept the elastic license
Select ens33 with the spacebar and set it to dhcp in direct mode.
<img width="729" height="353" alt="image" src="https://github.com/user-attachments/assets/45c9aa14-2e69-46ea-a70c-e9f4ea0cab93" />

Under ens35, set automatic, accept the defaults, enter an email and select IP.
<img width="1137" height="673" alt="image" src="https://github.com/user-attachments/assets/7cd146ec-bcf7-42f4-99a7-2d9fd2b14c87" />

This is where we can put the IP from Ubuntu to use.
<img width="809" height="353" alt="image" src="https://github.com/user-attachments/assets/17cbdf0e-f5fb-4277-8341-4225e046c55c" />

Find a safe place to store the options list presented as it is important to keeping your SecurityOnion running. 
<img width="660" height="436" alt="image" src="https://github.com/user-attachments/assets/13136d2f-dd94-4a1b-b38b-bf62445739ff" />



























