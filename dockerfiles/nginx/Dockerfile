FROM nginx

#install nginx
RUN apt-get update && apt-get -y upgrade


#Removes the existing configuration file
RUN rm /etc/nginx/conf.d/default.conf 

#Replaces the desired configuration
COPY ./default.conf /etc/nginx/conf.d/ 

#Adding SSL Selfsigned files to configuration
COPY ./nginx-selfsigned.crt /etc/ssl/certs/ 
COPY ./nginx-selfsigned.key /etc/ssl/private/
