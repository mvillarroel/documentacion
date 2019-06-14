# LibreNMS 
#### *En este documento encontrarás los posibles errores que se pueden presentar y su respectiva solución. Además, de los pasos a seguir para agregar nuevos dispositivos a monitorear.*

_________________________________________________

## Validate Config

* Revisar _Validate Config_ diariamente por si es que se presentara algún tipo de error. La pagina se debería ver así:


![ValidateC# cd /opt/librenmsonfig](https://user-images.githubusercontent.com/19380885/59522852-b9386000-8e9d-11e9-88b0-437701a21aa2.png)
![Config](https://user-images.githubusercontent.com/19380885/59522860-c0f80480-8e9d-11e9-95f2-87480490f712.png)
![ok](https://user-images.githubusercontent.com/19380885/59522857-bdfd1400-8e9d-11e9-86ac-633250d1088c.png)

* Si es que algunas de las filas anteriores dijera __Fail__, se detalla el error y su solución, la cual se debe ejecutar en un terminal como root, en el servidor donde se encuentra instalado LibreNMS y dentro del siguiente directorio:

      # cd /opt/librenms

* La segunda alternativa para realizar un Validate Config, es por medio de la consola ejecutando los siguientes comandos con permisos de root:

      # cd /opt/librenms
      # ./validate.php
      
* El output debería ser el siguiente:

![validate](https://user-images.githubusercontent.com/19380885/59524218-4b8e3300-8ea1-11e9-8e73-b7c218493f23.png)

_____________________________________________________

## Solución de fallas

* Falla de CronJob: ejecutar el siguiente comando

      # ./discovery.php -v Configuraciones para un nuevo cliente-h all
      
* Falla de Permisos: Para solucionarlo, hay que ejecutar los comandos que se encuentran destacados con morado, tal cual como se presentan.

![permissions](https://user-images.githubusercontent.com/19380885/59524785-be4bde00-8ea2-11e9-8ead-376bd3f97d09.png)

#### __“Después de solucionar las fallas es importante volver a ejecutar el comando ./validate.php para asegurarnos que está todo ok.“__

______________________________________________________

## Configuraciones para un nuevo cliente

Pasos: 

1. Ingresar a la consola del nuevo cliente que se desee agregar, ya sea por ssh o directamente. Luego se debe instalar el paquete de SNMP ejecutando el siguiente comando:

        # apt-get -y install snmpd
        
2. Modificar el archivo de configuración de SNMP, donde se debe editar “community string” por CuidateToth el cual corresponde al mismo nombre de comunidad que está ingresado en el Server. Para que de esta forma se puedan identificar los dispositivos. 

        #  /etc/snmp/snmpd.conf
        
* Ejemplo: 

![aaaa](https://user-images.githubusercontent.com/19380885/59521532-7c1e9e80-8e9a-11e9-9d66-897a13eddbc5.png)

3. Instalar el script correspondiente a la distro para obtener la información del sistema operativo del cliente en la web de Librenms.

        # curl -o /usr/bin/distro https://raw.githubusercontent.com/librenms/librenms-agent/master/snmp/distro
        # chmod +x /usr/bin/distro

4. Reiniciar el servicio snmpd.

        # systemctl restart snmpd

5. Habilitar el servicio snmpd para que se inicie automáticamente en el boot del sistema del cliente.

        # systemctl enable snmpd  

6. Para asegurarte que el servicio de snmpd que recién configuraste escucha en todas las interfaces de red o en una interfaz particular a la que LibreNMS pueda acceder.

        # netstat -antup | grep -i 161

* Output:

![netstat](https://user-images.githubusercontent.com/19380885/59524788-bee47480-8ea2-11e9-9dab-0d6fe882be18.png)

_____________________________________________________

## Acceder a la web de LibreNMS

* Ingresar a _Devices → Add Device_ y completar con los datos destacados en rojo.

![Add-Devices-to-LibreNMS-Adding-New-Device-768x483](https://user-images.githubusercontent.com/19380885/59524791-c0ae3800-8ea2-11e9-9103-cd938e50d578.png)


