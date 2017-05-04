# Mininet-connect-to-Net
Mininnet 自定义拓扑: <br />
h1----s1----h2 <br /> <br />
在运行自定义拓扑之后主机已经可以实现DHCP功能，可以自动分配IP，并且每次运行分配的IP不同。但是从Net却不能链接Ubuntu，这时候还需要更改 <br />
ifconfig s1 <ip/netmask> <br />
ifconfig eth0 0.0.0.0 <br />
route add default gw <nat_ip> s1 <br />
route del default gw <nat_ip> eth0 <br />
