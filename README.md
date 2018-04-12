# Udacity Full Stack Web Developer Nanodegree

## Linux Server Configuration

By Patrick Roche | [github.com/plr108](https://github.com/plr108) | [patrick.l.roche@gmail.com](mailto:patrick.l.roche@gmail.com)

### Project Overview

This repository contains my submission for the Linux Server Configuration project of the [Udacity Full Stack Web Developer Nanodegree](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004).

### Udacity Grader Access and Project Info

IP Address: 18.188.159.138

SSH Port: 2200

Web Application URL: http://ec2-18-188-159-138.us-east-2.compute.amazonaws.com/

### Software (Ubuntu Packages) Installed
* apache2
* libapache2-mod-wsgi
* postgresql
* postgresql-contrib
* python-dev
* python-flask   
* python-flask-sqlalchemy
* python-oauth2client
* python-psycopg2     
* python-requests

### Configuration Changes Made
1. UncomplicatedFirewall (UFW) was configured to only allow traffic on ports 80, 123, and 2200.

2. The OpenSSH config file (/etc/ssh/sshd_config) was modified to only listen on port 2200; `PermitRootLogin` in the file was changed to `no`.

3. An account called grader was created, given a password, and given sudo privileges.

4. A ssh key pair was generated using ssh-keygen on another machine; the contents of the public key were added to /home/grader/.ssh/authorized_keys on this server.  The .ssh folder was given `chmod 700` (user read, write, and execute) permissions.  The authorized_keys file was given `chmod 644` (user read and write, group and other read) permissions.

5. The URL for the server was determined using `nslookup`.  Google OAuth 2.0 credentials for the project were updated to add the server to the Authorized JavaScript origins and Authorized redirect URIs permission lists.

6. The item catalog project was pulled to the following location using git: /var/www/catalog

7. A postgresql account was created for the grader, given a password, and given superuser privileges.  The project database was created and category records were added using python scripts and the grader account credentials.

8. A new apache2 site configuration file (/etc/apache2/sites-available/catalog.conf) was created for the project.  The catalog site was enabled and the default site was disabled.

9. Third Party Resources Used to Complete This Project
* Amazon Lightsail Documentation
* Apache2 Web Server Documentation
* Ask Ubuntu
* Digital Ocean Community Tutorials
* Flask mod_wsgi (Apache) Documentation
* Stack Overflow
* Ubuntu Documentation
