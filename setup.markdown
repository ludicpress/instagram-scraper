---
layout: page
title: Setup
permalink: /setup/
---

Before we begin with the workshop component of how to use Wget for digital research there is some preliminary setup we have to complete on your computer. Since wget is used through the command line, we have to install packages onto your computer for it work. Depending on which operating system you use, setup can be straightforward or the most time consuming aspect of learning how to use wget. Below are installation instructions for Linux, Windows, and OS X users. Once wget is installed on each system, the instructions will be the same for every user participating in the workshop.

## Linux Instructions


## Windows Instructions
To install wget we have to activate the Windows Subsystem for Linux (WSL) and install a Linux distro (i.e., command line). For this workshop we will use the Ubuntu application on Windows, but first we have to activite the WSL.

To activate the WSL, open Powershell as an Administrator. To do this, type in Powershell in the Windows search bar in the bottom left corner of your screen. The application Windows Powershell Ise will appear. On the right-hand side of the window will be the option 'Run as administrator'. Select Run as administrator and enter your administrative login credentials if prompted. If you do not run Powershell as an administrator the next step will not work.

In the Powershell terminal that opens up, copy and paste the following command and hit enter:

```Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux```

Restart your computer when prompted to do so.

Once your computer has restarted, open the Microsoft Store. You can access the Microsoft Store by typing Microsoft Store in the Windows search bar and select open from the right-hand side of the window. When the Microsoft Store opens, type 'Ubuntu' into the search bar. Several Ubuntu applications will appear in the search results. Select the app that is only titled 'Ubuntu' and developed by Canonical Group Limited.

Click install and wait for the Ubuntu application for Windows to install. Once the application has installed, type Ubuntu in the Windows search bar and open the application. Note, you do not need to Run as administrator for this application. The Ubuntu application will take approximately 5 to 10 minutes to install, so do not worry if it does not open right away.

When Ubuntu opens for the first time you will be propted to create a username and password. Create your username and hit enter. Create your password and hit enter. A re-enter password prompt will appear and you re-enter your password. Your username and password should now be created. Whenever you open Ubuntu and try to install software you will be prompted for your username and password.

The next few steps are relatively time consuming, but they are necessary to make sure we install Ruby and then Jekyll on to your computer using Bash for Windows. In the Ubuntu command prompt type in the following command and hit enter:

```bash```

Your command prompt instance should now be a Bash instance. The colour of your command prompt should have changed to another colour (in my case, green). Next we need to update our Bash repository lists and packages. In the command prompt type in the following command and hit enter:

```sudo apt-get update -y && sudo apt-get upgrade -y```

The first part updates the Bash repository lists and the second following the ```&&``` upgrades the Bash packages. At this point you will be asked to restart services during package upgrades without asking. When prompted select ```<Yes>```and hit enter. This may take several minutes (almost 15 minutes when I timed it!), so hang tight and wait for the prompt to reappear.

When the prompt reappears we can check to make sure Bash was installed properly. In the command prompt type in the following command and his enter:

```bash --version```

If all went well, the following information should display on your machine:

```GNU bash, version 4.4.20(1)-release (x86_64-pc-linux-gnu)```  
```Copyright (C) 2016 Free Software Foundation, Inc.```  
```License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>```  
```This is free software; you are free to change and redistribute it.```  
```There is NO WARRANTY, to the extent permitted by law.```

At the time of writing this documentation Bash was at version 4.4.20.

Next we need to install Ruby. Ruby is the programming language that will enable us to install Jekyll and create our static website. To install Ruby we will use a repository from BrightBox, which hosts optimized versions of Ruby for Ubuntu. In the command prompt type in the following commands and hit enter. Remember to wait for the prompt before entering each line of code.

First:
```sudo apt-add-repository ppa:brightbox/ruby-ng```
Second:
```sudo apt-get update```
And third:
```sudo apt-get install ruby2.5 ruby2.5-dev build-essential dh-autoreconf```

If prompted select yes or type ```y``` and hit enter. This may take several minutes to complete the whole installation process.

Next, we need to install Ruby:

```apt install ruby```

If prompted select yes or type ```y``` and hit enter.

Now that Ruby is installed we need to update our gems. Gems are packages within Ruby that make it easy for us to install programs, like Jekyll, with a simple command. To update our gems, type the following into the command prompt and hit enter:

```gem update```

Now that the gems have been updated, we can install Jekyll. In the command prompt type in the following command and hit enter:

```gem install jekyll bundler```

When the prompt returns we can check to see if Jekyll is running smoothly by entering the following command:

```jekyll -v```

The following message should display in your prompt:

```jekyll 4.0.0```

At the time of writing Jekyll was upgraded to 4.0, but there may be a later version depending on when you read this documentation. Now that you have completed the setup and installation of jekyll you can move on to the workshop!

## OS X Instructions
On OS X, there are two ways to get wget and install it. The easiest is to install a package manager and use it to automatically install wget. There is a second method, discussed below, that involves compiling it.

Both, however, require that you install Apple’s ‘Command Line Tools’ to use properly. This requires downloading XCode. If you have the ‘App Store’, you should be able to just download XCode via this link.  If not, the following instructions will work.

To download this, go to the Apple Developer website, register as a developer, and then in the downloads for Apple developers section you will need to find the correct version. If you are on the most recent version, Lion as of July 2012, you can use the main link. If not, you will need to click on the link: “Looking for additional developer tools? View Downloads.”

After logging in with your free developer credentials, you will see a long list. Type xcode in the search bar and find a version that is compatible with your operating system version. This may take some clicking around to find the right version for you. For example, Xcode 3.2 is the version for OS X 10.6 Snow Leopard, 3.0 is the version for OS X 10.5 Leopard, etc.

It is a big download, and will take some time. Once you have the file, install it.

You will need to install the ‘Command Line Tools’ kit in XCode. Open up the ‘Preferences’ tab, click on ‘Downloads,’ and then click ‘Install’ next to Command Line Tools. We are now ready to install a package manager.

The easiest package manager to install is Homebrew. Go to https://brew.sh and review the instructions. There are many important commands, like wget, that are not included by default in OS X. This program facilitates the downloading and installation of all required files.

To install Homebrew, open up your terminal window and type the following:

```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```

This uses the ruby programming language, built into OS X, to install Homebrew. To see if the installation worked, type the following into your terminal window:

```brew```

A list of documentation options should appear if it has been installed. We have one more command to run to make sure everything is working, which is:

```brew doctor```

With Homebrew installed, we now have to install wget. This is now an easy step.

```brew install 
