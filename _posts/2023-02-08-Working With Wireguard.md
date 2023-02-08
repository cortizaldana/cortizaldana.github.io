---
title: Working With Wireguard
categories: [tutorials]
tags: [vpn,linux,opensource]
---

![Alt Text](/assets/img/Working-With-Wireguard.png)

# What Is Wireguard

# Setting A Static IP

# Installing Wireguard With PIVPN

To install Wireguard, issue the following command:

```bash
curl -L https://install.pivpn.io | bash
```

This will run you through the configuration set up. Be sure to pause when it displays whether you want to use a public IP or public DNS and continue with the next step.

# Creating DDNS With NoIP

Creating a Dynamic DNS will ensure that even if your public IP changes, DDNS will automatically update it. This mean if you use your public IP instead, you would have to update your configuartion everytime the public IP changes. Here is how you create a DDNS with NoIP:

1) Create an account
2) Click on Dynamic DNS on the left hand side
3) Click on NO-IP Hostnames
4) Create hostname
5) Add hostname and choose a domain

# Continuing Configuartion Setup

Once you've created a DDNS, add it to the configuration. After that continue going through the set up.

# Allowing Port Forwarding

# Creating Clients

To create a client, issue the following command:

```bash
pivpn add
```

# Transfering The Configuration File To The Client

# Activating VPN Connection

To activate the VPN connection, issue the following command:

```bash
wg-quick up client
```
