
## Installing a Python distribution for Windows CLI

This document gives the instructions to install a Python distribution with all dependencies required to create and Run python in Command Line in a Virtual Environment.


### Instruction for Windows

**Important**: download python from **official** website.

1. [Download latest version of Python 64-bit for Windows](https://www.python.org/ftp/python/3.12.1/python-3.12.1-amd64.exe).

   Follow the installation instructions.
   You can also download by going straight to website:

    ```
    https://www.python.org/downloads/
    ```

2. Open the terminal, perferably ***Windows PowerShell***


   PowerShell comes by default in latest versions of windows, if you do not have PowerShell installed, see instructions here


   verify that the python is working and confirm the version 
    ```
    python --version
    ```

    output should be like this `Python 3.12.1` depending on latest version installed.

   
     if windows doesnt recognize the command than

     * Either you have not installed python correctly or else
     * Python is not added to `PATH` variable. See how to add to `PATH` variable at the end.

   ### Update/install `pip`
3. `pip` comes pre installed with python however you can still install it with a simple command
    ```
    python -m pip install --upgrade pip
    ```
    this will automatically update `pip` to latest version
  
    confirm the version using this command
    ```
    pip -V
    ```
    The output will look like this

     `pip 23.3.2 from D:\Python312\Lib\site-packages\pip (python 3.12)`

    `{pip version}` from `{Path of the package (environment check)}` `(python version)`.


   ### Creating Virtual Environment using `venv`.
   
4.   A virtual Environment should be used whenever you work on any Python-based project.
     is generally good to have one new virtual environment for every Python-based project you work on.
     So the dependencies of every project are isolated from the system and each other. We will learn how to create a virtual environment using `venv`.
      *  Create the Virtual environment using
          ```
          python -m venv .myvenv
          ```
      *  activate the virtual environment using
          ```
          .myvenv\Scripts\activate
          ```
          In `PowerShell` activating the environment will add `(myvenv)` prefix to the command line.
           Now you can work on your project. Installing specific `Packages`, sometimes different version your project might be compatible with.

         This is usually done using `pip` command 
      *  deactivate the virtual environment simply typing
          ```
          deactivate
          ```
   ### Confirming the Virtual Environment
5. There are alot of ways to confirm that you are in the Virtual Environment     
      *   `(myvenv)` prefix to the command line.
      *    `pip -V` commands gives us the `pip` version as well as the current environment path. 
      *    Within python program, `import sys` the variable `sys.prefix` contains the path of current environment where as `sys.base_prefix`
            contains path of the system environment. if `sys.prefix != sys.base_prefix` comes out `True` it means you are in a virtual environment.
            Otherwise you will be in the system environment.
                  
   ### Unable to activate the Virtual Environment
 If you are unable to run the `.myvenv\scripts\activate` the problem might mention _unable to run scripts_.
  
      The solution could be a simple command. Open the `PowerShell` as _Administrator_ and run the command
      
      ```
      set-executionpolicy remotesigned
      ```
      
      This will allow scripts on your System.
   ### Adding to `PATH`  
 `PATH` is a system environment variable. When you enter a command in prompt some commands work regardless of your present working directory.
      How is this possible? Actually the System has a environment variable `PATH` which has all the `values`:_Paths of all commands_ which could be run in any location.
      There are two ways to add a path to `PATH` variable if not added by default we will only discuss the easy one.
    *    Using User Interface: type _environmental variables_ in the windows search panel and open the setting. Go to `Environment Variables...` option in the bottom right corner.
         Under _User variables for User_  select `Path` variable. Select `Edit` and `Add` new path. Save the changes and you are good to go.
        
      
        Now you can Run commands directly in CMD which ever are in the added path folder.
    
   
