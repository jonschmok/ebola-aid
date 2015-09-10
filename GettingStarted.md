# Getting Started
This is a short wiki for Ebola Aid Team members needing to set up their development environment for this project.

## Android Studio
1. Download Android Studio: https://developer.android.com/sdk/index.html#Other 
  + Under "All Android Studio Packages", select the file appropriate for your OS (Windows, Mac, Linux).
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
3. Clone this project's Git repository
  + Open a terminal and use the command line to navigate to a directory that you would like to save the repository. 
  + Example:
    + <code>mkdir "UBC BEST Projects"</code> (creates a new folder)
    + <code>cd "UBC BEST Projects</code> (nagivate to the folder)
    + <code>git clone https://github.com/UBC-BEST-Ebola/ebola-aid</code> (makes a local copy of the repository)
  + Note that you may be prompted to enter your GitHub credentials before the cloning proceeds

## Running the App
1. Launch Android Studio and click "Open an existing Android Studio Project".
2. Select the "ebola-aid" folder.
3. There should be a "play button" in the row of icons at the top of Android Studio. Click this to run the app. You can select whether you want to connect to your device or the emulator.

