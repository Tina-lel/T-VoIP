# T-VoIP
T-VoIP (or Tina's Voice over Internet Protocol) is a Peer to Peer, end to end encrypted voice chatting utility, using socat's openssl features, written in bash

Dependencies:
-
bash

socat

alsa-utils

(and working audio input and output devices)

Ussage:
-
```
git clone https://github.com/Tina-lel/T-VoIP
```
## server:

```
cd T-VoIP/server/
```
```
chmod +x *
```

open up "config" in a text editor and choose a port number to replace "1234", and optionally forward this port in your gateways configuration page, to communicate outside of your internal network

```
./server
```

see "Commands" for a list of valid commands

#### generating SSL stuff and running the server:

make sure that when asked for "common name" you enter your host name/ip (for example: 192.168.1.69)
```
!gen
```
the files where generated in (script location)/.ssl, i guess you should be carefull with them
```
!start
```
if everything went fine, the server should be waiting for a client, to exchange certificates

## client:

```
cd T-VoIP/client/
```
```
chmod +x *
```

open up "config" in a text editor and change the "host" and "port" variable, to point to a machine running the "server" script

```
./client
```

see "Commands" for a list of valid commands

#### generating SSL stuff and connecting to the server:

```
!gen
```
the files where generated in (script location)/.ssl, you should be carefull with them
```
!connect
```
if the server was running, and everything went fine, you should now be hearing whatever the mic on the server side is recording and vice versa

Commands:
-

### server:

!help [this message]

!gen [generates SSL key, certificate and PEM file]

!start [starts the server]

!stop [stops the server]

!exit [exit the script]

### client:

!help [this message]

!gen [generates SSL key, certificate and PEM file]

!connect [connects to the desired host]

!disconnect [disconnects from the host]

!exit [exit the script]
