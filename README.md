# Cheatsheet
just little saves of good bits of code to remember

ls /usr/share/xsessions/ <- this is to see my desktop environents currently installed 
nc -zv 192.168.1.134 22 <- this is to see if port 22 is open on ip 192.168.1.134

apt list --installed | grep vlc - this tells me everythinf install so long as the thing after grp is the thing im looking for, so i used it to find my ssh stuff 

docker container prune #CAUTION this will delete all non-running containers 

to make docker work properly: sudo group add docker --> sudo usermod -aG docker $USER --> newgrp docker #this should make docker be runnable as sudo 

sudo docker exec -it guac-mysql bash <-- this may be how you get into the containers to do stuff, need to get the robot to break it down or find a better way to figure it out. 

docker logs guacamole - this is handy for troubleshooting




