## ProxMox

### Set Partition Size On Install  

swapsize: Size of the swap

maxroot: Size of the root partition. 20GB should be enough if you dont want to store a lot of backups and images (The system usually uses around 3GB).

minfree: Unpartitioned space which will be used temporarily when creating new VM's. (8 GB is a good value)

maxvz: Size of the data partition (stores VM's). Leave this empty to use all remaining space.
|Label|swap|maxroot|minfree|Storage|
|---|---|---|---|---|
|HEX1|2|80|1|250|
|HEX2|2|30|1|120|
|HEX3|2|30|1|120|
|HEX4|2|30|1|120|
|HEX5|2|30|1|120|
|HEX6|2|30|1|120|

### Fix SSH Problems
Execute this for each host in the cluster on each host in the cluster:
```bash
ssh-keygen -f "/etc/ssh/ssh_known_hosts" -R <hostname>
ssh-keygen -f "/etc/ssh/ssh_known_hosts" -R <ip>
ssh-keygen -f "/root/.ssh/known_hosts" -R <hostname>
ssh-keygen -f "/root/.ssh/known_hosts" -R <ip>
ssh -o 'HostKeyAlias=<hostname>' root@<ip> 'exit'
ssh root@<ip> 'exit'
```

## Linux Disk Enlarging
If you want to enlarge a linux disk in Proxmox, first make sure that the partition you want to enlarge is the last one on the disk, otherwise it's a lot more complicated. Then you can select the disk you want to enlarge in Proxmox and select “Resize disk”.

After enlarging it in Proxmox you have to enlarge the file system and partition inside the VM, so boot up the VM and start parted (where sda is the device you want to modify):
```bash
sudo parted /dev/sda
```
Then you have to check which file system you want to enlarge with 'print':
```bash
(parted) print 

Number  Start   End     Size    Type      File system     Flags
 1      1048kB  1000MB  999MB   extended
 5      1049kB  1000MB  999MB   logical   linux-swap(v1)
 2      1000MB  4294MB  3294MB  primary   ext4            boot
```

In the example above we want to enlarge the file system with number 2, so we can resize the file system inside parted with:
```bash
(parted) resizepart 2 Yes 100%
```
After that you can quit parted with 'quit' and now we actually have to resize the partition to use the whole file system. We can do that with:
```bash
sudo resize2fs /dev/sda2
```
Then you can check if it was successful with:
```bash
df -h /dev/sda2
```
It should use the whole virtual disk now.