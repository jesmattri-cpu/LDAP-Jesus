1.- Primero aplica sudo apt update y upgrade a tu maquina virtual, si tiene conexión a internet


1.2-Configura el archivo 00-installer-config.yaml
<img width="670" height="407" alt="imagen" src="https://github.com/user-attachments/assets/28ee87b8-1c2d-4bb4-b15d-c0b46c7ebab3" />


2.- Después, intsla ldap con el comando sudo apt install slapd ldap-utils

<img width="1274" height="246" alt="imagen" src="https://github.com/user-attachments/assets/7aab3542-ef50-454c-993c-69417a052949" />


(dpkg –L slapd | grep bin = este comando puede mostrar todos los archivos y directorios ejecutables del programa que acabas de instalar)

3.- sudo dpkg-reconfigure slapd este comando inicia la coniguración

4.-Despues de esto te aparecerán varios pop ups con opciones al primero que dice de eliminar la base de datos anterior dices que no y la opción que movamos los datos a otra base de datos, a esta dale que si

<img width="1274" height="372" alt="imagen" src="https://github.com/user-attachments/assets/e10eb9de-d47d-43d7-92b7-61ce14db47df" />

( Información: opciones que puedes poner en el comando para decidirque hace
ldapdelete, s’utilitza per esborrar una o més entrades del directori.
ldapmodrdn, serveix per modificar els RDN de les entrades.
ldapsearch, s’utilitza per fer una cerca mitjançant els paràmetres especificats, possiblement és l’ordre més utilitzada.
ldapcompare, fa una comparança mitjançant els paràmetres especificats.
ldapmodify, serveix per modificar les entrades del directori.
ldappasswd, és una eina que s’utilitza per establir la contrasenya d’un usuari LDAP.
ldapwhoami, la funció és fer una operació whoami i determinar amb quin usuari heu fet un bind o login.
ldapexop, permet executar operacions esteses, definides per una organització d’estandardització o un venedor de directori particular, per exemple PAM.
ldapadd, s’usa per afegir entrades.)

(Información:  opciones que puedes poner para determinar como el sitema te registra en nivel de usuario
-D binddn. Determina el nom distintiu de l’usuari amb el qual us voleu connectar al servidor. El binddn es correspon amb la identificació única del node en què es troba l’usuari dins l’arbre LDAP.
-W . Us pregunta per línia de comandes la paraula de pas. També es pot especificar mitjançant -w password. (Cal anar amb compte perquè d’aquesta manera la contrasenya aniria en text clar.)
-H ldapurl. Especifica l’URL (s) de referència del servidor OpenLDAP (s) en què el client es vol autenticar. En la sintaxi només estan permesos els camps protocol / host / port i s’espera una o diversos URL, separades per espais en blanc o comes.
h –ldaphost. Especifica el nom de màquina del servidor en comptes de l’URL de l’opció anterior.
-x . Determina que s’utilitzarà l’autenticació simple en lloc de SASL.)

5.- Para conectar el serviidor y los usuarios con autenticación simple pones este comando sudo ldapadd -x -H ldap://localhost -D "cn=admin,dc=midominio,dc=localhost" -W -f base.ldif

<img width="911" height="141" alt="image" src="https://github.com/user-attachments/assets/2488f843-bca8-49bc-bab3-d0a525effef7" />

6.- despues configuras el archivo group.ldif como este ejemplo

<img width="615" height="343" alt="image" src="https://github.com/user-attachments/assets/3f51252f-006c-4637-ab60-dedc4e27d6b6" />

7.-agrega el conteido del archivo a ldap

<img width="770" height="144" alt="image" src="https://github.com/user-attachments/assets/8548b042-1845-4576-8b49-2178e16291c0" />

8.-Ahora creamos un nuevo usuario al poner en el archivo usuaris.ldif

R)<img width="827" height="665" alt="imagen" src="https://github.com/user-attachments/assets/9f6c8ebe-d5fe-4904-bb2a-fca447cca584" />

9.-ponemos una contraseña:
 agregano al archivo usuaris.ldif-userPassword: contrasenya
 <img width="843" height="668" alt="imagen" src="https://github.com/user-attachments/assets/72b73acc-1b0d-4963-9f8d-e9bac20c0bf9" />

 10.- lo montamos en el ldap
 con el comando sudo ldappasswd -S -W -D "cn=admin,dc=IOC-domini,dc=cat" -x "cn=Queralt Serra,cn=smx,ou=alumnat,dc=IOC-domini,dc=cat"
 <img width="843" height="668" alt="imagen" src="https://github.com/user-attachments/assets/00b17f3e-7e9a-40e0-bc61-cd1891fa8741" />

 






















