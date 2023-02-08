---
title: Working With Cockpit
categories: [tutorials]
tags: [monitoring,linux,opensource]
---

![Alt Text](/assets/img/Working-With-Cockpit%20.png)

# What Is Cockpit

Cockpit is a open source monitoring tool available in many distributions. This tool allows you to monitor different aspects of your Linux system. Cockpit is accessible through the web browser and it has a very nice simple user interface. 

![Alt Text](/assets/img/Cockpit.png)

For more information, visit https://cockpit-project.org/.

# Installing Cockpit

To install Cockpit, issue the following command:

```bash
sudo apt install cockpit cockpit-machines
```

If you are using RHEL based distributions, use YUM or DNF utility like so:

```bash
sudo yum install cockpit cockpit-machine

sudo dnf install cockpit cockpit-machines
```

# Starting & Enabling Cockpit

Once the packages are installed, we need to enable and start the Cockpit service. To do that, issue the following commands:

```bash
sudo systemctl enable cockpit

sudo systemctl start cockpit
```

# Firewall Setup

We need to allow communication to tcp/9090. To do so, issue the following command:

```bash
sudo ufw allow 9090/tcp
```

If you are using firewalld, issue the following command:

```bash
sudo firewall-cmd --permanent --add-service=cockpit

or

sudo firewall-cmd --permanent --add-port=9090/tcp
```

# Accessing Cockpit

To access cockpit, open your web browser and type in your IP address along with the port number that cockpit is listening on:

```bash
https://X.X.X.X:9090
```
# Conclusion 

It is important as a Linux administrator to monitor Linux systems on a daily basis. With Cockpit you will be able to manage storage, networking, and system updates. You will also be able to manage virtual machines and containers. With that being said, this concludes the installation of Cockpit.
