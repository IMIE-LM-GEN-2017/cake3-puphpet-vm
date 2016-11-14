# Cake3 - Another vagrant vm
This is the configuration for the virtual machine used in the development of my cake3 projects.

## Requirements

This virtual machine requires

  - [VirtualBox](https://www.virtualbox.org/wiki/Downloads) version >=5.1.6
  - [Vagrant](https://www.vagrantup.com/downloads.html) version >= 1.8.6


## Installation

  - Download and unzip this in your working directory (i.e : `~/dev/my_project/`)
  - After installing VirtualBox and Vagrant, go to your working directory.

### First launch
**You'll need an active internet connection for this step**

  1. Create the `html` folder.
  2. Run `vagrant up` in the working directory. That will run the provisionner (setup of desired packages, server configuration, etc...).
  3. Have some coffee during the launch and edit your `hosts` file to add this line at the end: `192.168.56.200 my-cake3-project.dev`
    - Linux: `/etc/hosts`
    - Mac: need feedback, but it should be the same.
    - Windows: need feedback
  4. When done, test the virtual machine:
    - try `vagrant ssh` from console. You should land _in_ the VM. Type `exit` to quit it.
    - Open your browser and test the following adresses [http://192.168.56.200](http://192.168.56.200), [http://my-cake3-project.dev](http://my-cake3-project.dev). You should land on a dummy file.
  5. When the first launch is done, delete the `html/index` file and go to the next step.

### Install Cake

### Start/stop the vm:

  - To start the vm: `vagrant up`
  - To suspend it: `vagrant suspend`
  - To stop it: `vagrant halt`
  - To force stop: `vagrant halt -f`
  - To destroy the VM: `vagrant destroy`. Note that this command will preserve the development files, but you'll lose all the database.
  -
## Access the machine via SSH:

If you need to access the virtualbox via SSH, the simple way is to use `vagrant ssh`

If you need to access it ie, for Mysql Workbench, the public key is `puphpet/files/dot/ssh/id_rsa.pub`

## Machine specifications:

  - Ram: 512Mo
  - Host: training-fight
  - Ip adress: 192.168.56.200
  - Shared folders: `./` leads to `/var/www/`
  - User:
    - name: vagrant
    - password: 123
  - Apache:
    - Version: 2.4
    - Server name: my-cake3-project.dev _alias_ www.my-cake3-project.dev
    - Webroot: `/var/www/html`
  - PHP:
    - Version: 7.0
    - Modules: cli, intl, xml
    - Logs: `/var/log/php-fpm.log`
  - xdebug: port 9000
  - Mysql:
    - Version: 5.7
    - user: vagrant
    - pass: 123
  - Sqlite
  - Paquets supplémentaires:
    - vim
