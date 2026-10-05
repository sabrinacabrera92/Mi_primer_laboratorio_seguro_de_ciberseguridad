# Mi_primer_laboratorio_seguro_de_ciberseguridad

Reporte Técnico de Configuración de Laboratorio para Ciberseguridad Coderhouse

Sabrina Cabrera

--

En lugar de utilizar Windows, se configuró una máquina virtual con Kali Linux, adaptando los controles de seguridad al entorno UNIX/Linux.

### Virtual box y red aislada:

<img width="896" height="571" alt="kali_red_modo_NAT" src="https://github.com/user-attachments/assets/2f987e00-6eb7-4e30-8a2f-5fa002ae59c8" />

La máquina virtual de Kali Linux está configurada con un adaptador de red en modo NAT. Este modo aísla la máquina de la red local física, actuando como un router invisible. Así permite a la VM tener salida a internet para realizar actualizaciones, pero no permitir que dispositivos externos se conecten directamente a ella, protegiendo así a la PC anfitriona (Host) de posibles ataques.

### Mantenimiento y Parches:

<img width="902" height="679" alt="kali_upgrade_completo" src="https://github.com/user-attachments/assets/a5235b1f-48c2-4984-b642-470f1f62307d" />

Quedó aplicado el hardening básico al SO instalando todos los parches de seguridad mediante el gestor de paquetes (con los comandos: sudo apt update y sudo apt upgrade). Como se ve en la captura de pantalla queda confirmado que no hay paquetes pendientes de actualización ("Upgrading: 0"), garantizando la integridad del sistema frente a vulnerabilidades conocidas.

### Gestión de Usuarios y Permisos:

<img width="643" height="252" alt="kali_permisos" src="https://github.com/user-attachments/assets/cd343222-cda8-41bc-b89a-f42b51c70e27" />

Se muestra mediante la creación del documento prueba_prmisos.txt y el comando
 ls -l prueba_permisos.txt 
Que se cumple con el principio de menor privilegio y reducir la superficie de ataque limitando los permisos de ejecución y escritura sobre archivos críticos del SO.

### Snapshot Hardening Inicial

<img width="1137" height="402" alt="kali_instantanea_hardening_inicial" src="https://github.com/user-attachments/assets/5f3c9c1a-1a0c-4da3-9aef-f886e1da28f2" />

Quedó creada la instantánea con el “hardening inicial” aplicado donde se ve el sistema actualizado, asegurando la recuperación del entorno de pruebas y dando la posibilidad de retornar a un estado seguro en caso de que un análisis de malware o configuración errónea “rompan” el sistema.

