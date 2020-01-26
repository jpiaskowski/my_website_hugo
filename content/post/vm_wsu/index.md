---
title:  "How to Set Up a Virtual Machine for Data Analysis If You Are an IT Admin Noob"
authors: 
- admin
date:   2018-03-18 10:50:02 -0700
draft: false
featured: false
diagram: true
image:
  caption: 'Image credit: [**???**]'
  placement: 3
projects: []
categories: 
- workflow
tags: 
- virtual machine
- Jupyter
---

## Basic Info

I came back from PAG (Plant & Animal Genome - a huge ag genetics conference held in San Diego each January) all fired about setting up a virtual machine (VM) to facilitate collaboration. The hope what this would enable us to share files and scripts better (without the aid of countless dropboxes everyone forgets about), and improve overall collaboration.

I had considered this before - enterprise deployment of RStudio server or Jupyter hub, but our program doesn’t have dedicated IT support to do this, and frankly, it all seemed rather intimidating to a plant geneticist like me. But this would be useful. I had once run my laptop on dual boot with Ubuntu and Windows. I could handle this, couldn’t I? All I want is a VM that everyone can access via remote desktop for their analytical needs. Fortunately, I had no idea how difficult this would be, or I might not have entered the lion’s den. So, here are fruits of my labor in the hopes it will ease the process for future users. This guide was developed specific for Washington State University's College of Agriculture, Human and Natural Resource Sciences (CAHNRS).

