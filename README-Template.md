﻿# Getting set up at Ross (DashBoard)

This document will walk you through how to set up GitBash, SHH Key, Eclipse, DashBoard, and Kaylee.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. Direct any further questions to your supervisor. 

## Prerequisites
1. GitBash
2. Eclipse 2019-03
3. JDK 1.8
4. DashBoard
5. Kaylee

## Installing
Follow the steps below to install the required programs.

### Git Bash
Git Bash is a text-only shell interface that Windows users can use alongside GitHub.
 
#### Installation
1. Go to https://gitforwindows.org/ and click download.
2. Follow the installation process using all the default options.
3. Open up the program and run 'git --version' to ensure that git is installed correctly.

### SSH Key
An SSH key is an alternate way to identify yourself. This will be used with Git.

#### Installation
1. Open the terminal you like to use (Git, cmd, etc.)
2. Run the following line of code into the terminal to generate an ed25519 key
```
 ssh-keygen -t ed25519
```
3. The terminal will prompt you to enter a filename for your new file. If you’d like the default name, simply press the Enter key. There is no passphrase, so press Enter when the terminal prompts you for a password.
4. Navigate to the following directory in your file browser (with username being your username).
```
C:\Users\username
```
5. If you used the default filename, find the folder titled .ssh. Otherwise, find the filename you previously entered in the terminal.
6. There will be two files available, one file with a .pub extension and a file with no extension. Use NotePad to open the file with the .pub extension. Copy the contents of the file. It should start with “ssh-ed25519”
7. Open Git Lab in your browser. Log in and navigate to your settings using the Icon at the top right corner of the screen. Use the lefthand panel to open the “SSH Keys tab”. Enter your key in the key field and press Add Key.
8. Now you can use “git.” links without authentication. 

### JDK 1.8
The JDK is the Java Development Kit. You will need it to run any java programs on your machine.

To check if your machine already has the JDK, run the following line of code in cmd. 

```
for %i in (javac.exe) do @echo %~$PATH:i
``` 

If you already have the JDK installed, the output should resemble the following filepath. Otherwise, follow the installation instructions below.

```
C:\Program Files\Java\jdk1.8.0_131\bin\javac.exe
```

#### Installation
1. Go to the [Oracle website](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) and install the latest version of JDK for your OS. 
2. Once you finished installing the JDK, open up the installation folder and go into the bin folder and copy the filepath. It should resemble the filepath below.
```
C:\Program Files\Java\jre1.8.0_221\bin
```
3. Open up the system properties by searching for “Edit the System Environment Variables” in the search bar or by pasting the following line of code into your cmd termial.
```
SystemPropertiesAdvanced
```
4. Click Environment Variables. Create a new User Variable. For Name, enter “PATH” and for Value, enter the bin filepath you previously copied. If there is already a variable with the name PATH, click Edit and add the bin filepath to the PATH variable. 
5. Ensure that the JDK is installed, explained above. 
### Eclipse
Eclipse is a common IDE which you could use to launch DashBoard.

#### Installation
1. Download the Eclipse 2019-03 installer [Eclipse2019-03-64bit.zip]( http://trogdor.rossvideo.com/dashboard/Dev%20Environment/Eclipse2019-03-64bit.zip). Note: installing another version of Eclipse has not worked well in the past in terms of getting the DashBoard programs to run on it.

### DashBoard
DashBoard is a platform by Ross Video that allows users to build User Interface custom panels for control and monitering. More on DashBoard (here)[https://www.rossvideo.com/products-services/management-systems/automated-production-control/dashboard/].

#### Installation
1. Start off by cloning the two repositories required for Dashboard.
	http://srvottodrepo01.rossvideo.com/ross_dashboard/dashboard
	http://srvottodrepo01.rossvideo.com/ross_dashboard/db_shared
	You can clone in the following two ways
a. Eclipse 
- Set up your SSH key by going to Window > Preferences > General > SSH2 in Eclipse and adding your key under Private keys.
- Open the Git perspective by going to window > Perspective > Open Perspective > Other > Git.
- Use the button shown in the link below to clone the Git repo using the SSH Link you coped in the previous step.
- 

b. Git Bash
- Cd to the directory where you want to clone (ex. cd /C/Data/DashBoard)
- Run the git clone command with the URL of the repository:
```
git clone git@srvottodrepo01.rossvideo.com:ross_dashboard/dashboard.git
```
2. 
### Kaylee

#### Installation

