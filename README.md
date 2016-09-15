# nexus
The purpose of this repository is to provide simple way to get started with developing application inside Virtual Machine locally. This sets up VM with installed NodeJS, postgres and running applications. By default applications are ran by supervisor and each has its own user and home like <app> stands for app name (either api or web):

    /usr/local/<app>

and code is under

    /usr/local/<app>/src

Instead of `localhost` use `192.168.50.4` to access the applications.

## make it work

Prerequisites for this to run are:
* Vagrant
* VirtualBox
* Ansible

To make it work clone other repositories to have a structure like this.

    api/            --> cloned api repository
    nexus/          --> this repository cloned
    superadmin/     --> cloned superadmin repository
    web/            --> cloned web repository

Simply then go into nexus/ and run

    vagrant up

If you are experiencing errors try running

    vagrant plugin install vagrant-host-shell
    vagrant plugin install nugrant

to ssh into VM you just run:

    vagrant ssh

##debug applications
By default applications (api and web) are ran by supervisor so to develop locally you can stop the service by running

    sudo supervisorctl <app> stop

to stop the service, then

    sudo su - <app>

to change to that application user which gets you to that user home so type `cd src` to get to where app code is `/usr/local/<app>/src` and from there just run the app

    npm start

## Local Development Access
Below are links to access the running applications locally:

* Api
  * [http://192.168.50.4:3000/](http://192.168.50.4:3000/)
* SuperAdmin
  * [http://192.168.50.4:7001/](http://192.168.50.4:7001/)
* Web
  * [http://192.168.50.4:7000/](http://192.168.50.4:7000/)
