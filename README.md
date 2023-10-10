# devops-Docker-for-Pro
in this work, we will go from Dockerfile to create our own docker image, then create a container and the accass our app through the browser


First you will need to create an ece instance in aws or create a VM in your cloud provider where you can install docker.
# ubuntu sever is recommended.

second, ssh into your new server and install ubuntu ( I will add a file for docker installation ) 



NOW, RUN THE FOLLOWING COMMANDS 
==>
mkdir app7 ( your app name ) 


#  then you need to create a simple file witch contents the message that you want to see in your browser when your app is deployed
==>
echo "HELLO WORLD, WELCOME TO DEVOPS BEST PRACTICE GUIDE" > index.html
or you can vi and create the same file.


The next step is to create a Dockerfile and vi into it
==>
touch Dockerfile 
vi Dockerfile 
# ( and add those two simple lines the first is for the base image and the second is just to copy what we have in our index.html) 
FROM nginx
COPY index.html /usr/share/nginx/html


CONGRATULATION, YOU JUST CREATED YOUR DOCKERFILE, NOW LET'S BUILD THE IMAGE AND DEPLOY OUR APP

to build the Docker image, we need to run this command, 
==>
docker build -t app7 ( your app name ) .
# this means that our Dockerfile is in our pwd, that is why we put .


let's finally create our very first container
==>
docker run -d -p 8080:80 app7 
# ( here, app7 is my image name so you will need to put your image name and in this case we did not specify any tag so the default tag will be latest ) 
YES YOU JUST DEPLOYED YOU VERY FIRST APP, 
now you can access it using curl localhost:8080 
or your public IP:8080 [ on your browser ] 
# in case you have some security issues, try to check your security group to allow the ports   !!!




































