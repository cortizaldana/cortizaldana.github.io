---
title: Installing Cockpit With Virtual Machine Support
categories: [home lab]
tags: [server,linux]
---

![Alt Text](/assets/img/Working-With-Cockpit%20.png)

# What Is Cockpit



# Installing Cockpit

To install cockpit issue,

```bash
sudo apt install cockpit cockpit-machines
```

## Starting & enabling Cockpit

```bash
sudo systemctl enable cockpit
sudo systemctl start cockpit
```

## Firewall setup

Allow port 9090/tcp

```bash
sudo ufw allow 9090/tcp
```

## Accessing Cockpit

