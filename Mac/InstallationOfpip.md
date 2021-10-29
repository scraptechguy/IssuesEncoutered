<h1>Mac for some reason can't access pip by default. To install it, do the following...</h1>

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
