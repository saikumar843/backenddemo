FROM ubuntu

#install nginx
RUN apt-get update && apt-get -y upgrade && apt install -y nginx

#Run nginx
RUN service nginx start

#Removes the existing configuration file
RUN rm /etc/nginx/sites-available/default 

#Replaces the desired configuration
COPY ./default /etc/nginx/sites-available 

#Adding SSL Selfsigned files to configuration
COPY ./nginx-selfsigned.crt /etc/ssl/certs/ 
COPY ./nginx-selfsigned.key /etc/ssl/private/

CMD ["nginx", "-g", "daemon off;"]