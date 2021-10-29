<h1> Mac's default version of Python is 2.7, to change that to the newest one, do the following... </h1>

+ Check current python version by: 
 
python --version

+ Visit <a href="Python.org" target="_blank">Python.org</a> and download the latest release

+ Open mac terminal as su (<a href="" target="_blank">How?</a>)

+ Change the default version to the latest release you downloaded (in my case 3.10) by: 

ln -s -f /usr/local/bin/python3.10 /usr/local/bin/python

