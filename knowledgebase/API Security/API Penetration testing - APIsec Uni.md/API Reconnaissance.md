---
title: 'API Reconnaissance'
description: 'It is the process of gathering information about a target'
image: ''
author: 'Andrews Boateng Okyere'
publishedAt: '29/08/2023'
tags: 'api, reconnaissance'
---
## Introduction
In almost every penetration testing, gathering information about the intended target is the first task to complete. In API pentesting, it is mainly about finding the api endpoint. This can be achieved by digging through documentation on the target website, wayback machine, git repos, etc
Another method is to use the browser developer tools to dig through the network connections to discover api's

### URL Schemes
The common indicators and structure that you have discovered an api.

https://target-name.com/api/v1 

https://api.target-name.com/v1 

https://target-name.com/docs

https://dev.target-name.com/rest

Look for API indicators within directory names like:
/api, /api/v1, /v1, /v2, /v3, /rest, /swagger, /swagger.json, /doc, /docs, /graphql, /graphiql, /altair, /playground

Also, subdomains can also be indicators of web APIs:

api.target-name.com

uat.target-name.com

dev.target-name.com

developer.target-name.com

test.target-name.com