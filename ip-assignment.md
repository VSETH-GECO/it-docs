### 10.233.0.0/16 (ETHZ “Docker” unrouted)
Switches 10.233.0.0 - 10.233.127.0
Jeder einen /24er

### 10.233.255.0/24 SYNC
Kein VLAN, blaues Kabel im CAB  
10.233.255.1 pf1-geco.vseth.ethz.ch  
10.233.255.2 pf1-geco.vseth.ethz.ch

### 10.233.254.0/24 Core
Vlan: 1254

### 10.233.253.0/24 Server
Vlan: 1253  
10.233.253.2 monitoring.lan.geco.ethz.ch  
10.233.253.3 dhcp0.lan.geco.ethz.ch  
10.233.253.4 dhcp1.lan.geco.ethz.ch  
10.233.253.5 cachedns.lan.geco.ethz.ch  
10.233.253.6 freeradius.lan.geco.ethz.ch  
10.233.253.7 librenms.lan.geco.ethz.ch  

10.233.253.10 steamcache.lan.geco.ethz.ch  
10.233.253.11 ebot.lan.geco.ethz.ch  
10.233.253.12 adminafk.lan.geco.ethz.ch  
10.233.253.13 login.lan.geco.ethz.ch  
10.233.253.14 files.lan.geco.ethz.ch  
10.233.253.15 ts1.lan.geco.ethz.ch  
10.233.253.16 ts2.lan.geco.ethz.ch  
10.233.253.17 csmon.lan.geco.ethz.ch  
10.233.253.18 srcdsmon.lan.geco.ethz.ch  

10.233.253.20 wc.lan.geco.ethz.ch  
10.233.253.21 wcmgt.lan.geco.ethz.ch  

10.233.253.50 csmatch1.lan.geco.ethz.ch  
10.233.253.51 csmatch2.lan.geco.ethz.ch  
10.233.253.52 csmatch3.lan.geco.ethz.ch  
10.233.253.53 csmatch4.lan.geco.ethz.ch  
10.233.253.54 csfun1.lan.geco.ethz.ch  
10.233.253.55 minecraft.lan.geco.ethz.ch  
10.233.253.56 bfbc2.lan.geco.ethz.ch  
10.233.253.57 openttd.lan.geco.ethz.ch  
10.233.253.58 bf2.lan.geco.ethz.ch  
10.233.253.59 cspug1.lan.geco.ethz.ch  
10.233.253.60 cspug2.lan.geco.ethz.ch  

10.233.253.99 androidap  

10.233.253.200 debian-template.lan.geco.ethz.ch  

10.233.253.240 transtec.lan.geco.ethz.ch  
10.233.253.241 hex1.lan.geco.ethz.ch  
10.233.253.242 hex2.lan.geco.ethz.ch  
10.233.253.243 hex3.lan.geco.ethz.ch  
10.233.253.244 hex4.lan.geco.ethz.ch  
10.233.253.245 hex5.lan.geco.ethz.ch  
10.233.253.246 hex6.lan.geco.ethz.ch  
10.233.253.247 hydra.lan.geco.ethz.ch  
10.233.253.248 nas.lan.geco.ethz.ch  

### 10.233.252.0/24 MGMT
Vlan 1 // Handy for setup  
10.233.252.100 usv  

### Catalyst 3750-E switches
|hostname(Model) | Label       |ip (management vlan 1) |Comment |
|----------------|-------------|-----------------------|--------|
|FDO12390BE8     |(access7)    |10.233.252.30||
|FDO13370K8G     |FDO13370K8G  |10.233.252.10||
|FDO13130WS7     |FDO13130WS7  |10.233.252.5||
|FDO133808ZZ     |FDO133808ZZ  |10.233.252.8    |(core 1, requires password on serial)|
|FDO13370KF5     |FDO13370KF5  |10.233.252.28||
|FDO134317P1     |FDO134317P1  |10.233.252.6||
|FDO13370KAH     |FDO13370KAH  |10.233.252.3||
|FDO14470CGS     |back to cisco|10.233.252.25||
|FDO13370KGE     |FDO13370KGE  |10.233.252.7    |(core-2)|
|FDO124504DY     |(user 8)     |10.233.252.12||
|FDO123809H0     |(user 11)    |10.233.252.13||
|FDO14020EP3     |(user 14)    |10.233.252.14||
|FDO13130WUX     |(user 13)    |10.233.252.15||
|FDO13370K9F     |(user 16)    |10.233.252.17   |(not booting label but does boot perfectly fine)|
|FDO15160LDZ     |(core-0)     |10.233.252.253||
|FDO133808A5     |FDO133808A5  |10.233.252.18||

### Core

### 10.233.200.0/24 WAN
Vlan 199  

###  10.233.199.0/24 Admin-Lan  
