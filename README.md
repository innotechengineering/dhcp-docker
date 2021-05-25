search hub.docker.com for
networkboot/dhcpd

make sure you have net0 interface up with a defined static address
nmcli connection up net0\ STATIC\ [192.168.0.1]

define the dhcp.conf in the /data dir with a lease pool in the range of the defined network interface above.

now.. you can launch the dhcp server using the below command
docker run -it --rm --init --net host -v /home/tyson/dev/isc-dhcp-server-docker/data:/data networkboot/dhcpd net0
