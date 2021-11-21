# Welcome to MacOS HOWTO! 

Before doing anything else (no matter how upset with an issue you are), please go over <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/README.md" target="_blank">README.md</a> of this repo. Thanks!

### Table of contents

+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Mac/HOWTO.md#python-installation">Python installation</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Mac/HOWTO.md#pip-installation">Pip installation</a>
+ <a href="https://github.com/scraptechguy/IssuesEncoutered/blob/main/Mac/HOWTO.md#setting-up-super-user-su">Setting up super user (su)</a>
+ <a href="">Running C++</a>
+ <a href="">Visual Studio Code won't update</a>

## Python installation 

Mac's default version of Python is 2.7, to change that to the newest one, do the following... 

+ Check current python version in terminal by: 
 
      python --version

+ Visit <a href="Python.org" target="_blank">Python.org</a> and download the latest release

+ Open mac terminal as su (<a href="https://github.com/scraptechguy/IssuesIEncoutered/blob/main/SettingUpSuperUserOnMac.md" target="_blank">How?</a>)

+ Change the default version to the latest release you downloaded (in my case 3.10) by: 

      ln -s -f /usr/local/bin/python3.10 /usr/local/bin/python

+ Check current Python version again by: 

      python --version

Output in my case:

      Python 3.10.0


## Pip installation

Mac for some reason can't access pip by default. To install it, do the following...

+ Try running pip command and installing a library. For example Python Turtle:

      pip install PythonTurtle
      
Output when pip doesn't work: 

    zhs: command not found: pip

+ Visit <a href="https://bootstrap.pypa.io/get-pip.py" target="_blank">online Python script</a> to check it's legitimacy
(read the first few lines, they're pretty funny xd)

+ Open terminal and execute the following command that downloads the online script (get-pip.py file)

      curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
      
+ Execute the Python file by: 

      python get-pip.py
      
+ My output (yours should look similar if not the same): 

      ...
      Successfully installed pip-21.3.1 wheel-0.37.0


## Setting up super user (su) 

<a href="https://support.apple.com/en-us/HT204012" target="_blank">Official documentation</a>

+ Go to System Preferences > Users and Groups 

+ Click the lock in left down corner to enable making changes 

+ Go to Login Options, there, click Network Account Server: Join...

+ Open Directory Utility and enable making changes by clicking the lock again 

+ In the menu at the top select Edit and Enable Root User

<img width="466" alt="image" src="https://user-images.githubusercontent.com/75474651/140280137-437f67db-2b0d-4f0c-925f-cc55d59efb5e.png">

(Image of how Edit menu looks like after succesfully setting up root user)


## Running C++

### Using XCode 

+ Download XCode from official <a href="" target="_blank">Apple developer site</a> or from the App Store

+ Open XCode and Create a new XCode project 

<img width="487" alt="image" src="https://user-images.githubusercontent.com/75474651/140281010-ce9ec4be-5efe-481c-abcc-88061bfe0ec4.png">

+ As a template choose Command Line Tool in macOS pane 

<img width="712" alt="image" src="https://user-images.githubusercontent.com/75474651/140281377-b9abe8ac-2a0b-4465-81a1-402423b0162b.png">

+ In options for your new project, fill in the blanks and as a language, choose C++ (all these settings can be changed later)

<img width="712" alt="image" src="https://user-images.githubusercontent.com/75474651/140281524-6a14ae1d-a21b-46f5-b925-cd5eeadc5109.png">

This will create main.cpp. We're done!

### Using Visual Studio 

### Using Visual Studio Code 

## Visual Studio Code won't update 

VSCode has by default (when downloaded) only read access - it's in the Downloads folder -> it won't update itself and won't let you update it To fix this, do the following...

+ Move Visual Studio Code to the Applications folder

+ Open VSCode and click the settings icon 

+ Scroll all the way down in the menu and click Check for Updates... 

<img width="335" alt="image" src="https://user-images.githubusercontent.com/75474651/142592674-e78bc89a-0c8b-4af3-962c-1e298142f99c.png">

After this, VSCode will check for updates and if it finds any, gets updated! 
