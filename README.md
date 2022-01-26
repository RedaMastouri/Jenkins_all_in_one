# Learn DevOps

CI/CD with Jenkins using Pipelines and Docker

# Recources

Procedure Document
Learn DevOps: Jenkins - Procedure document

DigitalOcean Installation Procedure
This is just a summary, for the demo, see lecture 5: Demo - Jenkins Installation

Summary
Create DigitalOcean account

Create Droplet
Jenkins install
Configuration until you hit main screen

 Full list of installation parameters: see https://hub.docker.com/_/jenkins/

Create DigitalOcean Account
Sign-up using https://m.do.co/c/007f99ffb902 to get $10 in credit to use on a droplet

Create droplet
with the $10 credits you can run a 1 GB memory droplet for 1 month, a 2 GB for at least 2 weeks and a 4 GB droplet for at least 1 week. The 4 GB memory droplet is recommended

Choose for ubuntu 20.04.x

You can choose another system, but the instructions provided to install docker will only work on ubuntu 20.04

Install Docker
```
$ sudo apt-get update
$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
$ echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
$ sudo apt-get update
$ sudo apt-get install docker-ce docker-ce-cli containerd.io
```
 See also https://docs.docker.com/engine/install/ubuntu/

Install Jenkins
$ sudo mkdir -p /var/jenkins_home

$ sudo chown -R 1000:1000 /var/jenkins_home/

$ docker run -p 8080:8080 -p 50000:50000 -v /var/jenkins_home:/var/jenkins_home --name jenkins -d jenkins/jenkins:lts

 

Open browser and go to: http://IP:8080/ (change IP to your droplet IP)

You will be asked for initial password for the Jenkins, you can get this password by entering following command on your server.

 

$ cat /var/jenkins_home/secrets/initialAdminPassword


A screen with “Create First admin User prompt” will appear. You will need to enter a username, password, full name and email address.

Alternative Installation methods
Using a Vagrant box: https://github.com/wardviaene/devops-box

Works on Mac / Linux / Windows

Download virtualbox at www.virtualbox.org

Download vagrant at www.vagrantup.com

Download the repository, open a cmd/shell/terminal

cd into the project directory

Type “vagrant up”

Without tools, just a plain install on your Linux / Mac / Windows machine:

Download the package from https://jenkins.io/download/ and follow the instructions for your operating system

Resources for this lecture

