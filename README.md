# Deploying to a Web-Server
First of all, [here](https://github.com/Pilotindream/Jenkins.git) you can see web-site that I will deploy to a target server.

## I divided my Project in to four main parts:
*Below, I am going to describe you, in a few words, what has been done  on each part.*

1. Ansible  
From my  Master machine( Jenkins-master 18.193.47.133 ) I lauched two EC2 instances. One instance for Node ( Node_1 3.120.250.107 ) and other one for an Apache web-server ( Web-Server 18.193.149.159 ).  
After that I installed Docker on the web-server, so that start web-server in container.  
*To see Ansible playbooks go to folder "Ansible"*


2. Jenkins
After starting Jenkins in container, I created a pipeline that checks whether there is changes in GitHub repo and publish, through the node, over SSH files to the web server.  
*To see Pipeline and screnshoots go to the folder "Jenkins"*


3. Docker  
On Master Machine Jenkins was started in container ( docker run -p 8080:8080 -p 50000:50000 -v /home/ubuntu/jenkins_volume:/var/jenkins_home jenkins ), and Apache2 was started in container on Web-Server machine (  docker run -d --name my-apache2 -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs/ httpd:2.4 ).
*To see additional screenshots go to the folder "Docker"*


4. AWS  
All of instances in this project are running in AWS. Security groups were created to make all conections more secure.  
*To see additional screenshots go to the foler "AWS"*

****
Thank you!

