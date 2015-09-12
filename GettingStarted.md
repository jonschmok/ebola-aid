# Getting Started
This is a short wiki for Ebola Aid Team members needing to set up their development environment for this project. The following prerequisites must be completed before we can begin development.

## Java
First, we must install Java on our machines, since Android applications are built upon Java.

1. Download the appropriate Java Development Kit 7 (JDK 7) package for your OS (Windows, Mac, Linux) [**here**](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).
  + Note that x86 is for 32-bit and x64 is for 64-bit architectures, so check the system info on your machine to determine which one your OS runs on.
  + <code>.tar.gz</code> files are compressed (similar to <code>.zip</code>) whereas <code>.exe</code> files are Windows executables. <code>.dmg</code> is an Apple disk image. It doesn't really matter which one you choose, as you will just have to unzip the file if it is compressed.
  + **Important:** Android Studio currently does not support JDK 8, so make sure that your version is correct.
2. Run the JDK installer that you just downloaded.

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
Our actual Android project is still being set up and is not ready to be built yet, so we will use the old *bestclinic* repository to quickly verify that Android Studio was configured properly and can build a simple Android project.

1. Navigate to a folder where you prefer to store your projects, similar to the example in the Git section above.
2. Run the command <code>git clone https://\<username\>@bitbucket.org/bestresearch/bestclinic.git</code> (replace <code>\<username\></code> with your actual username). 
  + *Tip:* Cloning may fail because your <code>~/.gitconfig</code> file may contain user credentials that do not match your Bitbucket account. You can perform a quick fix by editing the <code>[user]</code> field in <code>~/.gitconfig</code>.
3. Launch Android Studio and if the "Quick Start" menu shows up, then click "Import Non-Android Studio Project". Otherwise, go to **File > Import Project...** and select the bestclinic folder.
4. There should be a "play button" in the row of icons at the top of Android Studio. Click this to run the app. Android Studio will first build the project, and if it succeeds, then the Android app should launch in the connected device, or the emulator.
  + The build may fail due to lacking package dependencies. The compiler should prompt you with a link to import these lacking dependencies, which should fix any issues.

## OpenMRS
OpenMRS is an open source platform that we will be using to build the back-end of our EMR system. It is a web-based service that provides APIs that communicate the data from our front-end (aka the user interface of our Android application) to a database. ***This component of our project is still being set up. Further instructions will be provided soon.***


