# Overview

This charm deploys [wildfly] application server in standalone mode. It uses openjdk-7 for it's java depedencies. The current version supports the mysql connectivity. You can add mysql relation by using juju add-relation command. Connectivity to the database is established through the mysql connector which is deplyoed when mysql relation is added.


##Usage

###Deployment steps
Once the juju environment is bootstrapped. Proceed with following steps.

This command deploys the charm in your juju environment.

    - juju deploy wildfly

To destroy the wildfly charm instance you need to run the following command

    - juju destroy-unit wildfly/(instance no.)

To destroy the wildfly service run the following command

    - juju destroy-service wildfly

to expose the wildfly charm run the following command

    - juju expose wildfly
To connect the mysql database you need to deploy the mysql charm 

    - juju deploy mysql

And add the database relation using the following command

    - juju add-relation mysql wildfly


##Configurations

###Configurable options

This wildfly charm allows you to create admin user and assign password by using the following configurable variables

    - username
    - password

##Network
This charm configures the wildfly server to listen for all ipv4 addresses for public and management interfaces.

###Accessing the web console
The management console will be available at  http://server-ip:9990
For the first time when you try to access the management web console it will take you to a page which says wildfly server is running but you need to create a user to access the console.
The default username is "admin" (however you can change it any time using the command given below), there is no default password set so you need to set the password explicitly inorder to log into the management console.

To set a custom username (optional step if u are fine using admin as username)

    -juju set wildfly username=desired_name

To set a desired password (a must do step, inorder to be able to accessi the management web console)

    -juju set wildfly password=desired_password

##Contact Information

###Author Contact Information
    - Author Name : Saurabh
    - Email ID    : saurabh.kumar@techblue.co.uk

###Wildfly Server Contact Information
    - [ wildfly website ] (http://wildfly.org)
    - [ wildfly documentation ] (https://docs.jboss.org/author/display/WFLY8/Documentation)
    - [ wildfly bug tracker ] (https://issues.jboss.org/browse/WFLY)
