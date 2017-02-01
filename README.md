# WakeUp-Network
Network Protocol for WakeUp Applications

## Description of the protocole
The objective of the applications WakeUp server and client is to can Suspend server when all clients are off.

We first study the protocol from the client point of view.

### Client Side start
When the client start it send to the server a message "hello". 
If the server receive message, it answer with "hello too" message.
Then they go to okay - okay state.
If the server does not responding, client send a "WakeOnLan" message.
Then few seconds later resend a "hello" message.
if the server respond it is ok.
Else, the client log message and continue wating "hello too" response. 
When a change occurs, log it.


### Server Side start
If the server is running when receive a "hello" message it respond with "hello too" message.
If server is sleeping, client will send "WakeOnLan" message and resume server.
Then server will respond "hello too"

### Client Server Okay-Okay
After "hello" exchange, client and server must send then some "okay" message every minute.
If a message does not arrive the server will remove client to is client list.
This client must send an "hello" message to reset is status. 
If the client send an "okay" message, the server respond "don't know you", then client known that server don't remember him.


## Messages details
