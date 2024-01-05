#!/bin/bash


#!/bin/bash

# Server details
username="root"
server_address="192.168.144.191"
#private_key_path="your_private_key_path"

# Docker image details
docker_image="httpd"

# SSH into the server and run Docker image
#ssh -i "$private_key_path"
ssh "$username@$server_address" << EOF
    # Change to the directory where your Docker-compose file is located (if needed)
    # cd /path/to/your/docker/compose/directory

    # Pull the latest Docker image (if needed)
    docker pull $docker_image

    # Run the Docker image
    docker run -d --name http_web -p 80:80 $docker_image
EOF




