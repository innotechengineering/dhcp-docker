# dhcp-docker
easily spin up a docker instance of a dhcp server.  usefull for connecting to a headless raspberry pi.

## my system
i use `network manager` and my main ethernet interface on my thinkpad is named `net0`

## steps
1) make sure you have net0 interface up with a defined static address.  
`nmcli connection up net0\ STATIC\ [192.168.0.1]`

2) define the dhcp.conf in the /data dir with a lease pool in the range of the defined network interface above.  

3) now.. you can launch the dhcp server using the below command.  
`docker run -it --rm --init --net host -v "$PWD"/data:/data networkboot/dhcpd net0`


 
#### reference
search hub.docker.com for
networkboot/dhcpd
