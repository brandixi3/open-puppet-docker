# open-puppet-docker
Docker file for setting up open source puppet.

Docker images - https://hub.docker.com/u/brandixi3/

This image contains following S/W versions,

### Versions

* Puppet Master Server 3.8.1
* Ruby 1.8.7
* Bundler 1.1
* MySQL 5.6 

Installation Steps for Puppet Master Server.

1. Start the Docker container as follows,
   > docker run -p 80:80 -p 8140:8140 -p 3000:3000 -p 3306:3306 -h Docker-PUPPET-01 -t -i brandixi3/open-puppet-docker  /bin/bash

2. Generate New certificate using the below command, (Note : When it displays "Starting Puppet master version 3.8.1, the           certificate setup is complete. Press CTRL-C to return to the shell.)
   > sudo puppet master --verbose --no-daemonize

2. Start puppet Master using the command,
   > sudo service apache2 start

Installation steps for Puppet Dashboard,

1. Start MySQL Server,
   > /etc/init.d/mysql start

2. Create Databse "puppet" by login to mysql server. (Note : Puppet Dashboard data base configuration file -               
   /opt/puppet-dashboard/config/database.yml)

3. Move to the puppet-dashboard location,
   > cd /opt/puppet-dashboard

4. Generate a new secret_token in config/settings.yml: 
   > echo "secret_token: '$(bundle exec rake secret)'" >> config/settings.yml

5. To setup the Database,
   > bundle exec rake db:setup

6. To start the Puppet Dashboard,
   > bundle exec rails server

7. Access the puppet Dashboard,
   http://server_ip:3000
   
