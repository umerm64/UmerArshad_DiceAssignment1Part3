# UmerArshad_DiceAssignment1Part3
Docker Volumes 

# Step 1
New docker volume is created using the command:
`docker volume create my_volume`

# Step 2
The container is run with `my_volume` mounted inside the container:
`docker run --mount source=my_volume,destination=/usr/share/nginx/html/ -p 8080:80 nginx`

# Step 3
The nginx welcome page is visible.

# Step 4
A minimal `index.html` is created.

# Step 5
`docker cp index.html infallible_neumann:/tmp/vol/`
Successfully copied 2.048kB to infallible_neumann:/tmp/vol/

# Step 6
The updated `index.html` is accesible.

# Step 7
`docker stop infallible_neumann`
`docker rm infallible_neumann`

# Step 8
`docker run --mount source=my_volume,destination=/usr/local/apache2/htdocs/ -p 8081:80 httpd`

# Step 9
The httpd default page is accesible.

# Step 10
File created about.html

# Step 11
`docker cp about.html pensive_sinoussi:/usr/local/apache2/htdocs/`
Successfully copied 2.048kB to pensive_sinoussi:/usr/local/apache2/htdocs/

# Step 12
about.html is accessible on /about.html

# Step 13
docker stop pensive_sinoussi
docker rm pensive_sinoussi

# Step 14
The files are available:
`sudo ls /var/lib/docker/volumes/my_volume/_data`
about.html  index.html

# Step 15
docker volume rm my_volume
