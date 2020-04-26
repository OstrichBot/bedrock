# Linux Minecraft Bedrock Server
Linux Minecraft Bedrock Server Docker Image from the Microsoft Official Site.
https://www.minecraft.net/en-us/download/server/bedrock/

Image should be updated within 12-hours of a Microsoft Update.

Assumes you build run from your ./bedrock directory
.json & .property files stored in $pwd/configs/
world files stored in $pwd/worlds/

sudo docker run -d \
	--name bedrock \
	-p 19132:19132/udp \
	-p 19133:19133/udp \
	-v $pwd/configs/whitelist.json:/bedrock-server/whitelist.json \
	-v $pwd/configs/permissions.json:/bedrock-server/permissions.json \
	-v $pwd/configs/server.properties:/bedrock-server/server.properties \
	-v $pwd/bedrock/worlds:/bedrock-server/worlds \
	--restart=unless-stopped \
	ostrichbot/bedrock-server
