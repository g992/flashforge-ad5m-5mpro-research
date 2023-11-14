Since we have firmware files, it's easy to create a user. Open the archive with the firmware, find the file flashforge_init.sh , Add the following lines, having previously changed username and password to your username and password:
```bash
USERNAME="USERNAME"
PASSWORD="password"

adduser --disabled-password --gecos "" "$USERNAME"
echo -e "$PASSWORD\n$PASSWORD" | passwd "$USERNAME"
adduser "$USERNAME" sudo

```
It should turn out like this:
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/0a26b2a4-4bfd-42b8-bda5-19ad91fa7761)

Next, install the USB flash drive into the printer, reboot, see how it is updated, reboot again, connect via Telnet to port 23, and rejoice.
And in the /opt/klipper folder you can successfully find the clipper! Hooray!
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/21337ecd-fde8-4a2e-bd74-73294dc0f113)

And in the /opt/config folder you can find all the printer configs
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/6473d34c-04bf-4082-9e7a-51ebc6d6bda6)
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/c4914c03-652b-4439-9d51-67dadebb31c1)

But this is a user without root, I don't have enough knowledge for further modifications.
