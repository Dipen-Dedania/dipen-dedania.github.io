---
date: 2018-08-09
title: Deploy GO application on Google Compute Engine
categories: dev
tags: [development]
---

Hello There!

# Create Instance
https://console.cloud.google.com/compute/instances

# Generate and Add SSH key
https://console.cloud.google.com/compute/metadata

# Connect app with Filezilla & Putty

# Install Go

# Set GOPATH
export $GOPATH=/var/www
export $GOROOT=/usr/local/go

export PATH=$GOPATH/bin:$GOROOT/bin:$PATH
export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

# Upload Code

# Set firewall rule for 8081

gcloud compute firewall-rules create default-allow-http-8081 --allow tcp:8081 --source-ranges 0.0.0.0/0 --target-tags http-server --description "Allow port 8081 access to http-server"

# Create Service 

## create /etc/systemd/system/myservice.service

[Unit]
Description=my amazing service

[Service]
Restart=always
RestartSec=3
WorkingDirectory=/var/www/src/zuru.tech/jobs/
ExecStart=/var/www/src/zuru.tech/jobs/main 

[Install]
WantedBy=multi-user.target

## enable service
systemctl enable myservice

## start/stop
sudo systemctl start myservice
sudo systemctl stop myservice
sudo systemctl status myservice
sudo systemctl restart myservice

## Install Openssl
https://www.howtoforge.com/tutorial/how-to-install-openssl-from-source-on-linux/


# Openssl

## with password
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -subj '/CN=localhost'

## W/o password
openssl req  -nodes -new -x509  -keyout server.key -out server.cert


# Quick cmd
/var/www/src/zuru.tech/jobs/cmd
/etc/ld.so.conf.d/


