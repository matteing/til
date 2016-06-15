# How to open a Django REPL inside a virtualenv using SublimeREPL
I found some instructions online to use a Django shell inside SublimeREPL, but they didn't apply for virtualenv, which was screwing up the setup due to it not finding config files and some python path issues.

I hacked together a script to fix it, making it compatible with virtualenv.


In the root of your project, create a file called shell.py, containing the code in the following code:

    import os
    import sys
    import django
    
    # The path to your project
    path = '/home/sergio/Projects/alphasquare/alphasquare'
    if path not in sys.path:
        sys.path.append(path)
    
    # Change to your project settings root
    os.environ.setdefault("DJANGO_SETTINGS_MODULE", "alphasquare.settings")
    
    django.setup()

Now, when you want to open a shell inside Sublime, all you have to do is open a REPL inside your virtualenv using Tools > SublimeREPL > Python > Virtualenv, then run the following code to execute a shell:

    exec(open('shell.py').read())
    
That's it! You now have a fully working django shell inside your sublime text editor. Happy hacking!

![REPL inside venv](http://i.imgur.com/ClQhazx.png)
