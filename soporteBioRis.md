# Soporte BioRis
## En éste documento encontrarás los procesos habituales de soporte para el sistema BioRis
_____________________
**Síntoma 1**:
Si en la agenda aparece un gif "cargando" y no permite visualizar horarios ni citas, debes revisar lo siguiente:
* Campo **"hour_c"** de la tabla **calendar** de la semana en la cual presente problemas: en algunos casos existen más de una cita en el mismo horario, se debe corregir modificando la hora de una de las citas.
* Revisar **"date_s"** de la tabla **schedule** de la semana en la cual presente problemas: en algunos casos existen más de un horario duplicado, se debe corregir modificando la hora de los horarios en cuestion.
_____________________
