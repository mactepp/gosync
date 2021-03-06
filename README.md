Added Features
---------------

1. Fixed ``wxSimpleApp deprecated`` warning.

2. Tray Icon: Click to hide or show the window, right click to enable/disable the sync process or to exit the program

3. ``user_settings.yaml`` file: (copy to ``$HOME/.gosync/`` folder along with your ``client_secrets.json`` file)

    ``saveCredentials``: True if you want to save your credentials. Default: ``False``
    
    ``syncFolder``: Folder to save your files. Default: ``$HOME/Google Drive.``
    
    ``syncInterval``: Number of seconds between syncs. Default: ``600``.
    
    ``syncOnStart``: True if you want to start the sync process when starting GoSync. Default: ``False``

Instructions
------------

#### Install

There's one tricky dependency to be installed.

If you are using Ubuntu, simply run this command

    sudo apt install python-wxgtk3.0

If you are using something else, read more [here](https://wiki.wxpython.org/How%20to%20install%20wxPython).

Finally, run these commands

    git clone https://github.com/blegora/gosync
    cd gosync
    sudo python setup.py install
    
Dependencies should be already installed. If you get any import errors, refer to the depencies section below

#### Running

Add your ``client_secrets.json`` in ``.gosync`` folder

Then run ``GoSync &``

#### Configuration

The default ``user_settings.yaml`` file will be created if you don't provide it.
You can do further configuration by editing it on your ``.gosync`` folder.

Original Readme:
----------------

GoSync is an open source Google Drive client for Linux written in python language.
It's not perfect yet but it does the job. GoSync is released under GNU GPL version 2.0.

What it does?
------------
It syncs everything from the drive. By default, the sync is turned on. You can pause
it by clicking "Pause/Resume Sync" menu item. GoSync also monitors for the file changes
in the local mirror directory. When a new file is created in local mirror, it is
immediately uploaded to the Google Drive.

GoSync does the sync every 10 minutes. It is not configurable right now. This is called
as "regular sync".

There are some limitations as of now:
1. You cannot choose which directories to sync.
   It just syncs everything.
2. While its calculating the drive usage, the progress
   is not shown. If the usage of drive is high, it takes
   time to calculate the total categorical usage.

This will be fixed in future versions.

What you need to make it work?
------------------------------
Starting from version 0.3, GoSync is available for installation via pip. Simply run:

pip install GoSync

This will also install the dependencies.

If you have cloned the source from GitHub, the dependencies should be installed manually.
You need to install the following libraries before using GoSync:

1. python (version >= 2.7. Version 3 not tested yet)
2. wxPython  (version >= 2.8)
3. python-googleapi
4. pip
5. watchdog (to be installed from pip)
6. PyDrive (to be installed from pip)

There is one more essential thing. The "client_secrets.json" file. I am not distributing
my "client_secrets.json" because I am not distributing GoSync commercially.

A very good get started page can be found at (https://developers.google.com/drive/web/quickstart/python)
and a step-by-step process at (https://github.com/jay0lee/GAM/wiki/CreatingClientSecretsFile).

When you are done creating the client_secrets.json file, download it and keep it inside
.gosync directory in your home directory.

In case you have some problem you can send me mail at hschauhan at nulltrace dot org or
hs dot chauhan at gmail dot com.

Where to get the code?
----------------------
The code is being maintained as a github project. You can either clone the project from github or you
can download the zip file. The following is the github page for GoSync:

https://github.com/hschauhan/gosync

A Request
---------
Please help in improving this project. You can send me patches at hschauhan at nulltrace dot org. If you
can't write the code and you find something more or something non-functional, please create a bug on github
page. I will see if I can fix that as soon as possible. Since I work on this project in my free time, I
can't tell when exactly I will be able to honor your request. But rest assured I will.
