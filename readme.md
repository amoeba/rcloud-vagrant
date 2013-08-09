# Vagrantfile setup for RCloud

This Vagrantfile (http://www.vagrantup.com) creates a virtual machine, configures, and provisions it with the necessary software to run your own instance of RCloud (https://github.com/cscheid/rcloud).

## Pre-requisites

There are two things you'll definitely need to have before starting:

- Vagrant (http://www.vagrantup.com)
- Virtual Box (http://www.virtualbox.org)

As outlined in the RCloud documentation, we need to set up a GitHub application for RCloud (https://github.com/settings/applications). Once you've done that, edit the github_info.txt accordingly (more at https://github.com/cscheid/rcloud#github-authentication). This will likely just required editing the first two lines with your GitHub Client ID and Secret.

The Vagrantfile will then copy this file into the VM so RCloud can use it to authenticate.

## Installing

Clone this repository to your local computer by running

    $ git clone https://github.com/amoeba/rcloud-vagrant

Change directories into the location you've cloned `rcloud-vagrant` into and start the VM with

    $ vagrant up

You should see Vagrant download, configure and provision the virtual machine and this step may take some time, depending on connection and computer speed. If you have errors, please file an issue or contact me directly.

If everything has finished without error, you should now be running RCloud. Open a WebSockets-able browser and navigate to

    http://127.0.0.1:8080/login.html

and enter your GitHub username and click the Login button. You should now be staring at RCloud. Again, if you aren't, please get in touch.