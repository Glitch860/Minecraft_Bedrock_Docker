# Minecraft_Bedrock_Docker
Docker deployment for hosting a Minecraft Bedrock server in Docker

COMMENTS:
This Compose file uses the itzg/minecraft-bedrock-server image from Docker Hub to create a container for the Minecraft Bedrock server. The container_name is set to "minecraft-bedrock" for easy identification.

The container is configured to expose the default Minecraft Bedrock server port 19132 as a UDP port to the host machine using the ports configuration. This can be changed if you want to host multiple servers or already have that port in use. 

Several environment variables are set to configure the Minecraft Bedrock server, including EULA, SERVER_NAME, LEVEL_NAME, DIFFICULTY, GAMEMODE, SERVER_PORT, VIEW_DISTANCE, and ALLOW_CHEATS. These can be adjusted to match your desired server settings.

The volumes configuration is used to mount the host directory ./data as a volume in the container, which will be used to store the server data. This can be setup to use an NFS share if you want to keep the data of the server persistent. Persistent  data is helpful with running the docker image in a cluster.

With this Compose file, you can start the Minecraft Bedrock server container using the command 
```
docker-compose up -d
```
