# TryDocker
#Hello

#Created the directory called html and placed index.html to display a webpage
#Ran the below command from terminal to start the web server using nginx
docker run -v /Users/s0e02l3/git/TryDocker/html:/usr/share/nginx/html:ro -p 8080:80 -d nginx
