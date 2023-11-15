Since we have firmware files, it's easy to create a user. Open the archive with the firmware, find the file flashforge_init.sh , Add the following lines, having previously changed username and password to your username and password:
```bash
USERNAME="USERNAME"
PASSWORD="password"

adduser --disabled-password --gecos "" "$USERNAME"
echo -e "$PASSWORD\n$PASSWORD" | passwd "$USERNAME"

```
It should turn out like this:

![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/0a26b2a4-4bfd-42b8-bda5-19ad91fa7761)

Next, install the USB flash drive into the printer, reboot, see how it is updated, reboot again, connect via Telnet to port 23, and rejoice.

Getting root (my way):
connect to printer using telnet, ```cat /etc/passwd```, create file passwd in update archive, paste content, edit uid to 0 0 (screenshot)

![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/58398e17-fe65-4bd5-b500-9ae449c8397a)

![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/e399e8a7-2408-4ef4-ac99-6a63e0c7059b)

Next, edit flashforge_init.sh and add ```cp $WORK_DIR/passwd /etc/passwd ``` to copy passwd file to /etc/ directory

![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/83301dd2-58dc-4d17-8e0d-bed7f3a9d5a2)


