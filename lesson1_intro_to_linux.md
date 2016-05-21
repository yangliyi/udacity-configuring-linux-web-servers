# L1 Intro to Linux
## Linux Distribution Comparison
* Red Hat Enterprise Linux
  * Large enterprise / corporate customers 
* Ubuntu
  * Ease of use on servers, desktops, laptops 
* Linux Mint
  * Desktop users with proprietary media support 
* CoreOS
  * Clustered, containerized deployment of apps
* Reference: 
  * <http://www.howtogeek.com/191207/10-of-the-most-popular-linux-distributions-compared/>

## Vagrant Commands
We’re now ready to get started working within our Linux virtual machine. If your download hasn’t completed from the initial setup, go ahead and take a break and come back when that has completed. You won’t be able to make further progress until the virtual machine is up and running as much of the course will take place within this environment.

Before we access our machine, let’s quickly review a few commands that vagrant provides to make managing your virtual machines much simpler. Remember, your vagrant machine lives within this specific folder on your computer so make sure you’re within that same folder your created earlier; otherwise these commands won’t work as expected.
### vagrant status
This command will show you the current status of the virtual machine. It should currently read “default running (virtualbox)” along with some other information.
### vagrant suspend
This command suspends your virtual machine. All of your work is saved and the machine is put into a “sleep mode” of sorts. The machines state is saved and it’s very quick to stop and start your work. You should use this command if you plan to just take a short break from your work but don’t want to leave the virtual machine running.
### vagrant up
This gets your virtual machine up and running again. Notice we didn’t have to redownload the virtual machine image, since it’s already been downloaded.
### vagrant ssh
This command will actually connect to and log you into your virtual machine. Once done you will see a few lines of text showing various performance statistics of the virtual machine along with a new command line prompt that reads vagrant@vagrant-ubuntu-trusty-64:~$

Here are a few other important commands that we’ll discuss but you do not need to practice at this time:
### vagrant halt
This command halts your virtual machine. All of your work is saved and the machine is turned off - think of this as “turning the power off”. It’s much slower to stop and start your virtual machine using this command, but it does free up all of your RAM once the machine has been stopped. You should use this command if you plan to take an extended break from your work, like when you are done for the day. The command vagrant up will turn your machine back on and you can continue your work.
### vagrant destroy
This command destroys your virtual machine. Your work is not saved, the machine is turned off and forgotten about for the most part. Think of this as formatting the hard drive of a computer. You can always use vagrant up to relaunch the machine but you’ll be left with the baseline Linux installation from the beginning of this course. You should not have to use this command at any time during this course unless, at some point in time, you perform a task on the virtual machine that makes it completely inoperable.

## Other Important Directories
* /root/
  * etc - where configuration files live
  * var - variable files
    * system and application logs
  * bin - executable binaries, accessible by all users
  * sbin - used by the root user for system administration and maintenance purposes.
  * lib - libraries support the binaries that are located around the system
  * usr - user programs.
  
## Understanding $PATH
* $PATH - the diredctories Linux will progress through and looking for a binary when you just type the name of it.
* Update $PATH: <http://askubuntu.com/questions/60218/how-to-add-a-directory-to-my-path>
  
  
    