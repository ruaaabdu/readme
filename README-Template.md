# Getting set up at Ross (DashBoard)

This document will walk you through how to set up GitBash, SHH Key, Eclipse, DashBoard, Kaylee. It will also explain how to obtain Sony License Keys and how to build DashBoard through Jenkins.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. Direct any further questions to your supervisor. 

## What you will be installing
1. GitBash
2. Eclipse 2019-03
3. JDK 1.8
4. DashBoard
5. Kaylee

## Installing
Follow the steps below to install the required programs.

### Git Bash
Git Bash is a text-only shell interface that Windows users can use alongside GitHub/Lab.
 
#### Installation
1. Go to https://gitforwindows.org/ and click Download.
2. Follow the installation process using all the default options.
3. Open up the program and run 'git --version' to ensure that git is installed correctly. 

Note: You will need a GitLab account to work on DashBoard projects. If you do not have a GitLab account, send an email to Trung Do and specify to him that you require Developer access to the Ross_DashBoard project. 

### SSH Key
An SSH key is an alternate way to identify yourself. This will be used with Git.

#### Installation
1. Open the terminal you like to use (Git, cmd, etc.)
2. Run the following line of code into the terminal to generate an ed25519 key
```
 ssh-keygen -t ed25519
```
3. The terminal will prompt you to enter a filename for your new file. If you’d like to use the default name, simply press the Enter key. There is no passphrase, so press Enter when the terminal prompts you for one.
4. Navigate to the following directory in your file browser (with username being your windows username).
```
C:\Users\username
```
5. If you used the default filename, find the folder titled .ssh. Otherwise, find the filename you previously entered in the terminal.
6. There will be two files available, one file with a .pub extension and a file with no extension. Use NotePad to open the file with the .pub extension. Copy the contents of the file. It should start with “ssh-ed25519”
7. Open Git Lab in your browser. Log in and navigate to your settings using the Icon at the top right corner of the screen. Use the lefthand panel to open the “SSH Keys tab”. Enter your key in the key field and press Add Key.
8. Now you can use “git.” links without authentication. 

### JDK 1.8
The JDK is the Java Development Kit. You will need it to run any java programs on your machine.

To check if your machine already has the JDK, run this line of code in cmd. 

```
for %i in (javac.exe) do @echo %~$PATH:i
``` 

If you already have the JDK installed, the output should resemble the following filepath. Otherwise, follow the installation instructions below.

