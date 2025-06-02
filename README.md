# TP Computación Aplicada
## Integrantes del Grupo 1:
### Mariano Antonsich
###  Mateo Rasmussen
### Alejandro Garcia
### María Pía Achigar

# 
El trabajo práctico consiste en la configuración de entorno, de servicios, de Red y de almacenamiento del Sistema Operativo Virtualiasdo GNU/Linux Debian11, con un script backup "backaup_full.sh"


# Consignas

1) Configuración del entorno
-  La máquina virtual está dividida en partes y comprimidas en formato “.rar”.
Descargar y ensamblar los archivos utilizando herramientas como WinRar.
- La clave de root es desconocida inicialmente, por lo que deberá ser blanqueada
antes de comenzar. Una vez dentro del sistema operativo, la misma debe ser
cambiada por “palermo” (sin comillas).
- Establecer el nombre de hostname como TPServer.
2) Servicios
- SSH: instalar y configurar el servicio de SSH. El servidor debe permitir el acceso al
usuario root mediante una clave privada/pública, proporcionada junto con la
máquina virtual en Blackboard.
- WEB: instalar y configurar el servidor Apache con soporte para PHP (versión 7.3 o
superior). Configurar el servidor para servir el archivo “index.php” y “logo.png”,
disponible junto con la máquina virtual en Blackboard.
- Base de datos: instalar y configurar MariaDB. Cargar, en el motor de base de
datos, el script SQL, denominado “db.sql”, disponible junto con la máquina virtual
en Blackboard.
3) Configuración de Red
- Configurar la interfaz de red con una IP estática en el archivo de configuración. La
IP debe pertenecer al mismo rango red de la máquina física.
- El archivo de configuración debe incluir los campos ADDRESS, NETMASK y
GATEWAY.
4) Almacenamiento
- Agregar un nuevo disco de 10 GB adicional a la máquina virtual.
- Crear dos particiones estándar (tipo 83), con las siguientes capacidades:
  - /www_dir: 3 GB
  - /backup_dir: 6 GB
- Configurar el directorio /www_dir para alojar el archivo index.php y logo.png.
Actualizar el archivo de configuración de Apache para que éste apunte a la nueva
ubicación (ver archivos 000-default.conf y apache2).
- Configurar el directorio /www_dir para que se monte automáticamente al iniciar
el sistema operativo.
- Configurar el directorio /backup_dir para que se monte automáticamente al iniciar
el sistema operativo.

Backup
1) Desarrollar un script de backup denominado “backup_full.sh”, y guardarlo en
/opt/scripts.
2) El script debe backupear los directorios indicados con nombres que incluyan la
fecha en formato ANSI (YYYMMDD). Por ejemplo, para /var/log, el archivo
generado debería llamarse “log_bkp_20240302.tar.gz”.
3) Los backups generados deben almacenarse en la partición que tiene montado el
directorio /backup_dir.
4) El script debe aceptar argumentos como origen (lo que se va a backupear) y
destino (dónde se va a backupear).
5) El script debe incluir una opción de ayuda (-help), para guiar al usuario en el uso
del script.
6) El script debe validar que los sistemas de archivos de origen y destino estén
disponibles antes de ejecutar el backup.
7) El script debe ser incluido en un calendario de tareas para correr
automáticamente:
   - TODOS LOS DÍAS a las 00:00 hs: Backupear “/var/logs”
   - LUNES, MIÉRCOLES, VIERNES a las 23:00 hs: Backupear “/www_dir”.   

Entregables
1) Crear un repositorio en github (es gratuito), y redactar el README.md con los
nombres de los participantes del grupo.
2) Subir, en el repositorio creado, los directorios:
 “/root”, “/etc”, “/opt”, “/proc”, “/www_dir” y “/backup_dir”. Todos ellos
comprimidos individualmente en formato “.tar.gz”.
 “/var” se lo debe splitear en partes pequeñas para que pueda ser subido.
3) Realizar un diagrama topológico de la infraestructura armada.
