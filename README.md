# Pterodactyl ngrok eggs
Pterodactyl eggs with ngrok <br /> <br />
## What is ngrok?
Ngrok is a tunneling software to portforward your server to custom other than the numeric ip <br />
Ngrok is an alternative from port forwarding in your router settings and exposing your ip <br /> <br />
To get the ip of your server, you have to go to https://dashboard.ngrok.com/cloud-edge/endpoints <br />
Feel free to open a request/feedback/issue in: [Issues](https://github.com/Bertogim/pterodactyl-ngrok-eggs/issues)

**⚠️Using these eggs is intended for personal use, the ngrok token can be seen from ngrok.yml⚠️**

## How it works

You can use this to create your own eggs with ngrok
The eggs are the default ones but with ngrok added, it installs ngrok and starts it in the background

### Startup command

It adds this to the startup command:
```
; ./ngrok start server --config ngrok.yml --log=stdout > ngrok.log &
```
It will look like this: (Java tags deleted)
```
java -jar {{SERVER_JARFILE}} ; ./ngrok start server --config ngrok.yml --log=stdout > ngrok.log &
```

### Install script
It adds this to the install script:
```
### Ngrok download ###

# URL of ngrok download
URL="https://bin.equinox.io/c/bNyj1mQVY4c/ngrok-v3-stable-linux-amd64.tgz"

FILE="ngrok-v3-stable-linux-amd64.tgz"

# Download file
wget "$URL"

# Unzip file
tar -xzf "$FILE"

# Delete zipped file
rm "$FILE"



## Download the ngrok config file for dynmap ##

# Download ngrok yml config file for dynmap
NGROK_YML_URL="https://raw.githubusercontent.com/Bertogim/pterodactyl-ngrok-eggs/main/Ngrok%20config%20files/dynmap/ngrok.yml"
NGROK_YML_FILE="ngrok.yml"

wget "$NGROK_YML_URL" -O "$NGROK_YML_FILE"

# Add ngrok authtoken
sed -i "s/000/${NGROK_AUTHTOKEN}/g" "$NGROK_YML_FILE"

# Replace placeholders with variables
sed -i "s/001/${SERVER_PORT}/g" "$NGROK_YML_FILE"
```

### Variables
It adds this variables:
#### Ngrok Authtoken
Name: Ngrok Authtoken
Environment Variable: NGROK_AUTHTOKEN
Input Rules: required|string

### What does the egg add with dynmap
The dynmap egg adds: <br /> <br />
To the startup command adds dynmap next to server, this is to tunnel the dynmap web: <br />
; ./ngrok start server **dynmap** --config ngrok.yml --log=stdout > ngrok.log & <br /> <br />

To the install script adds this in the last line:
```
sed -i "s/002/${DYNMAP_PORT}/g" "$NGROK_YML_FILE"
```
<br />
And to the variables it adds "Dynmap Port": <br />
Name: Dynmap Port <br />
Description: The port you are gonna use for dynmap <br />
Environment Variable: DYNMAP_PORT <br />
Input Rules: required|string|max:20 <br />



## Games:

### [Minecraft](https://github.com/Bertogim/pterodactyl-ngrok-eggs/tree/main/Minecraft): 
[Paper](https://github.com/Bertogim/pterodactyl-ngrok-eggs/blob/main/Minecraft/egg-paper-ngrok.json) <br />
[Paper with Dynmap](https://github.com/Bertogim/pterodactyl-ngrok-eggs/blob/main/Minecraft/egg-paper-ngrok-dynmap.json) <br /> <br />
You can make your own eggs with ngrok with the explanation on "How it works"


## Games that don't work with ngrok:

### Mindustry
Mindustry needs tcp and udp "fowarding" wich ngrok dosn't support, although you can do it with localtonet (its like ngrok but supports tcp-udp at the same time) in your pc <br /> <br />
Here is how you can do it with localtonet in the game: <br />
1. Go to mindustry, start a world <br />
2. Go to (ESC) and click "Host a multiplayer game" <br />
3. Go to localtonet and open a tunnel tcp-udp in the port 6567 (mindustry port)
  


## Tags:
Pterodactyl with ngrok <br />
Pterodactyl ngrok <br />
pterodactyl egg ngrok <br />
pterodactyl minecraft ngrok <br />
pterodactyl beamng ngrok <br />
pterodactyl beammp ngrok
