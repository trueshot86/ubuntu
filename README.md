# Ubuntu tips

### Network

Normal

```
network:
  version: 2
  renderer: networkd
  ethernets:
    ens33:
      dhcp4: no
      dhcp6: no
      addresses: [192.168.100.130/24]
      gateway4: 192.168.100.1
      nameservers:
        addresses: [192.168.100.53, 8.8.8.8, 8.8.4.4]
```
        
Bridge
```
network:
   version: 2
   renderer: networkd
   ethernets:
     ens160:
       dhcp4: no
       dhcp6: no
       accept-ra: no
   bridges:
     br0:
       dhcp4: no
       dhcp6: no
       accept-ra: no
       addresses:
         - 192.168.0.1/24
         - fc00:dead:beef:1::1/64
       gateway4: 192.168.0.1
       gateway6: fc00:dead:beef:1::fffe
       nameservers:
         addresses:
           - 8.8.8.8
           - 8.8.4.4
           - 2001:2860:4860::8888
           - 2001:2860:4860::8844
         search:
           - example.com
       interfaces:
         - ens160
       parameters:
         stp: no
```



