================================================================================
Welcome to MarkUs-VM project! MarkUs Installation Made Easy
================================================================================

http://markusproject.org/

MarkUs (pronounced "mark us") is an open-source tool which recreates the ease
and flexibility of grading assignments with pen on paper, within a web
application. It also allows students and instructors to form groups, and
collaborate on assignments. Its predecessor OLM (Online Marking) was originally
written in Python on top of the TurboGears framework.

1. Synopsis
================================================================================

The MarkUs-VM project aimed at facilitating MarkUs installation, both in
production (with nginx as webserver and unicorn as ruby backend) or in
development mode (with latest ruby and subversion build).

This project uses both Vagrant and Chef.

The virtual machine is provisionned by Chef Solo to contain everything needed
to start MarkUs. Vagrant is used as a wrapper to manipulate the virtual
machine. You can still access the virtual machine using VirtualBox GUI.

Chef
--------------------------------------------------------------------------------


Vagrant
--------------------------------------------------------------------------------



2. Install
================================================================================

1. Install Virtual Box <https://www.virtualbox.org/wiki/Downloads>

2. Install ruby and ensure you have rubygems installed too

3. Install Vagrant `gem install vagrant` or `sudo gem install vagrant`
   if ruby is installed system-wide.

4. Rename Vagrantfile.development or Vagrantfile.production to Vagrantfile
   (according to the mode you want to use)

Development
--------------------------------------------------------------------------------

5. Ensure you have properly forked MarkUs (on Github) repository and clone your
   MarkUs repository to ../Markus (you can modify the path to your Markus local
   repository in Vagrantfile (see the `config.vm.share_folder` option in
   Vagrantfile).

6. Start the build of your virtual machine using `vagrant up` command in the
   directory where the Vagrantfile is. The first time you run the `vagrant up`
   command, it can take a long time (your virtual machine will compile both
   subversion and ruby)

7. Once your virtual machine is up, you can access it using `vagrant ssh`
   command. **Note: development must be done with markus user, not with vagrant
   user.** You can log in with markus user by doing `sudo su - markus` once
   logged in with the vagrant user.
 
8. Please note that you will edit MarkUs source code on "your" computer, in the
   ../Markus directory and you will start the rails server on the virtual
   machine (using `bundle exec rails server`). Please refer to MarkUs
   documentation for more infos.

9. You can stop the virtual machine by running `vagrant halt`.

Production
--------------------------------------------------------------------------------

3. Links
================================================================================

* MarkUsProject website: http://markusproject.org/
* MarkUs-VM website: http://github.com/benjaminvialle/MarkUs-VM
* VirtualBox: https://www.virtualbox.org/wiki/Downloads
