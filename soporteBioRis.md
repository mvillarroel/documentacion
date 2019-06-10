# Soporte BioRis
## En éste documento encontrarás los procesos habituales de soporte para el sistema BioRis
_____________________
**Síntoma 1**:
Si en la agenda aparece un gif "cargando" y no permite visualizar horarios ni citas, debes revisar lo siguiente:
* Campo **"hour_c"** de la tabla **calendar** de la semana en la cual presente problemas: en algunos casos existen más de una cita en el mismo horario, se debe corregir modificando la hora de una de las citas.
* Revisar **"date_s"** de la tabla **schedule** de la semana en la cual presente problemas: en algunos casos existen más de un horario duplicado, se debe corregir modificando la hora de los horarios en cuestion.
_____________________
**Síntoma 2**: Clínica San Patricio
Si en la agenda aparece un gif "cargando" y no permite visualizar horarios ni citas, debes revisar lo siguiente:
* Revisar **"date_s"**, **"mi_hour"**, **"me_hour"**, **"ai_hour"**, **"ai_hour"** de la tabla **schedule** y verificar que los horarios correspondan a la jornada. 
  * **mi_hour**: Inicio jornada mañana, desde las 00:00 a las 14:00
  * **me_hour**: Fin jornada mañana, desde las 00:00 a las 14:00
  * **ai_hour**: Inicio jornada tarde, desde las 14:00 a las 23:55
  * **ae_hour**: Fin jornada tarde, desde las 14:00 a las 23:55
_____________________
**Síntoma 3**: 
Si en la "Traza / Asignados" no carga la tabla de datos, debes revisar que el servicio BioPacs esté habilitado.
_____________________
**Síntoma 4**:
Si al usuario no le cargan las agendas en el menú "Agendas",
1. Revisar en el menú "Salas / Salas de usuario" y asignar las salas que no visualiza.
