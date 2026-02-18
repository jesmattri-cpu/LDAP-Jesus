1.- Primero aplica sudo apt update y upgrade a tu maquina virtual, si tiene conexión a internet

2.- Después, intsla ldap con el comando sudo apt install slapd ldap-utils

<img width="1274" height="246" alt="imagen" src="https://github.com/user-attachments/assets/7aab3542-ef50-454c-993c-69417a052949" />


(dpkg –L slapd | grep bin = este comando puede mostrar todos los archivos y directorios ejecutables del programa que acabas de instalar)

3.- sudo dpkg-reconfigure slapd este comando inicia la coniguración

4.-Despues de esto te aparecerán varios pop ups con opciones al primero que dice de eliminar la base de datos anterior dices que no y la opción que movamos los datos a otra base de datos, a esta dale que si

<img width="1274" height="372" alt="imagen" src="https://github.com/user-attachments/assets/e10eb9de-d47d-43d7-92b7-61ce14db47df" />

