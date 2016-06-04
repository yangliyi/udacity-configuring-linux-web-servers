# L3 Web Application Servers
## Vagrant Prerequisites
If you’re using the Vagrant virtual machine from earlier in this course you will need to make a slight modification to the configuration of this machine to make your web server accessible. This step is not related to configuring a web server in general, it’s just a condition of our current environment. You would not need to complete this step if you were configuring a machine from a cloud provider like Amazon Web Services.
Open the Vagrantfile in your project directory and look for the following section near lines 20-23:

```
Create a forwarded port mapping which allows access to a specific port
within the machine from a port on the host machine. 
In the example below, 
accessing "localhost:8080" will access port 80 on the guest machine.
```
### `config.vm.network "forwarded_port", guest: 80, host: 8080`
Add the following directly below those comments: config.vm.network :forwarded_port, guest: 80, host: 8080
Save the file and start your Vagrant virtual machine using the vagrant up command. If your virtual machine is currently running, you can reload it using the vagrant reload command.
This configuration change will setup port forwarding from port 8080 on the host machine (your computer) to the guest machine (your Vagrant virtual machine) when your virtual machine is running. This will allow you to access your web server using the URL http://localhost:8080.

## Installing Apache
You’ll setup your web application server one piece at a time, testing each as you progress. The first step is to get your server responding to HTTP requests. To do this, you’ll use **Apache HTTP Server** - the most commonly installed web server on the Internet with roughly 47% market share.
Install Apache using your package manager with the following command: 

`sudo apt-get install apache2`

Confirm Apache is working by visiting http://localhost:8080 in your browser. 