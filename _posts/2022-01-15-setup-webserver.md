---
layout: post
title: Setting up a web server in an EC2
date: 2022-01-15 15:09:00
description: An article on installing programs to use an EC2 machine as a webservers
tags: web-development programming
categories: web-dev
---

## SSH Connection
Refer [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)
{% highlight bash lineos %}
ssh -i "~/Downloads/aws_webserver.pem" ubuntu@ec2-3-83-163-243.compute-1.amazonaws.com
{% endhighlight %}

## Install MongoDB
Refer [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

{% highlight bash lineos %}
wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo systemctl start mongod
sudo systemctl status mongod
{% endhighlight %}


##### Setup authentication for mongodb (optional)
Refer. 
- [https://docs.mongodb.com/manual/tutorial/configure-scram-client-authentication/](https://docs.mongodb.com/manual/tutorial/configure-scram-client-authentication/)
- [https://docs.mongodb.com/manual/reference/connection-string/](https://docs.mongodb.com/manual/reference/connection-string/)

Open a mongo shell with - `mongosh` 

Run the following in the mongo shell
  {% highlight mongo lineos %}
  use admin
  db.createUser(
    {
      user: "myUserAdmin",
      pwd: "myPassword", // or cleartext password
      roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
    }
  )
  db.adminCommand( { shutdown: 1 } )
  {% endhighlight %}

Exit mongosh with `Crtl+ C` and run the following in a normal shell

{% highlight bash lineos %}
sudo nano /etc/mongod.conf
# add the following lines ###########
security
  authentication: enabled
#####################################
sudo systemctl restart mongod

# how to connect after enabling auth
mongosh --port 27017 --authenticationDatabase "admin" -u "myUserAdmin" -p "myPassword"
# change mongodb URL in the server config too
{% endhighlight %}

In case of errors try the following

{% highlight bash lineos %}
sudo chown -R mongodb:mongodb /var/lib/mongodb
sudo chown mongodb:mongodb /tmp/mongodb-27017.sock
sudo service mongod restart
sudo systemctl status mongod
{% endhighlight %}


## Install NodeJS
`sudo snap install node --classic`

### Transferring files
`sudo snap install wormhole`

> **Important** wormhole is named magic-wormhole in mac. You have to install in your local machine to upload the files

`wormhole receive <received code>` 
## Install packages
{% highlight bash lineos %}
cd react-express-project
npm i
cd client
npm i
npm run build
{% endhighlight %}

Set up Nginx. 
{% highlight bash lineos %}
sudo apt install nginx
sudo service nginx start
sudo service nginx status

sudo nano /etc/nginx/sites-available/default
sudo systemctl restart nginx
{% endhighlight %}

### Nginx server configuration 
Refer [https://www.nginx.com/resources/wiki/start/topics/examples/full/](https://www.nginx.com/resources/wiki/start/topics/examples/full/) and edit the 
 `/etc/nginx/sites-available/default` file with the following.

{% highlight text lineos %}
server {
    index index.html index.htm index.nginx-debian.html;
    server_name example.com www.example.com;

    location /
    {
      proxy_pass http://localhost:5000;
      proxy_buffering         on;
    }
}
{% endhighlight %}

## Run Server
Refer [https://www.dev2qa.com/how-to-run-node-js-server-in-background/](https://www.dev2qa.com/how-to-run-node-js-server-in-background/)
{% highlight bash lineos %}
nohup node server.js  > output.log & disown
{% endhighlight %}


## Additional Resources
- Run nodejs in the background using [PM2](https://pm2.keymetrics.io/docs/usage/pm2-doc-single-page/)
- [https://medium.com/idomongodb/how-to-npm-run-start-at-the-background-%EF%B8%8F-64ddda7c1f1](https://medium.com/idomongodb/how-to-npm-run-start-at-the-background-%EF%B8%8F-64ddda7c1f1)
- [https://medium.com/geekculture/deploying-a-react-app-and-a-node-js-server-on-a-single-machine-with-pm2-and-nginx-15f17251ee74](https://medium.com/geekculture/deploying-a-react-app-and-a-node-js-server-on-a-single-machine-with-pm2-and-nginx-15f17251ee74)
- [https://keithweaverca.medium.com/setting-up-mern-stack-on-aws-ec2-6dc599be4737](https://keithweaverca.medium.com/setting-up-mern-stack-on-aws-ec2-6dc599be4737)
- [https://unix.stackexchange.com/questions/420594/why-process-killed-with-nohup](https://unix.stackexchange.com/questions/420594/why-process-killed-with-nohup)