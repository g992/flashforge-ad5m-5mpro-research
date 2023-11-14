Here will be instructions on how to get root access to your printer....
Так как у нас есть файлы прошивки, это будет просто. Открываем архив с прошивкой, находим файл flashforge_init.sh, Добавляем следующие строки, предварительно изменив username и password на свои логин и пароль:
```bash
USERNAME="USERNAME"
PASSWORD="password"

adduser --disabled-password --gecos "" "$USERNAME"
echo -e "$PASSWORD\n$PASSWORD" | passwd "$USERNAME"
adduser "$USERNAME" sudo

```
Должно получиться как то так:
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/0a26b2a4-4bfd-42b8-bda5-19ad91fa7761)

Далее устанавливаем флешку в принтер, перезагружаем, видим как он обновляется, перезагружаем еще раз, подключаемся по Telnet к 23 порту, и радуемся.
И в папке /opt/klipper вы успешно можете найти клиппер! Ура!
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/21337ecd-fde8-4a2e-bd74-73294dc0f113)

А в папке /opt/config вы можете найти все конфиги принтера
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/6473d34c-04bf-4082-9e7a-51ebc6d6bda6)
![image](https://github.com/g992/flashforge-ad5m-5mpro-research/assets/48438685/c4914c03-652b-4439-9d51-67dadebb31c1)