```
C:\Program Files\Java\jdk1.8.0_221\bin\javac.exe
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
2. To apply the DB code style, go into the Java prespective by going to window > Perspective > Open Perspective > Other > Java. Go to Window > Preferences > Java > Code Style > Formatter and import the XML style file found [here](http://trogdor.rossvideo.com/dashboard/Dev Environment/).
3. Go to Window > Java > Compiler and set the compliance to 1.8.

### DashBoard
DashBoard is a platform created by Ross Video that allows users to build custom User Interface panels for control and monitering. More on DashBoard [here](https://www.rossvideo.com/products-services/management-systems/automated-production-control/dashboard/).

#### Installation
1. Start off by cloning the two repositories required for Dashboard.
	http://srvottodrepo01.rossvideo.com/ross_dashboard/dashboard 
	http://srvottodrepo01.rossvideo.com/ross_dashboard/db_shared
You can clone in the following two ways
a. Eclipse 
- Set up your SSH key by going to Window > Preferences > General > SSH2 in Eclipse and adding your key under Private keys. To add it, click Add Private Key and select the folder that without a .pub extension.
- Browse to the [DashBoard project](http://srvottodrepo01.rossvideo.com/ross_dashboard/dashboard) in Gitlab. Click the blue Clone button on the top right of the screen and copy the SSH link. 
- Open the Git perspective and click the clone button.
	![](/images/image1.png)
- Select Clone URL and use the SSH Link you copied in the previous step as the URI. The remaining required fields will auto-fill.

b. Git Bash
- Cd to the directory where you want to clone (ex. cd /C/Data/DashBoard)
- Run the git clone command with the URL of the repository:
```
git clone git@srvottodrepo01.rossvideo.com:ross_dashboard/dashboard.git
```
2. Create a target folder (E.g. C:\Data\DashBoard\target) and paste the contents of the [dashboardtp](file://srvottfp01/Company/Project%20Files/dashboard/Binaries/Dev%20Environment/dashboardtp.zip) into the target file. Also copy the content of build\client\NSIS Scripts\extras from your cloned dashboard (e.g. C:\Data\DashBoard\dashboard\build\client\NSIS Scripts\extras) and projectRoot\client\DashBoard.openGear.product.feature\rootfiles from your cloned dashboard (e.g. C:\Data\DashBoard\dashboard\projectRoot\client \DashBoard.openGear.product.feature\rootfiles) into your target folder.
3. Setup the target in eclipse: Window > Preferences > Plug-in Development > Target Platform. Select Add, then choose the “Start with an empty target definition option. Then add your tagret as a Directory and select the folder you just created (C:\Data\DashBoard\target). Make sure to select the newly created target in the Target Platform screen and hit Apply. 
4. Import the dashboard repository into Eclipse by going to File > Import > General > Existing Projects into Workspace. Select the root directory where you cloned the project (C:\Data\DashBoard\dashboard). The list of available projects is offered. Select All and Finish. 
5. Repeat Step 4 for db-shared (C:\Data\DashBoard\db-shared).
6. In the Plug In Development perspective, find the com.rossvideo.dashboardsuite.branding plugin in the list on the left. From this plug in, right click the DashBoardFramework product and “Run as” an Eclipse Application. Ignore the errors/warnings for now.
7. In the Plug In Development perspective, go to Debug Configurations using the drop down menu next to the run button. Within DashBoardFramework.product in the Eclipse Application drop down, select the Plug-ins tab and select everything under these plugins:
	- Nk – except for tstorm
	- Visual
	- Joy
	- Camera
	- Ndi
	- Touch
	- Midi
	- Device
	- tally
	- Osgi, deselect the osgi in workspace and select the target one
	- slf, ensure that only the pde plugin and slf4j 1.2.0 are selected
Click “Add Required Plug-ins” and “Validate Plug-ins”.
8. Click Run to run DashBoard from Eclipse.

### Kaylee

#### Installation

### Sony License Key
You will need a Sony License Key to work with a Sony Camera. A screen will show up like this:

#### Process
1. Go to \\server12\Company\RossKeys\KeyGenerator.exe

2. Fill out the fields in the popout window. The password is today’s day number summed with today’s month number, written out in text. i.e. for 28/11/2019 = 28 + 11 = thirty-nine (with a hyphen).
3. Paste the generated code into the DashBoard panel.

### Builds
A build is the process of turning source code to an executable file. 

#### Process
1. Go to the build website for [Camera Robotics for DashBoard](http://automation/view/DashBoard/view/All%20DashBoard/job/DashboardCameraAlphaBuild/) and log in to Jenkins (same as your windows log in).
2. Click Configure from the panel on the left and selec the Build Environment tab. Modify the values accordingly:
- dashboard_branch: The branch in the Dashboard repo to build
- db_shared: The branch in the db_shared repo to build
- db_version: The major.minor.micro version number to be associated with your build (all 3 numbers have to be included)
- db_version_major: The major version number to be associated with your build
- output-folder-name: The name of the folder that will be posted under the Alpha/Sprint XX folder in [Trogdor]( http://trogdor.rossvideo.com/dashboard/DashBoard/GCC/Alpha/).
- jira-comment: A Boolean indicating whether you would like a JIRA comment posted with the link to the build.
- jira-id: The JIRA ticket number to post the comment to (eg. DASH-1234). This is ignored if jira-comment=false
3. Hit Save and Navigate to the [home page](http://automation/view/DashBoard/view/All%20DashBoard/job/DashboardCameraAlphaBuild/). Click Build Now. If your build is successful, there will a folder, with the name you configured, in [Trogdor](http://trogdor.rossvideo.com/dashboard/DashBoard/GCC/Alpha/) containing your build.
Note: Do not click Delete Project. To investigate a failed build, look through the console output of your build in the Build History.

## Helpful Links and Information:

### Links
https://rossvideoltd.sharepoint.com/sites/hr_info/SitePages/Home.aspx

### IP Addresses for cameras
BRC H900 – 10.65.110.230
BRC X1000 – 10.65.110.226
PIVOTCam-SE (Rooster) – 10.65.110.223

### Appendix

#### How to add a PTZ Camera


#### How to add a Server
 

#### How to add Kaylee PowerPlay

