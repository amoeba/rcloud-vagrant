# Vagrantfile setup for RCloud

This Vagrantfile (http://www.vagrantup.com) creates a virtual machine, configures, and provisions it with the necessary software to run your own instance of RCloud (https://github.com/cscheid/rcloud).

## Pre-requisites

There should be just two things you'll need to have before starting:

- Vagrant (http://www.vagrantup.com)
- Virtual Box (http://www.virtualbox.org)

As outlined in the RCloud documentation, we need to set up a GitHub application for RCloud. Once you've done that, run the following commands on the your local computer (replacing the appropriate values):

    $ export RCLOUD_GITHUB_CLIENT_ID={YOUR CLIENT ID HERE}
    $ export RCLOUD_GITHUB_SECRET={YOUR SECRET HERE}

I have configured the Vagrantfile to read the Client ID and Secret from the user's environment variables.

## Installing

Clone this repository to your local computer by running

    $ git clone https://github.com/amoeba/rcloud-vagrant

Change directories into the location you've cloned `rcloud-vagrant` and run

    $ vagrant up

You should see Vagrant download, configure and provision the virtual machine and this step may take some time, depending on connection and computer speed.

If everything has finished without error, you should now be running RCloud. Open a WebSockets-able browser and navigate to

    http://127.0.0.1/login.html

and enter your GitHub username and click the Login button. You should now be staring at RCloud.