---
layout: post
title:  "Creating a Dev Server from Scratch - Part 2"
date:   2020-12-12 11:56:01 -0400
categories: blog development
---

This is a continuation of the Creating a Dev Server from Scratch. This post continues to describe things that I have installed on my dev server.


## Installation
### 1 Docker
To start, I have installed a fresh version of Ubuntu 20.04. This is a pretty self explanatory step, so I won't go into detail. This includes creating your user, setting up network connection (basic DHCP address, reserve an address on your router to ensure constant IP Address). Once installation is complete, we can begin installing our dev dependencies. I opted for Ubuntu desktop instead of server since I want to preserve the ability to use the GUI mode of the computer (it's hooked up near my computer so it can double as an HTPC if needed).

### 2 Install Open SSH
In order to communicate with the computer remotely from my other machines, and to allow for me to tuck this dev server away, I will install an ssh server
```
$ sudo apt update
$ sudo apt install openssh-server
```
Once the installation has completed, the OpenSSH server should be running automatically. You must add and exception for ssh to communicate through your firewall.
```
$ sudo ufw allow ssh
```
NOTE: If you plan on exposing this machine to the public, there are other steps that are highly recommended for security reasons (i.e. add Fail2Ban, add ssh key authentication, change SSH port from default 22, etc.). I am just using this locally for now so I will not be adding these 

Now I can just tuck away my laptop and work on the rest of the setup remotely. In order to connect to your computer (as long as you left the default configuration) you should simply be able to use the following command from a terminal of another device:
```
// ssh [username]@[IP_ADDRESS], for example:
$ ssh ryan@192.168.1.100
```
You will then be prompted for your password (which you setup during installation of Ubuntu), and then you should be successfully logged in to your device remotely.

### 3 Install a Text Editor
Here is where personal preference comes to play, install your favourite text editor for work in the terminal (over SSH). We will be doing a lot of configuration and having a text editor you are comfortable with is important. My go to is Vim.

```
$ sudo apt install vim
```

### 4 Update GRUB to boot to CMD Line
In order to keep things low powered and reduce load on the server, I have decided to boot to command line on the dev server rather than spin up the GUI on reboots. Set linux in multi-user mode to enable boot to command line and then reboot:
```
$ sudo systemctl set-default multi-user
$ sudo reboot
```
To revert this change you can set linux in 'graphical' mode:
```
$ sudo systemctl set-default graphical
```
To start the GUI from the command line enter the following (note this may vary for different Linux installations. For Ubuntu 20.04 the default GUI is GNOME so that is what this command starts):
```
$ sudo systemctl start gdm3
```