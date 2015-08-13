# open-puppet-docker
Docker file for setting up open source puppet.

Docker images - https://hub.docker.com/u/brandixi3/

This image contains following S/W versions,

### Versions

* Puppet Master Server 3.8.1
* Puppet dashboard
* Ruby 1.8.7
* Bundler 1.1
* MySQL 5.6 

Installation Steps for Puppet Master Server.

1. Start the Docker container as follows,
   > docker run -p 80:80 -p 8140:8140 -p 3000:3000 -p 3306:3306 -h Docker-PUPPET-01 -t -i brandixi3/open-puppet-docker  /bin/bash

2. After the whole setup completed you'll get a terminal output as follows,
   
   "=> Booting Thin
=> Rails 3.2.21 application starting in development on http://0.0.0.0:3000
=> Call with -d to detach
=> Ctrl-C to shutdown server
Thin web server (v1.6.3 codename Protein Powder)
Maximum connections set to 1024
Listening on 0.0.0.0:3000, CTRL+C to stop"
   
  Now you can access Puppet dashboard using , http://server_ip:3000
   
