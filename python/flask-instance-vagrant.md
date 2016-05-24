# How to run a Flask instance in Vagrant

Since Vagrant is an isolated environment, there are several steps you need to do before Vagrant can run in your environment.

1. To get things up and running quickly, set up a port forward in your Vagrantfile by uncommenting this line:
   
   `config.vm.network "forwarded_port", guest: 8000, host: 8080`
 
2. Do `vagrant up && vagrant ssh`.
3. After you are in the environment, run a `sudo apt update` and subsequently `sudo apt install virtualenv`. This updates your repositories and installs Python virtualenv.
4. Change directory to `/vagrant`, your working directory. Create a virtual environment by running `virtualenv flask -p python3`.
5. In your Flask app's runner, use these parameters:
   
   `app.run(port=8000, host='0.0.0.0', debug=True)`
6. Run the app and you should be set!
