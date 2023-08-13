# Running sample node js app with docker

- Get a ubuntu vm and run below steps in setup vm file
# Create User
	sudo adduser apps
	sudo usermod -aG sudo apps
	su apps
	sudo ls
	exit
	su - apps
# Install Docker and Docker Compose
	sudo apt-get -y update
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
	sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
	sudo apt-get install -y docker-ce
	sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

 	docker-compose -v
	sudo groupadd docker # some times docker user already there, just go next step
	sudo usermod -aG docker $USER
	exit
	su - apps # eixt and login again

# Running ingnix

	docker pull nginx:latest
	docker run --name mynginx -v ~/html:/usr/share/nginx/html -d -p 80:80 nginx:latest
	docker ps
	docker stop mynginx
# Unix commad
	sudo mv foldername /home/otheruser/
	sudo mv foldername /home/apps/
