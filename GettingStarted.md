# Getting Started
This is a short wiki for Ebola Aid Team members needing to set up their development environment for this project. The following prerequisites must be completed before we can begin development.

## Java
First, we must install Java on our machines, since Android applications are built upon Java.

1. Download the appropriate Java Development Kit 7 (JDK 7) package for your OS (Windows, Mac, Linux) [**here**](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).
  + Note that x86 is for 32-bit and x64 is for 64-bit architectures, so check the system info on your machine to determine which one your OS runs on.
  + <code>.tar.gz</code> files are compressed (similar to <code>.zip</code>) whereas <code>.exe</code> files are Windows executables. <code>.dmg</code> is an Apple disk image. It doesn't really matter which one you choose, as you will just have to unzip the file if it is compressed.
  + **Important:** Android Studio currently does not support JDK 8, so make sure that your version is correct.
2. Run the JDK installer that you just downloaded.

## MySQL
MySQL is a relatonal database that will essentially be storing all of our patient data in the back-end. We won't directly be interacting with MySQL in code, as OpenMRS has APIs that abstracts a lot of the complex database queries/commands and from us. However, we need to install MySQL on our dev machines so that the OpenMRS server can run.

1. Go to http://www.sitepoint.com/how-to-install-mysql/ for instructions on how to install MySQL.
  + Complete steps 1, 2, 4, 5, 6.
  + Coreection for step 4: The path for the data directory on Windows should be <code>C:\\mysql\\data"</code>
  + Correction for step 5: <code>mysqlbin</code> should be <code>mysql/bin</code>. Also note that running <code>mysqld</code> will launch the application in the current terminal window, so you will need to open a new terminal window to run <code>mysql -u root</code>

## Android Studio
This is the IDE we will be using for Android development. 

1. Download Android Studio: https://developer.android.com/sdk/index.html#Other 
  + Under "All Android Studio Packages", select the file appropriate for your OS.
2. Install Android Studio: https://developer.android.com/sdk/installing/index.html?pkg=studio
3. Add SDK Packages: https://developer.android.com/sdk/installing/adding-packages.html
  + Only steps 1, 2, and 4 are necessary; step 3 is optional and not really needed for our project at this point.

## Git
Git is a version control system that will allow us to maintain a history of our project files. Each revision is tracked, which makes it easy for multiple developers to collaborate on a single project. We will go through the workflow of Git later on.

1. Download Git
  + Linux: http://git-scm.com/download/linux
  + Mac: http://git-scm.com/download/mac
  + Windows: http://git-scm.com/download/win
2. Create a GitHub account
  + Please email ryanmawong@gmail.com with your GitHub username so that you can be added to the UBC-BEST-Ebola GitHub organization.
3. Clone this project's Git repository
  + Open a terminal and use the command line to navigate to a directory that you would like to save the repository. 
  + Example:
    + <code>mkdir "UBC BEST Projects"</code> (creates a new folder)
    + <code>cd "UBC BEST Projects</code> (nagivates to the folder)
    + <code>git clone https://github.com/UBC-BEST-Ebola/ebola-aid</code> (makes a local copy of the repository)
  + Note that you may be prompted to enter your GitHub credentials before the cloning proceeds

## Checkpoint (Sept. 12, 2015)
Our actual Android project is still being set up and is not ready to be built yet, so we will create an Android app from the templates to quickly verify that Android Studio was configured properly and can build a simple Android project.

1. **File > New Project**
2. **Application name:** ExampleApp (arbitrary)
3. **Company Domain:** example.co (arbitrary)
4. Select **Phone and Tablet** with **Minimum SDK: API 19**
5. Select **Blank Activity** then Finish.
6. Setup developer mode on your device and enable USB Debugging: http://www.kingoapp.com/root-tutorials/how-to-enable-usb-debugging-mode-on-android.htm
7. Press the play icon to build and run the app.

## OpenMRS
OpenMRS is an open source platform that we will be using to build the back-end of our EMR system. It is a web-based service that provides APIs that communicate the data from our front-end (aka the user interface of our Android application) to a database. Choose one of the two options to set up a local OpenMRS server:

### Build/run OpenMRS from source ###
This step requires maven to build and run the source code for OpenMRS.

1. Navigate to a project folder of your choice, then run: <code>git clone https://github.com/openmrs/openmrs-core</code>
2. <code>cd openmrs-core</code>
3. <code>mvn clean install</code>
4. Change to the <code>webapp</code> directory and run <code>mvn jetty:run</code>
5. Open http://localhost:8080/openmrs/ in a browser and run the setup (simple install with demo patient data)
 
### Run OpenMRS via the standalone application ###
Use the standalone app **only** if you are unable to successfully build and run OpenMRS from source.

1. Download, unzip and run https://sourceforge.net/projects/openmrs/files/releases/OpenMRS_2.2/openmrs-standalone-2.2.zip/download
2. Download https://wiki.openmrs.org/download/attachments/74252444/webservices.rest-omod-2.12-20150615.175221-10.omod?version=1&modificationDate=1434391646461&api=v2
3. Login with username "admin" and password "Admin123". Go to Administration -> Advanced Administration -> Manage Modules -> Add or Upgrade Module -> Type: xforms and hit install. Repeat to upgrade webservices.rest, but instead of typing upload the omod file downloaded in the previous step.
4. Restart the server.
5. You should be able to login using your Android Client given server is accessible over the network.
