---
title: Network Scanner(Scandy) - Python
description: A tool to scan a network for open ports, manufacturer of discovered devices and checking for already known vulnerabilities for those discovered devices and/or services
image: https://okdsmchimpofxigqckfu.supabase.co/storage/v1/object/public/assets/images/scandy.webp
author: 'Andrews Boateng Okyere'
publishedAt: 27/08/2023
---

## Introduction
In this project, I used scapy a popular network library of python to create a tool to scan any authorized network for open ports and savage other information such as manufacturer based on the MAC address, os, etc. And the tool also used an api by [vulners](https://vulners.com/) to scan for any CVE's out there based on the deduced information.
> Every pentester is as good as their information gathering skills - Andrews

### Features
- Scan network for connected(active) devices. 
 - Retrieve information such as Mac address, OS, Host name,
 - Scan for open ports, port services, port banner and additional vulnerabilities.
 - Search for existing CVE for open ports using [Vulners API](https://vulners.com) 

All codes used can be found at [cybandy](https://github.com/cybandy/scandy) repo. You can choose to dive right in get your hands dirty or follow along with the youtube videos I have. Either way happy learning and hope to get your feedbacks.

## Detailed explanation : Videos
::sub-section-listing

::

## Usage
### Installation

#### Caution
Because scapy interact directly with the raw socket of your system it requires sudo priveledges. You can directly call sudo as I have shown below or follow the explanation [here](http://https://github.com/Forescout/project-memoria-detector/issues/6 "here") to tweak it as you want it.

Clone the repo
```sh
git clone https://github.com/cybandy/scandy.git
```

Create a virtual environment
```sh
python -m venv venv #use any name you want
```
Activate the environment
```sh
source ./venv/bin/activate
```
Install the packages
```sh
pip install -r requirements.txt
```
### Commands

|   Commands    	   |     Description         	      |
|:-----------------:|:------------------------------:|
| -t or --target 	  |    Target network ip      	    |
|  -p or --port  	  |    port(s) to scan       	     |
| -th or --thread 	 | Number of thread. Default 50 	 |
| -v or --verbose 	 |  Print all closed ports    	   |

The command below will check if the IP can be reached and then scan default ports 1-1024
```sh
sudo python -t 192.168.227.3
```

The command below will check if the IP can be reached and then scan default port 22, 80, 221
```sh
sudo python -t 192.168.227.3 -p 80 22 221
```

The command below will check for all the device on the network 192.168.227.1/28 can be reached and then scan default port 22, 80, 221 and ports in the range of 2000 - 5000
```sh
sudo python -t 192.168.227.1/28 -p 80 22 221 -pr 2000 5000
```
