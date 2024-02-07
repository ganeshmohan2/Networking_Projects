Designed core network using OSPF network topology with ABRs, ASBRs(EIGRP and BGP into OSPF), NSSA, virtual link, route summarization at ABRs and ASBRs, and Natting to reach internet. 


![image](https://github.com/Dhananetwork/Networking_Projects/assets/159283500/20752d89-502a-4486-927b-161fa1cc057d)

ip nat inside source list INTERNET interface FastEthernet0/0 overload
ip route 0.0.0.0 0.0.0.0 192.168.122.1
!
ip access-list standard INTERNET
 permit 10.1.1.1
 permit 60.1.0.0 0.0.255.255
 !
router ospf 1
 router-id 1.1.1.1
 passive-interface FastEthernet0/0
 network 0.0.0.0 255.255.255.255 area 0
 default-information originate always

