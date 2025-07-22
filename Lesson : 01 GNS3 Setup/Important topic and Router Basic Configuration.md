# GNS3 Setup


## importants commant for Mikrotik
- login : admin
- password : Blank
- ctrl + c // for skip password
- interface print  or  interface/ print  // show interface
- ip address print 
- ip address add address=192.168.0.1/24 interface=ether1
## how to edit IP Address or others infromation
-   ip address/edit
-   enter row number
-   enter value name 
-   press Enter
-   Edit 
-   Save with CTRL + o  and quit

## how to remove IP Address or others infromation
-   ip address/remove
-   enter row number
-   enter value name
-   Enter

## MikroTik Router Basic Configuration : 
**Steps**:
1.  WAN Configure
2.  LAN Configure
3.  Default route Configure
4.  NAT Configure
5.  DNS Setup

### ether1 will connect to ISP
### Step by Step Configuration Commands : 
-   ip address/add address= 100.0.0.2/30 inter1
-   ip address/add address= 192.168.0.1 inter2
-   ip route/add gateway=next_Hoop_Address 
-   ip firewall/nat add chain=srcnat action=masquerade
-   ip dns/set servers=8.8.8.8

