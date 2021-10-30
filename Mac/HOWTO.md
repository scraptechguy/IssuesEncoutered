## Python installation on Mac

Mac's default version of Python is 2.7, to change that to the newest one, do the following... 

+ Check current python version by: 
 
      python --version

+ Visit <a href="Python.org" target="_blank">Python.org</a> and download the latest release

+ Open mac terminal as su (<a href="https://github.com/scraptechguy/IssuesIEncoutered/blob/main/SettingUpSuperUserOnMac.md" target="_blank">How?</a>)

+ Change the default version to the latest release you downloaded (in my case 3.10) by: 

      ln -s -f /usr/local/bin/python3.10 /usr/local/bin/python

+ Check current Python version again by: 

      python --version

Output in my case:

      Python 3.10.0


## Installation of pip

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
