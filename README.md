# Docker_Project_joomla
This is the final project using Docker to set-up a WebApp called Joomla. I will explain you the whole process that has been done for creating the WebApp.

# What's Joomla :
Joomla is a free and open-source content management system (CMS) for publishing web content. It is built on a model–view–controller web application framework that can be used independently of the CMS. Joomla is written in PHP, uses object-oriented programming (OOP) techniques and software design patterns, stores data in a MySQL, MS SQL, or PostgreSQL database, and includes features such as page caching, RSS feeds, printable versions of pages, news flashes, blogs, search, and support for language internationalization.

# Pre configurations:
# i] Download Redhat 8 Linux 
# ii] Download the Docker tool
First of all configure the yum command in linux and download the software by

     yum install docker-ce --nobest 

and start the docker by command

     systemctl start docker.
     
Disable Filrewall: Disabling firewall is not a good choice but, whenever you try to run any network based service then the firewall may block it and the service won't work properly. So, you have to disable firewall for implementing network based services to system. Use the following command to stop firewall systemctl stop firewalld Use the following code to disable the firewall permanently until you start it systemctl disable firewalld You can check the status of firewall by command systemctl status firewalld Use the following command to start firewall systemctl start firewalld.

# Run Docker:
For moving towards the project we have to enable docker service in the system so that we can use it. To start docker, use command systemctl start docker You can use this command to enable docker permanently systemctl enable docker You can check the status of docker by command systemctl status docker To stop docker, use command systemctl stop docker.

# Download the Required Images
Download The joomla and MySQL image from https://hub.docker.com using

      docker pull joomla:latest
      docker pull mysql:5.7 
      
# Setting up MySQL:
Use the code given below and it will create a user with a database inside Your MySQL Server. 

        docker run -it -e MYSQL_ROOT_PASSWORD=(password of your choice) -e MYSQL_USER=(username you have given) -e MYSQL_PASSWORD=(password you have given) -e MYSQL_DATABASE=(name of the database) --name onkardb mysql:5.7
        
# Docker-Compose :
Install a docker-compose software from https://docs.docker.com/compose/install. Make a compose file using

           mkdir /mycompose
           
 You can create/edit your docker-compose file using
 
           vim docker-compose.yml
           
  The file name should always be docker-compose.yml.
  
Version :
         
         Each version has different syntax. This version supports docker-compose fine.

Services :
             
             In service, which containers we want to run.

Containers :
            
            dbos and cloudos are the name of docker container. Docker-compose will automatically create the specified name containers.

Image :


# Running Joomla WebApp:
Open the browser and type localhost:80 or localhost in the address bar and you will be able to see your Joomla WebApp. Note: If you want to use any other port then you have to mention it in your docker-compose file.
  
  
