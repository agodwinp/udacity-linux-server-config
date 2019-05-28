# 3. Linux Server Configuration

This repository will guide you through how to set up a Ubuntu Linux VM using Amazon Lightsail, and access my deployed item-catalog application from the server.

***

## Design

Include architecture and code design diagrams.

***

## Setup

### Starting Ubuntu Linux VM

Include set up steps from the Udacity project page.

### Software Installed

#### Update Package Source List

    $ sudo apt-get update

#### Update Currently Installed Packages

    $ sudo apt-get upgrade

#### Remove Unused Packages

    $ sudo apt-get autoremove

### Configurations

#### Public/Private Key

Use ssh-keygen to generate a private/public key pair on your local machine.

Use the browser to SSH into the Linux VM. In the root directory, create a directory called `.ssh`.

    $ sudo mkdir .ssh

Create a file called `authorized_keys`.

    $ sudo touch authorized_keys

Return to the public key that has been generated on your local machine, and view the key using:

    $ cat ~/.ssh/item-catalog.pub

Copy this entire key into the `authorized_key` file within the VM using:

    $ sudo nano ~/.ssh/authorized_keys

Restart the VM. 

From a terminal window, ssh into the VM using this command:

    $ ssh ubuntu@3.8.116.47 -i ~/.ssh/item_catalog

#### Firewall

First, block all incoming requests.

    $ sudo ufw default deny incoming

Allow all outgoing requests.

    $ sudo ufw default allow outgoing

Allow ssh.

    $ sudo ufw allow ssh
    $ sudo ufw allow 2200/tcp

Allow HTTP (port 80)

    $ sudo ufw allow www

Allow NTP (port 123)

    $ sudo ufw allow 123/tcp

#### Users

Create a new user called `grader`

Firewall, users, database etc...

***

## Usage

How to connect to application.

***

## Authors

Arun Godwin Patel