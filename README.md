# Pterodactyl ngrok eggs
Pterodactyl eggs with ngrok <br /> <br />
## What is ngrok?
Ngrok is a tunneling software to portforward your server to custom other than the numeric ip <br />
Ngrok is an alternative from port forwarding in your router settings and exposing your ip <br /> <br />
To get the ip of your server, you have to go to https://dashboard.ngrok.com/cloud-edge/endpoints <br />
Feel free to open a request/feedback/issue in: [Issues](https://github.com/Bertogim/pterodactyl-ngrok-eggs/issues)



## How it works

The eggs are the default ones but with ngrok added, it installs ngrok and starts it in the background

It adds this to the startup command:
```
; .\/ngrok tcp {{SERVER_PORT}} --log=stdout > ngrok.log &
```
It will look like this:
```
java -Xms128M -XX:MaxRAMPercentage=95.0 -Dterminal.jline=false -Dterminal.ansi=true -jar {{SERVER_JARFILE}} ; .\/ngrok tcp {{SERVER_PORT}} --log=stdout > ngrok.log &
```

## Downsides
The eggs only supports ngrok endpoints at the time <br />
**⚠️Using these eggs is intended for personal use, the ngrok token can be seen from ngrok.yml⚠️**

## Games:

### [Minecraft](https://github.com/Bertogim/pterodactyl-ngrok-eggs/tree/main/Minecraft): 
[Vanilla](https://github.com/Bertogim/pterodactyl-ngrok-eggs/blob/main/Minecraft/egg-vanilla-ngrok.json) <br />
[Paper](https://github.com/Bertogim/pterodactyl-ngrok-eggs/blob/main/Minecraft/egg-paper-ngrok.json)

### [Beammmp](https://github.com/Bertogim/pterodactyl-ngrok-eggs/blob/main/Beammp/egg-beam-mp-ngrok.json)

## Games that don't work with ngrok:

### Mindustry
Mindustry needs tcp and udp "fowarding" wigh ngrok dosn't support, although you can do it with localtonet (its like ngrok but supports tcp-udp at the same time) in your pc <br /> <br />
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
