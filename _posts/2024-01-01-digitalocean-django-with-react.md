---
title: Useful Learnings
author: mbeals
date: 2024-01-01 13:00:00 -0700
categories: [Blogging, First]
tags: [helloworld]
pin: true
math: true
mermaid: true
---

This post is a brain list of thoughts and questions as I work through the DigitalOcean tutorial [How To Build a To-Do application Using Django and React](https://www.digitalocean.com/community/tutorials/build-a-to-do-application-using-django-and-react). This is good practice for me as I learn the basics of Django and React

## Notes

- Useful shell commands:
  - `pipenv shell` starts a virtual environment (creates one if it doesn't exist)
  - `wsl --shutdown` close wsl from command prompt
- Useful django commands:
  - `django-admin startproject FOLDERNAME` creates a new django project in `FOLDERNAME`
  - `python manage.py` is a command-line utility for admin tasks
    - where are these commands stored?
    - `python manage.py startapp TODO` creates new app called `TODO`
    - `python manage.py migrate` performs a migration
      - migrations are a way to systematically make changes to the database (think version control for database changes)
    - `python manage.py runserver` opens a server
    - `python manage.py createsuperuser` creates a superuser
  - What is djangorestframework and django-cors-headers?
    - djangorestframework is a flexible framework for Web APIs
    - django-cors-headers is a security feature that allows communication between different domains (without it, you cannot make requests from a dif domain)
      - by placing `http://localhost:3000` in the whitelist in settings.py, you are allowing it to make requests to you
    - what is a serializer?
      - allows python objects to be converted to a structured data format like JSON or XML which can be transferred between dif systems in the network
      - serializer.py specifies what you want to be serialized
- Useful react commands:
  - npx is a tool for loading remote libraries without downloading them

## Questions

- What is the REST framework?
  - it's an industry standard framework for setting up APIs
  - a request from the client in REST framework contains:
    - a header which may carry an API token/authentication
    - an operation (Post Get Put Delete which are equivalent to CRUD respectively)
    - an endpoint specifiying who it's communicating with
    - parameters/body which may contain more info
  - a response from the server in REST framework contains:
    - JSON data (common format for network communication)
- Why choose Django + React over MERN?
  - Both follow the Model View Controller (MVC) pattern (what's that?)
  - Django is Python backend while MERN is JS backend
  - Django uses relational databases like SQL whereas MongoDB uses noSQL
- What is localhost? What are ports?
  - localhost is an alias for 127.0.0.1 which is the machine you are actively on
  - every machine on a network has an IP address (e.g. 66.94.53.22)
    - IP address indicates geographical location of that machine
    - first part is the network address, second part is host address
      - e.g. 192.168.1.25 --> 192.168.1 is the network address, 25 is the host address
      - host address can range from 0-255 with 3 exceptions:
        - 192.168.1.0 is the network address
        - 192.168.1.255 is the broadcast address (sends info to all devices in network)
        - 192.168.1.1 is typically the router address (see default gateway in ipconfig)
  - every machine has several ports from 0-65535 used for exchanging information. Each port is associated with a specific program
    - ports assigned by IANA (internet assigned number authority)
    - ports 0-1023 are called system or well-known ports
      - 80, 443 used for web pages (HTTP, HTTPS)
      - 25 used for email (SMTP)
      - 21 used for FTP
    - ports 1024-49151 are called user or registered ports that can be registered by companies/devs for a particular service
      - 1102 used for adobe server
      - 1433 user for microsoft SQL server
    - ports 49152-65535 are called dynamic or private ports that are free to use (your computer temporarily assigns iteslf these ports during a session)
    - ports 0-49151 are SERVER SIDE ports (used by server) while 49152-65535 are CLIENT SIDE port (used by client)
  - to see what connections you currently have, you can type `netstat -n` into cmd and display all connections between your machine and others
- What's HTTP vs HTTPS vs FTP?
- updated node from ver 12 to 21 using [n package installed using npm](https://blog.hubspot.com/website/update-node-js)
- local copy of ubuntu is stored under `//wsl.localhost/Ubuntu` in git bash, `\\wsl.localhost\Ubuntu` in windows application
  - the actual location of this in the c directory is `C:\Users\mbeals\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu_79rhkp1fndgsc\LocalState`
- virtual envs stored under `/home/mbeals/.local/share/virtualenvs/` in wsl
