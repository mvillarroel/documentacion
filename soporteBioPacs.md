# Documentación Toth
## En éstos archivos encontrarás los procesos habituales de soporte para el sistema BioPacs.

###### **BioPacs - Corona**: https://corona.toth.cl 
* radiologico.biopacs.com
* lascondes.biopacs.com
* cimek.biopacs.com
* divim.biopacs.com
* centroimagen.biopacs.com
* vibra.biopacs.com
* sanpatricio.biopacs.com
* dellago.biopacs.com

###### **BioPacs - Externos**
* cao.biopacs.com
* csf.biopacs.com
* clinicaucm.biopacs.cl
* hospitaldetalca.biopacs.com
* centac.biopacs.com
___________________________________________________________
**Síntoma 1**: *No llegan los estudios al sistema Biopacs y/o no tiene worklist (desde BioRis).*
1. Revisar discos **df - h**
  * Revisar si la carpeta donde llegan los estudios está llena.
  * Si la carpeta está llena debes mover los estudios.
2. ¿El disco se encuentra en modo lectura?
  * Para averiguarlo sólo debes entrar al cliente desde la consola y aparecerá el mensaje "read only", para solucionarlo debes reiniciar el servicio **sudo reboot**
3. Si los discos no están lleno y no se encuentran en modo lectura entonces debes matar java y luego levantar biopacs.sh
  * **sudo killall java**
  * **sudo /etc/ini.d/biopacs.sh**
___________________________________________________________
