# Conexión a Hospital Regional de Talca
## *En este documento encontrarás como conectarte a los sistemas BioRis y Biopacs del Hospital regional de Talca.*
__________________________________________________________
1. **Puente para conexión a BioRis de HRT por consola**
* En la consola debes conectarte al sistema BioRis escribiendo el siguiente comando: 
*__ssh -N -f -o ProxyCommand="ssh toth@biopacs.hospitaldetalca.cl -W %h:%p" -L 8002:localhost:80 toth@10.3.205.71 (Con -F queda en background y sin -F debes tener la consola abierta).__*
> Nota: El puerto 8002 es referencial.

2. En la web debes abrir el pacs con la siguiente dirección: **http://localhost:8002**
> Nota: El puerto es el que configuraste en el punto 1.
__________________________________________________________
1. **Puente para conexión a Base de datos del sistema BioRis de HRT por consola**
* En la consola debes conectarte al sistema BioRis escribiendo el siguiente comando: *__ssh -N  -o ProxyCommand="ssh  toth@biopacs.hospitaldetalca.cl -W %h:%p" -L 30000:localhost:5432 toth@10.3.205.71__*
> Nota: El puerto 30000 es referencial.

2. Para conectarte a la base de datos, debes ingresar los siguientes datos:
* **Host: localhost**
* **Port: 30000**
> Nota: El puerto 30000 es referencial.
__________________________________________________________
1. **Puente para conexión a BioPacs de HRT por consola**
* En la consola debes conectarte al sistema BioPacs nuevo escribiendo el siguiente comando: 
*__“ssh -N -f -o ProxyCommand="ssh  toth@biopacs.hospitaldetalca.cl -W %h:%p" -L 8004:localhost:80 toth@10.3.205.70"__*
> Nota: El puerto 8004 es referencial.

* Luego debes abrir una nueva ventana en la consola conectarte al pacs antiguo escribiendo el siguiente comando:
*__“ssh -N -f -o ProxyCommand="ssh  toth@biopacs.hospitaldetalca.cl -W %h:%p" -L 10000:localhost:80 toth@10.3.205.73”__*
> Nota: El puerto 10000 es referencial.

* 3.- En la web debes abrir el pacs con la siguiente dirección: **“http://localhost:10000/newbiopacsOLD/index.php”**
__________________________________________________________
1. **Puente para conexión a Base de datos del sistema BioPacs de HRT por consola**
* En la consola debes conectarte al sistema BioRis escribiendo el siguiente comando: *__ssh -N  -o ProxyCommand="ssh  toth@biopacs.hospitaldetalca.cl -W %h:%p" -L 30000:localhost:5432 toth@10.3.205.70__*
> Nota: El puerto 30000 es referencial.

2. Para conectarte a la base de datos, debes ingresar los siguientes datos:
* **Host: localhost**
* **Port: 30000**
> Nota: El puerto 30000 es referencial.
