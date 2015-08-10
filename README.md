# open-puppet-docker
Docker file for setting up open source puppet

Docker images - https://hub.docker.com/u/brandixi3/

Installation Steps for Puppet Master Server.

1. Generate New certificate using the below command, (Note : When it displays "Starting Puppet master version 3.8.1, the           certificate setup is complete. Press CTRL-C to return to the shell.)
   > sudo puppet master --verbose --no-daemonize

2. Start puppet Master using the command,
   > sudo service apache2 start

Installation steps for Puppet Dashboard,

1. Start MySQL Server,
   > /etc/init.d/mysql start

2. Crete Databse "puppet" by login to mysql server. (Note : Puppet Dashboard data base configuration file -               
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
   http://<<server:ip>>:3000
   
