---
title: Working With Wireguard
categories: [tutorials]
tags: [vpn,linux,opensource]
---

![Alt Text](/assets/img/Working-With-Wireguard.png)

# What Is Wireguard

Wireguard is a remote access VPN that allows you to connect to a private network from anywhere.

# Setting A Static IP

Setting a static IP will ensure that the sever is accessible at all times. To set a static IP, issue the following command:

```bash
sudo nmcli con add type ethernet con-name Wired1 ifname enp5s0 ipv4.method manual ip4 x.x.x.x gw4 x.x.x.x ipv4.dns 1.1.1.1
```

# Creating DDNS With NoIP

Before you install Wireguard, you need to create a hostname with NoIP.Creating a Dynamic DNS will ensure that even if your public IP changes, DDNS will automatically update it.Here is how you create a DDNS with NoIP:

1) Create an account
2) Click on Dynamic DNS on the left hand side
3) Click on NO-IP Hostnames
4) Create hostname
5) Add hostname and choose a domain

# Installing Wireguard With PIVPN

To install Wireguard, issue the following command:

```bash
curl -L https://install.pivpn.io | bash
```

This will run you through the configuration setup. The default port Wireguard listens on is 51820 but you can use whichever port number you wish. Ensure that you select public DNS and enter the DDNS hostname you cretaed.

# Allowing Port Forwarding

You need to allow port forwarding on UDP 51820 or the custom port number that you set. Make sure you consult your routers manual as every router is different.

# Creating Clients

To create a client, issue the following command:

```bash
pivpn add
```
Enter the client's name. A configuration file will be generated and stored in the configs directory within your home directory. 

# Installing Wireguard On The Client Machine

To install Wireguard, issue the following command:

```bash
sudo apt install wireguard
```

# Transfering The Configuration File To The Client

To transfer the configuration file to the client, issue the following command:

```bash
sudo rsync ~/configs/client.conf cortizaldana@x.x.x.x:/etc/wireguard/
```

# Activating VPN Connection

To activate the VPN connection, issue the following command:

```bash
sudo wg-quick up client
```
# Conclusion

Wireguard is a fast and reliable VPN tunnel that allows you to connect to a private network. PIVPN is a quick way to install Wireguard and it is very simple to use. You can generate a QR code and scan it with the Wireguard app. If you run into issues, you can debug it by using the --debug option with the pivpn command.