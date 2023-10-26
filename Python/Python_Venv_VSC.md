
Contents:
1. VENV
2. FILEHANDLING IN VENV
3. REQUIREMENTS.TXT


1. VENV
=======

Install virtual env:

Navigate to folder holding pip (C:\Users\....Python3xx\Scripts) 
and type 

$ pip install virtualenv


VSCode direkt in einem Verzeichnis öffnen [aus dem Win CLI]:
$ code .

Python virtual environment anlegen [aus dem VSC-Terminal]:
$ python -m venv venv
--> das zweite venv ist hierbei der Name des virtuellen
Environments. Dieser kann auch anders lauten.
Siehe auch https://docs.python.org/3/tutorial/venv.html

Das neu angelegte venv nutzen (aktivieren) [aus dem VSC-Terminal]:
$ .\\venv\\Scripts\\Activate
--> Falls das erstellte Environment nicht venv heißt,
lautet der Befehl .\\name-des-venv\\Scripts\\Activate

--> Sollte der Befehl zu einer Fehlermeldung führen,
dann sucht man in der Windows-Suche nach 'skript'
und klickt auf 'Ausführung lokaler PowerShell-Skripte ohne
Signatur zulassen' und setzt den Haken bei der entsprechenden
Option.

Alternativ funktioniert auch dieser Befehl (IM COMMAND PROMPT):
$ ./venv/Scripts/activate
oder
$ "./venv/Scripts/activate"


Das venv wieder verlassen (nur PowerShell):
$ deactivate

Venv aus cmd verlassen (vom Projektordner aus):
$ ..\venv\Scripts\deactivate

Anmerkung:
Ein Virtual Environment (Kurzform: virtualenv oder ganz kurz: venv) dient zum Einrichten von ein oder mehreren unabhängigen Python-Umgebungen. Normalerweise werden alle Python-Module in die allgemeine Benutzer- oder Systemumgebung installiert.
----------------------------------------------

2. FILEHANDLING IN VENV?
========================

>>>>> QUESTION <<<<<<<

<a href="https://stackoverflow.com/questions/51499950/where-do-i-put-my-python-files-in-the-venv-folder">
    Where do I put my python files in the venv folder?</a>

Where do I put my python files in the venv folder?

(Probably a noob question, but I didn't find a solution after googling for 20 minutes.)

I created a new pure Python project with PyCharm which yielded the following folder structure

myproject
└── venv
    ├── bin
    │   ├── activate
    │   ├── activate.csh
    │   ├── activate.fish
    │   ├── easy_install
    │   ├── easy_install-3.5
    │   ├── pip
    │   ├── pip3
    │   ├── pip3.5
    │   ├── python
    │   ├── python3
    │   └── python3.5
    ├── include
    ├── lib
    │   └── python3.5
    ├── lib64 -> lib
    └── pyvenv.cfg
Where do I put myproject.py or the myproject folder now?

Inside or outside of venv?
In the venv/binfolder?
Just inside venv, i.e. myproject/venv/myproject.py?


>>>>> ANSWER <<<<<<

The virtual environment manages files which aren't yours. It doesn't care how you manage your own files. Put them wherever makes sense to you, just not anywhere inside the venv directory tree. Common solutions include directly in myproject, or in myproject/src.

For what it's worth, one of the important use cases for virtual environments is the ability to delete one and start over. You obviously can't do that if you put stuff there which isn't part of the virtual environment. Regard them as ephemeral infrastructure.

Another use case is the ability to have multiple virtual environments for the same project, so that you can test that your code works with different versions of the libraries you depend on, or even different Python versions.

A common convention is to collect the libraries you need in requirements.txt so that you can create a new virtual environment, activate it, and pip install -f requirements.txt whenever you need to.

I guess you misunderstood the term "Virtual Environment". It provides an isolated environment wherein you can download a different version of python packages and run it for your project. Hence, do not put anything inside your virtual environment. Keep it clean.

To take advantage of the virtual environment,

activate it (source path_to_virtual_env/bin/activate )
install the necessary python packages using pip (pip install XYZ)
and run your python code using python command (python3 mycode.py)



3. REQUIREMENTS.TXT
===================

https://frankcorso.dev/setting-up-python-environment-venv-requirements.html

Setting Up Your Python Environment With Venv and requirements.txt

Reading From and Writing to CSV Files in Python
By default, all the Python packages you install on your computer are used within all of your projects. But, what if one project requires version 1 of a package and another project requires version 2?

Or, if you have multiple people working on a project, how do you tell them which dependencies are needed and make sure everyone is using the same versions?

This is where using requirements.txt and virtual environments come in.

What Is requirements.txt?
When you usually install a package, you probably do something like:

pip install pandas

But, imagine if you have someone else working on the project and they also install pandas. Or, maybe you are deploying your project to Netlify or are using Docker. How do you make sure the right dependencies get installed and the correct version?

With requirements.txt, you can list all the required packages for your project and what version is needed. If you are familiar with NPM or Composer, you may have seen a similar concept in their package.json or composer.json files.

Creating Your requirements.txt
In your project, you can create a requirements.txt file. Inside, you can list each package that is needed.

matplotlib
numpy
openpyxl
pandas
To make it easy to scan and read, the list is normally alphabetical. If you want a specific version, you could add an equal sign like this:

matplotlib==3.3.3
numpy==1.19.3
openpyxl==3.0.5
pandas==1.0.5

Now, it would be challenging to manually write out all your dependencies and remember to change the version number when you upgrade. Luckily, pip can help with this.

If you ever want to see what packages you have installed, you can run pip list. This will output all the packages installed and their version numbers.

Package         Version
--------------- ---------
matplotlib      3.3.3
numpy           1.19.3
openpyxl        3.0.5
pandas          1.0.5

Even better, you can use pip freeze > requirements.txt to automatically take this list and store it in your requirements.txt file.

As you add, update, and remove packages, you can run that command again to update your requirements.txt file.

Installing From Your requirements.txt
Let's say you just cloned a git repo. This repo contains a requirements.txt file. What do you do next?

Once again, pip is here to help. We can run pip install -r requirements.txt to have pip automatically install all dependencies listed in the requirements.txt file.

Using Virtual Environments
Now, if you only have one Python project on your computer, this may be fine as-is. But, what if you start cloning or creating several projects all with their own requirements.txt files? You can quickly end up with package versions that are not compatible with each other.

This is where virtual environments come in. You can set up your project to exist within its own environment and packages only installed within that environment. Each project will have its own environment and its own packages installed within it.

To create your virtual environment, go into your project and run:

python -m venv .venv

The last parameter, .venv, is the name of the directory to install the virtual environment into. You can name this whatever you would like, but I like to stick with .venv as it's easy to tell what it is and it doesn't conflict with directory names I use with other systems.

Once the command is finished, your virtual environment will be ready. Next, you can "activate" it by running the activation script.

If you are on Windows, you will use .venv\Scripts\activate.bat.

On other OSes, you will use source .venv/bin/activate.

Once activated, you will see the name of the environment within the terminal.

(.venv) fpcorso:~$ pip install -r requirements.txt
Now, you will be able to install packages and run Python within the environment without interfering with packages installed globally.

Once you are finished, just use the deactivate command to exit the virtual environment.

Next Steps
Going forward, you will want to install a virtual environment within all of your projects and install packages within. Then, use the pip freeze > requirements.txt command to generate your requirements.txt file to keep everyone working on the project in-sync.
