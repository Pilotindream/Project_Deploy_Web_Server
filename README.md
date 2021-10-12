# Deploying to a Web-Server
First of all, [here](https://github.com/Pilotindream/Jenkins.git) you can see web-site that I will deploy to a target server.

## I divided my Project in to three main parts:
*Below, I am going to describe you, in a few words, what has been done  on each part.*


1. Jenkins
After starting Jenkins in container, I created a pipeline that checks whether there is changes in GitHub repo and publish over SSH files to the web server. Also, there is four Ansible playbooks that starts in my pipeline: a) Launch AWS EC-2 target server. b) Install Docker to the target server. c) create all necessary folders and setting permissions to them. d) Running an Apache Web Server in a container. 
*To see Pipeline and screnshoots go to the folder "Jenkins"*
*To see Ansible playbooks go to the folder "Ansible"*


2. Docker  
On Master Machine Jenkins was started in container ( docker run -p 8080:8080 -p 50000:50000 -v /home/ubuntu/jenkins_volume:/var/jenkins_home jenkins ), and Apache2 was started in container on Web-Server machine (  docker run -d --name my-apache2 -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4 ).
*To see additional screenshots go to the folder "Docker"*


3. AWS  
All of instances in this project are running in AWS. Security groups were created to make all conections more secure.  
*To see additional screenshots go to the foler "AWS"*

****
This is link to my website 3.69.91.150:8080 to check for changes during presentation

****
Thank you!

