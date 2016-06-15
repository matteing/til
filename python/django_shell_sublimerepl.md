# Opening a Django shell while on Sublime Text
I found some instructions online to use a Django shell inside SublimeREPL, but they didn't apply for virtualenv, which was screwing up the setup due to it not finding config files.

I hacked together a script to fix it, making it compatible with virtualenv.


In the root of your project, create a file called shell.py, containing the code in the following gist:
https://gist.github.com/fallenshell/d8bb7b01bf61b095965a28192c0a6d10

Now, when you want to open a shell inside Sublime, all you have to do is open a REPL inside your virtualenv using Tools > SublimeREPL > Python > Virtualenv, then run the following code to execute a shell:

    exec(open('shell.py').read())
    
That's it! You now have a fully working django shell inside your sublime text editor. Happy hacking!

![REPL inside venv](http://i.imgur.com/aCTj7V3.png)
