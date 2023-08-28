---
title: "Your API hacking lab"
description: ""
image: ""
author: 'Andrews Boateng Okyere'
publishedAt: "29/08/2023"
tags: "api, apisec, hacking lab"
---

::cy-sources
---
items: [
    {
label: "APIsec University",
    to:  "https://university.apisec.ai"
}
]
---
::

## Introduction
This section of the course introduced the setup of the vulnerable applications [crapi](crapi.apisec.ai) and [vapi](vapi.apisec.ai). It also talked about other sources such as thm and htb where students should practice and test their skills gained in the course

## crAPI Installation
```sh
mkdir ~/lab && cd ~/lab
sudo curl -o docker-compose.yml https://raw.githubusercontent.com/OWASP/crAPI/main/deploy/docker/docker-compose.yml
```
```sh
sudo docker-compose pull
sudo docker-compose -f docker-compose.yml --compatibility up -d
```
If no error occurred, crapi should available on [http://127.0.0.1:8888](http://127.0.0.1:8888/)

## vAPI Installation
```sh
cd ~/lab
```
```sh
sudo git clone https://github.com/roottusk/vapi.git
cd ./vapi
```
```sh
sudo docker-compose up -d
```
vAPI will also be accessible at [http://127.0.0.1/vapi](http://127.0.0.1/vapi) and comes with a pre-built postman collection and environment located in vAPI/postman directory