__Step 1:__  Request a virtual machine. I used the [**CAHNRS webform**](https://it.cahnrs.wsu.edu/service-catalog/vm-hosting/). I went with CentOS 7 - a Linux distribution that had been recommended to me as “full featured” (this remains to be seen). This step may take a few weeks.

It helps to know exactly what you want to do so CAHNRS IT can properly set up the VM and “rules” (exceptions to their standing rules) to allow you to do the work you want. Running RStudio server means having at least one port open. The RStudio Server default port is 8787 (although than can be easily changed). Remote desktop needs port 3350 open. Jupyter Hub will have its own conventions - all described in their documentation. I recommend you consult the documentation for what you want *before* ordering a VM.

__Step 2:__ Download the [__WSU VPN client__](https://its.wsu.edu/ssl-vpn/). Whoever is the admin will need have the WSU SSLVPN to tunnel in through a secure connection in order to do any work remotely. This is the probably the easiest step of the entire process. Who doesn’t love point-and-click installations?

__Step 3:__ Download software for SSH. Initially, you will need an SSH program to connect through secure, encrypted tunnel. [__Putty__](https://www.chiark.greenend.org.uk/~sgtatham/putty/) is a popular option. I like secure shell, which I found [__here__](https://www.wm.edu/offices/it/services/software/licensedsoftware/webeditingsftp/sshsecureshell/index.php). This is actually a rather convenient way to manage the VM, so its utility will likely stretch past the setup phase.

## General Linux notes:
This is CentOS, an alternative distribution to its more popular relative, Ubuntu. While most commands are the same across Linux distributions, some things are a little different. FYI, Centos is similar to .rhel and Red Hat if you are combing forums for help.

Check out these [__standards for Linux filesystems__](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard). It will help you understand how the machine is organized. Don’t spend too much time here; it’s more of a reference than pleasure reading.

[__The Centos documentation__](https://www.centos.org/docs/5/) can be helpful, as well.

### Miscellaneous useful commands:

Most of the command listed here for VM setup require root privileges, which can be accomplished with “sudo”. You’ll find you need to be root 98% of time during VM setup, so do this:

`sudo su`

This changes the console from:
`$ `
to:
`#   `

Use Ctrl-D to leave root. And be careful when you are root!

Print current working directory:  

`pwd`

Change the working directory to go up a level:  

`cd .. `

Absolute path (will work everywhere):  

`$ cd /<path>`

Relative path (only sees child directories):  

`cd <path>`

This produces a long list of all files and directories in your current working directory:  

`ll -a`

To see options associated with a particular command:  

`<command> --help`

To remove a single file:  

`rm <your_file.txt>`

 To remove an entire directory:  
 ‘r’ does it recursively   
 ‘f’ will do it without asking again (it skips the step that is essentially asking “are you sure you want to delete this????”)

`rm -rf <your_directory>`

To install a piece of software for all users:

`sudo yum install <library>`

 To view files:

`more <file>`

To edit files. This command requires sudo for most of the files you will need to look at for VM setup.

`nano <file>`

There’s also the vim editor, but use it your own risk. Here is the best description I have ever read of it:
>“If you want an outstanding free text editor and don't mind a seemingly vertical learning curve plus long days of pain and suffering while all your neural pathways are rewired, try Vim.”

`vi <file> `

To escape vim:

`  :q  `

Make a new directory:

`mkdir <dir_name>`

Setting your VM to the correct timezone (Pacific in this case). It is helpful to have the correct time when you are inspecting the logs during troubleshooting:

```
timedatectl set-timezone 'America/Los_Angeles'
```

###  Managing Users

It is important to think thru how to organize the users into groups and create folders with shared permissions in order to enable collaboration.

Below are some common commands. Note that they all require root or sudo access. Centos provides excellent [__documentation__](https://www.centos.org/docs/5/html/Deployment_Guide-en-US/s1-users-tools.html) on this.

Add a new user (the second option adds a new user to an existing group):  
`useradd <username>`  
`useradd <username> -g <groupname>`  

Set user password:  
`passwd <username>`  

Add a group:  
`groupadd <groupname>`   

Add an existing user to an existing group:   
`sudo usermod -a -G <groupname> <username>`

Enable file ownership by a group:  
`chown :<groupname> <path/to/directory>`

Enable file ownership by a user:  
`chown :<username> <path/to/directory>`

Delete a user:  
`userdel <username>`

Link directories:  
`ln -s <path/to/file> <path/to/link>`  


## If you want to run remote desktop:
There are other desktop environments, but Gnome is a popular one, so why not?

See what is available:
```
yum group list
```
Install Gnome desktop environment:

```
sudo yum install gnome
sudo yum install gnome desktop environment
```
Check that it is running
```
ps -aux | grep gnome
```
Install and configure the EPEL repository:
```
sudo rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
```
Add the nux repository:
```
sudo rpm -Uvh http://li.nux.ro/download/nux/dextop/el7/x86_64/nux-dextop-release-0-1.el7.nux.noarch.rpm
```
Install xrdp:
```
sudo yum -y install xrdp tigervnc*
```
You’ll need to start xrdp and xrdp-sesman (“session manager”) as a service (so they are always running) and enable them both to autostart:

```
sudo systemctl start xrdp
sudo systemctl enable xrdp
sudo systemctl start xrdp-sesman
sudo systemctl enable xrdp-sesman
```

And check:

```
sudo systemctl status xrdp
sudo systemctl status xrdp-sesman
```

These should indicate that xrdp and xrdp-sesman are _active_.

Open a port to allow remote desktop connections:

```
sudo firewall-cmd --permanent --zone=public --add-port=3389/tcp
sudo firewall-cmd --reload
```

Configure SELinux:

```
sudo chcon --type=bin_t /usr/sbin/xrdp
sudo chcon --type=bin_t /usr/sbin/xrdp-sesman
```

And check that the port is open:

```
netstat -plan | grep xrdp
```

Next, vnc has to be started. It is tied to a user, so get out of root if you are there (and don’t use sudo).

Set a password:

```
vncpasswd -<user>
```

It will return a prompt, asking you for a password. This is what you will use for remote desktop. You can definitely skip the  step of having a read-only password by answering “n” for no. (It’s unclear to me why anyone would want a password for that as opposed to whole new user account with read-only permissions, but what do I know?).

Next, start the server. Try to only do this once.

```
vnc server
```

If you end up with multiple vnc server instances running on just ONE user account, kill the extra processes and delete their log files. Here are the steps:

First, find the process ID’s:
```
ps aux | grep vnc
```

The process ID's (pid) are located in the second column from the left. Kill the extra vnc pid's:
```
kill -9 <pid>
```

Find the associated files and delete them. I found there here:

```
cd /var/log
```
They will have names like "Xorg.9.log".

### Troubleshooting Remote Desktop

If you run into trouble, try disabling SELinux:

```
sudo setenforce 0
```

Check:

```
getenforce
```

(it should say “permissive” NOT “enforcing)

Check for problems (as root):

```
cd /var/logs
more xrdp.log
more xrdp-sesman.log
```

These are cleared rapidly and folded into the xrdp .tar files, so do not be alarmed if the log files are empty. If you really want to see something in the xrdp logs, stop and restart xrdp.

The most useful file is the messages file, but it’s very long, so just show the end:

```
sudo tail -55 messages
```

If you _really_ want to see what's going on, watch the file in real time:

`tail -f messages`

Ctlr-C to leave

The firewalld file in the /var/log/ directory is stuffed with known, but currently unresolved bugs so it’s not very useful for diagnosing problems at this time.

There's a number of remote desktop applications which can be used to access the VM. Windows RDP is easy to use and secure.

### Run R in remote desktop
Start by installing R. WSU would not let me access the internet directly from the remote desktop internet browser, but I could through the SSH. So here are command line instructions:
```
sudo yum install epel-release
sudo yum update
sudo yum install R -y
```
Next, install RStudio. Get current link from the [__RStudio website__](https://www.rstudio.com/products/rstudio/download/). The link below worked March 19, 2018:
```
wget https://download1.rstudio.org/rstudio-1.1.442-x86_6
sudo rpm -Uvh rstudio-1.1.442-x86_64.rpm
```

## Other

It's also helpful to have an office suite

```
sudo yum install libreoffice
```

Okay, all done! Go and solve the world’s problems!
