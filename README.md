# Cheatsheet
just little saves of good bits of code to remember

ls /usr/share/xsessions/ <- this is to see my desktop environents currently installed 
nc -zv 192.168.1.134 22 <- this is to see if port 22 is open on ip 192.168.1.134

apt list --installed | grep vlc - this tells me everythinf install so long as the thing after grp is the thing im looking for, so i used it to find my ssh stuff 

docker container prune #CAUTION this will delete all non-running containers 

to make docker work properly: sudo group add docker --> sudo usermod -aG docker $USER --> newgrp docker #this should make docker be runnable as sudo 

sudo docker exec -it guac-mysql bash <-- this may be how you get into the containers to do stuff, need to get the robot to break it down or find a better way to figure it out. 

docker logs guacamole - this is handy for troubleshooting

dpkg -l | grep mate //so this is to look up what is currently in my computer under mate. Also, you seem to have fucked up your keyboard again. 

docker rm -f guacamole <-- the -f means force

docker network ls <-- shows what networks docker has RN. 

docker run --name guacamole \
  --network guacnet \
  -e MYSQL_HOSTNAME=guac-mysql \
  -e MYSQL_DATABASE=guacamole_db \
  -e MYSQL_USER=guacamole_user \
  -e MYSQL_PASSWORD=yourpass \
  -d -p 8080:8080 guacamole/guacamole 

^^^^ this appears to be a working version of guacamole


  docker inspect guacamole guac-mysql guacd --format='{{ json .NetworkSettings.Networks }}' | jq <-- this is how you inspect all of the containers cleanly

autorestarting in docker: 
docker run -d --restart=unless-stopped <image_name>: Recommended for most services; respects manual stops but restarts on reboot. 
docker run -d --restart=always <image_name>: Forces the container to restart on reboot and after every exit, even if manually stopped. 
docker run -d --restart=on-failure <image_name>: Restarts only if the container exits with a non-zero code. 

renaming docker containers

docker container rename zealous_neumann cloudflare

connecting my container to a new network: 
malware-rig@malware-rig:~$ docker network connect 021250535fc2 cloudflare
where 021250535fc2 is the network id and cloudflare is the container 

nc -zv 192.168.1.134 22 - this will see if port 22 is open on the ip address 192.168.1.134 

How to ssh from my own machine: 
ssh malware-rig@192.168.0.50




