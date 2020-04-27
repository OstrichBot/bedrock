# Linux Minecraft Bedrock Server
![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/ostrichbot/bedrock-server)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/ostrichbot/bedrock-server)
![Docker Pulls](https://img.shields.io/docker/pulls/ostrichbot/bedrock-server)

Linux Minecraft Bedrock Server Docker Image from the Microsoft Official Site.
https://www.minecraft.net/en-us/download/server/bedrock/

Image should be updated within 12-hours of a Microsoft Update.

### Running with defaults
```
sudo docker run -d \
	--name bedrock \
	-p 19132:19132/udp \
	-p 19133:19133/udp \
	ostrichbot/bedrock-server
```

### Running with custom configs
```
sudo docker run -d \
	--name bedrock \
	-p 19132:19132/udp \
	-p 19133:19133/udp \
	-v $(pwd)/configs/whitelist.json:/bedrock-server/whitelist.json \
	-v $(pwd)/configs/permissions.json:/bedrock-server/permissions.json \
	-v $(pwd)/configs/server.properties:/bedrock-server/server.properties \
	-v $(pwd)/bedrock/worlds:/bedrock-server/worlds \
	--restart=unless-stopped \
	ostrichbot/bedrock-server
```
