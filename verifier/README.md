#Follow My Vote - ID Verification
This is the website interface for the follow my vote ID Verification

###How to run this site:
1. Install Python 2.7 (https://www.python.org/download/releases/2.7/) and pip (https://pip.pypa.io/en/latest/installing.html) if not already installed
2. Change to the root directory which is vote\verifier ..
3. Create a new virtual environment: virtualenv env
4. Activate the virtual enviroment: .\env\scripts\activate or bin/activate depening on your os
5. Install Dependencies: pip install -r requirements.txt
6. Make sure the voter database pointed to by DB_CONNECTION_STRING in settings.py is valid.  The voter.db file referenced in this setting by default is **NOT** included in this repository because it contains sensitive data.  There is a sample_voter.db file in the data directory which contains a small amount of sample data which can be used, this database does not contain any real voter information.
7. Start the Development Server: python runserver.py
8. Connect to Site:  http://localhost:5555

Settings can be found in settings.py. You may also need to change the api host address.


###Installation on apache
1.  If modwsgi is not installed on apache follow the directions on this page: https://code.google.com/p/modwsgi/wiki/QuickInstallationGuide
2.  Follow the directions from **How to run this site** above to make sure that the site is installed correctly, and you can run it from the development sever
3.  Configure the verfier.wsgi file located in this directory.
    * Change the **activate_this** variable to set the path to the activate_this.py script located in /scripts or /bin of the vitual environment directory
    * Change the **path_to_site** variable to set the path to the site, this should be the same directory in which the .wsgi file is located
4.  Configure Apache:  
    * Follow instructions located on this page: http://flask.pocoo.org/docs/0.10/deploying/mod_wsgi/#configuring-apache
    * Add **WSGIScriptReloading On** to your directory config to allow the server to reload when changes are detected

A restart of apache may be needed.  If you run into problems consult the page: http://flask.pocoo.org/docs/0.10/deploying/mod_wsgi/ for additional help




