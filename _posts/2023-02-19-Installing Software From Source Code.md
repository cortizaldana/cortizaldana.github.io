---
title: Installing Software From Source
categories: [tutorials]
tags: [sourcecode,linux,opensource,software]
---

![Alt Text](/assets/img/Installing-Software-From-Source-Code.png)

# Software Source Code

In the modern world, we normally install software from our local repositories. These repositories contain software that is already compiled. They're times where we would like to install software downloaded from the internet. These are given to us via tar ball packages. It is not recommended to install software from source unless you know it comes from a trusted source.

# Requirements For Installing Software Source Code

Before installing source code, you need to verify if you have compiler tools. Almost all Linux distros have them installed but it won't hurt to double check. Issue the following command:

```bash
sudo apt install build-essentials gcc
```
# Extracting The Tar Ball

Right after you download the software, you need to extract the tgz package. To do that, issue the following command:

```bash
tar -xzvf nmap-7.93.tgz
```

Once extracted, go into the folder that was created.

# Installing The Software

We will be using three simple commands to install the software. The ./configure command will just check if you have the proper tools to compile software. The make command will convert the source code into a binary executable file. The make install command will install the software. The following commands will install software from source code,

```bash
./configure

make

make install
```