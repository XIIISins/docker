TS3 INSTANCE
====

TS3 server in a container  
Usage:  
sh docker-ts3 <name> <increment>  

Example with 2 containers, server1 listening on 9987 and server2 listening on 9988  
``` 
server1: sh docker-ts3 ts3-1 0  
server2: sh docker-ts3 ts3-2 1  
```
