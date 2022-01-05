# Born2beRoot Step-by-step

## Creating the virtual machine
 
1. Open Oracle VirtualBox 
2. Select New - choose type Linux, Debian (64-bit) version
3. Set the RAM (I used 2GB)
4. Create a new virtual disk - type: VDI - storage: dynamically allocated - set the size (I used 15GB) - OK
5. Select your machine and then Settings: Armazenamento/Storage: Controladora/Controller: IDE - add your debian iso file
6. Still in Settings: Network: follow instructions Sharing Internet with the Virtual Machine (Bridge Adapter) - https://www.youtube.com/watch?v=PH854ARB0rU (video in portuguese)

## Debian instalation and LVM with encrypted partitions

1. In VirtualBox, select your machine, select start
2. Select your debian iso file
3. Choose Graphical install or Install (I recomend you to try the Install version to get used to the non graphical interfaces - it also seems faster for me)
4. Select your country, language and keyboard settings
5. Follow the instructions (set hostname and user; the domain field can be left empty)

### Partition with incryted LVM
6. Partition disks: select "Guided - select entire disk and set up incrypted LVM"
7. /home partition separada
8. Yes
9. Set a secret phrase to incrypt your partition (always read the instructions!!)
10. Use all your memory
At this point 3 partitions should have been created and configured (root, home and swap partitions)

-------------------------------------------------------------------------
### If you are going to make the Bonus:
11. Configure the Logical Volume Manager - select Yes
12. Exclude all logic volumes
13. Exclude volum group
14. Create volum group - name: LVMGroup - select /dev/mapper/sda5_crypt
15. Create new logic volumes* - set name (according with bonus) and size 
*aqui você pode escolher deixar uma das partições de fora, para depois aprender a diminuir uma partição (por exemplo, na tmp) e criar um novo volume lógico na linha de comando (abordaremos esses passos mais para frente)
16. Finish
17. Select each logical volume and configure fields: 
    For swap partition: 
      a. use as: change area (swap)
      b. Done setting up the partition
    For other partitions:
      a. use as: file system ext4
      b. mount point (/, /home, /tmp...)
      c. Done setting up the partition
---------------------------------------------------------------------------

18. Finish partitioning and write changes to disk
20. Check the data and select Yes

### Finishing instalation



## Adding a logic Volum
