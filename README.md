# Art-In
Art-In is a Artix Linux installer script. The init is runit.
## Installation:
\- Backup your data !
\- Download the last artix base iso, flash it to a usb drive and boot it
\- Put the 3 script files on another usb drive and mount it on /ai
```
mkdir /ai
mount /dev/sdc /ai
cd /ai
```
\- Make the partitions now or in the installer with cfdisk
\- Note the partitions path in /dev for boot, system, swap. These partitions will be formated!
\- Start the first part of the installer and follow the instrucions
```
./arisc1
```
\- When finished remove the Artix iso and installer drives and restart
\- Login as root, connect to wifi if needed, and start the second part
```
./arisc2
```
\- If lightdm starts use ctrl+alt+F1 to go back
\- Restart. Review and delete the installer files in /root

