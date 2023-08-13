```
1. sudo apt update
2. sudo apt upgrade
3. sudo apt install linux-headers-$(uname -r) build-essential dkms
4. sudo apt install build-essential # if unable to locate package
5. Devices (on VM toolbar) -> Insert Guest additions CD image
6. Look for VBoxLinuxAdditions.run (should appear in a new File Manager window)
   - If no new window:
       File Manager -> Devices (left side of window) -> VBox_GAs_x.x.x
7. File (in new File Manager window) -> Open Terminal Here
8. sudo ./VBoxLinuxAdditions.run (in new terminal)
9. Right click VBox_GAs_x.x.x -> Eject
10. reboot (in terminal)
```