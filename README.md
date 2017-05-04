# Mininet-connect-to-Net
Mininnet 自定义拓扑:
h1----s1----h2
在运行自定义拓扑之后主机已经可以实现DHCP功能，可以自动分配IP，并且每次运行分配的IP不同。但是从Net却不能链接Ubuntu，这时候还需要更改
ovs-vsctl add-port s1 eth0
ifconfig s1 <ip/netmask>
ifconfig eth0 0.0.0.0
route add default gw <nat_ip> s1
route del default gw <nat_ip> eth0
