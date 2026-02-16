1.- Primero aplica sudo apt update y upgrade a tu maquina virtual, si tiene conexión a internet

2.- Después, intsla ldap con el comando sudo apt install slapd ldap-utils

(dpkg –L slapd | grep bin = este comando puede mostrar todos los archivos y directorios ejecutables del programa que acabas de instalar)

3.- sudo dpkg-reconfigure slapd este comando inicia la coniguración
