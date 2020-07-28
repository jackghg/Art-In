# Art-In
Art-In is a **Artix** installer scripts, to install Artix Linux with a interactive bash script, easy to customize, I hope. The init is **runit**. 

Art-in is still a beta.
## Installation:
- Backup your data !
- Download the last artix base iso, flash it to a usb drive, boot it and login as root
- Put the 3 script files in /ai for example by mounting a drive
```
mkdir /ai
mount /dev/sdc1 /ai
cd /ai
```
- Make the partitions now or in the installer with cfdisk
- Note the partitions path in /dev for boot, system, swap. Data on these partitions will be deleted!
- Start the first part of the installer and follow the instrucions
```
./arisc1
```
- When finished remove the Artix iso and installer drives and restart
- Login as root, connect to wifi if needed, and start the second part
```
./arisc2
```
- If lightdm starts, don't login, use ctrl+alt+F1 to go back
- Restart. Review and delete the installer files in /root

## Autoupdate
A very basic auto update will execute `pacman -Syyu && paccache -rk1` every 7 days if you install it. If the update fails, see  the arch linux news, a manual fix may be needed.\
You can tweak the script at: `/opt/aiupdate`\
Autostarted at: `/etc/xdg/autostart/autostart`, `home/.config/autostart/autostart` or `/etc/xdg/lxsession/LXDE/autostart`, `home/.config/lxsession/LXDE/autostart`\
The invisible update is a cronie anacron task at `/etc/anacrontab`

## Time Update
A script will update the clock some minute after the boot. If your PC stays on for days, you could use ntpd or cron instead.\
The script is at: `/opt/aitime`\
Autostarted at `/etc/rc.local`\
If you dualboot windows the easyest way to fix the time is to set the hardware clock to UTC in windows(registry).

## Warnings and limitations
- **Backup** your data before installing Linux !
- Xfce or Lxde (only) can be installed at the moment
- the installer won't connect to **wifi**. Do it manually. Internet is needed at part 2
- home partition and extra partitions won't be mounted. Edit the fstab later
- no encryption
