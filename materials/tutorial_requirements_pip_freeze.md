## Tutorial Pip Freeze > requirements.txt & Github



### Create a virtual

````

    $ python -m venv tutorial_env
    $ source tutorial_env/bin/activate

    # on windows in git bash
    $ source tutorial-env/Scripts/activate

    $ pip list

    Package       Version
    ------------- -------
    pip           19.1.1 
    setuptools    40.8.0    

    $ pip install simple-colors

    $ pip list

    Package       Version
    ------------- -------
    pip           19.1.1 
    setuptools    40.8.0 
    simple-colors 0.1.5

````

### Create a new project

````

    $ mkdir pip_test
    $ cd pip_test
    $ touch script.py
    $ touch README.md  # checkout https://www.makeareadme.com/ for content 

````
>script.py  
````python

    from simple_colors import *

    print(green('hello'))
    print(green('hello', 'bold'))
    print(green('hello', ['bold', 'underlined']))

````
### Pip Freeze

````

    $ pip freeze 
    simple-colors==0.1.5 # shows a list of installed packages

    $ pip freeze > requirements.txt # creates a file with a requirements list
    
    $ ls
        .
        ├── README.md
        ├── requirements.txt
        └── script.py

````

### Git
````
    $ git remote add origin https://github.com/clbokea/test_pip.git
    $ git add .
    $ git commit -m "init"
    $ git push -u origin master
````

Now you have "delivered" you finished project. Next you will act as the user of your project. 


### Create a new virtual enviroment
First deactivate the virtual enviroment you are in (if you are)

````
    $ deactivate
````
````
    $ python -m venv tutorial_2_env
    $ source tutorial_2_env/bin/activate

    # on windows in git bash
    $ source tutorial_2-env/Scripts/activate

````


### GIT CLONE or PIP INSTALL

````

    $ pip install git+https://github.com/clbokea/test_pip.git

    # or

    $ git clone https://github.com/clbokea/test_pip.git

````

### Try to run

````
    python script.py
    Traceback (most recent call last):
        File "script.py", line 1, in <module>
        from simple_colors import *
    ModuleNotFoundError: No module named 'simple_colors'
````
### Install dependencies

````
    $ pip list

    Package       Version
    ------------- -------
    pip           19.1.1 
    setuptools    40.8.0    

    $ pip install -r requirements.txt

    $ pip list

    Package       Version
    ------------- -------
    pip           19.1.1 
    setuptools    40.8.0 
    simple-colors 0.1.5

````

### Run script.py

````python
    
    python script.py
    hello
    hello
    hello
````


&copy; clbo@kea.dk, 09-05-2019