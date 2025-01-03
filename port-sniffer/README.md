
```cargo run -- --address 127.0.0.1```

to run the program

it will start sniffing the ports on the given address
and print the open ports on the console


how it works:

1. User provides an IP address and port range (or uses defaults: localhost and ports 1-65535)
2. Program creates a channel for communication and spawns an async task for each port in the range
3. Each task attempts to make a TCP connection to the IP:port combination
4. When a connection succeeds, the port number is sent through a channel (indicating it's open)
5. After all tasks complete, the program displays a sorted list of all open ports found
