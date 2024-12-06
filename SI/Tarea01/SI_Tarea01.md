## Datos del alumno:

- **Título del archivo**: dieguez_barrio_andrea_SI01_Tarea
- **Fecha de entrega**: 06/12/2024


## Ejercicio 01

|                           | **Software Propietario**                  | **Software Libre**                           |
|---------------------------|-------------------------------------------|----------------------------------------------|
| **Paquetes de ofimática** | iWork (macOS) / Microsoft 365 (Windows)  | LibreOffice (Linux)                           |
| **Programa de correo**    | Mail (macOS) / Outlook (Windows)         | Thunderbird (Linux)                           |
| **Lector de archivos PDF**| Safari - Vista Previa (macOS) / Adobe Reader (Windows) | Evince (Linux)                  |
| **Navegador web**         | Safari (macOS) / Chrome (Windows)        | Brave / Firefox (Linux)                       |
| **Reproductor multimedia**| QuickTime (macOS) / Windows Media Player (Windows) | VLC Media Player                    |
| **Programa de agenda**    | Apple Calendar (macOS) / Microsoft Outlook (Windows) | KOrganizer (KDE - Linux)          |
| **Antivirus**             | McAfee / Norton (Windows, macOS)         | ClamAV (Linux)                                |
| **Editor de imágenes**    | Adobe Photoshop (macOS, Windows)         | GIMP (Linux)                                  |

---

## Ejercicio 02

### Apartado A - VB de Windows
Apartado 1. Procesos en Windows. Administrador de tareas (Realizar este apartado en una máquina Windows)

![Admin.tareas](/Tarea01/img_tareas/tarea02_1.png)

![Administración de tareas - Detalles](/Tarea01/img_tareas/tarea02_2.png)

![Administración de tareas - Prioridad](/Tarea01/img_tareas/tarea02_3.png)

---

### Apartado B - Linux
![Figura de la actividad](/Tarea01/img_tareas/TareaProcesos01.png)

1. ¿Cuántos procesos se han ejecutado desde que se ha encendido el ordenador
    - **3293**
    - *Explicación*: CMD ps -efl es el inicio de procesos y este marca PPID: 3293

2. ¿Cuál es el PID y el nombre del proceso con menor prioridad?
    - **2603 (tiene 10 de prioridad) nombre: usr/bin/python3**
    - *Explicación*: Para ver la prioridad de un proceso se observa el NI (NIce) si marca -20 es la máxima y 19 es la mínima

3. ¿Cuál es el PID y el nombre del proceso con mayor prioridad?
    - **5 (tiene -20 de prioridad) nombre: [kworker/0:0h]**

4. Comenzando por el proceso final, especificar su proceso padre, su abuelo, bisabuelo y así hasta llegar al proceso inicial.
    En este caso sería: 
    - **Proceso final**: PID 2603 - PPID 1865
    - **Proceso padre**: PID 1865 - PPID 1440
    - **Proceso abuelo**: PID 1440 - PPID 1227
    - **Proceso bisabuelo**: PID 1227 - PPID 1
    - **Proceso inicial**: PID 1 - PPID 0
    - *Explicación*: En un SIST. Operativo cada proceso se crea a partir de otro (excepto el init - inicial) 
    - Y la relacion entre ellos se da por <abbr title="Es el identificador del proceso que lo creó. Parent Process ID">PPID</abbr> y el <abbr title="Identificador único del proceso. Process ID">PID</abbr>

5. **¿Qué identificador de proceso (PID) tiene el proceso padre de todos los procesos? ¿Cómo se llama?**
    - El proceso inicial **PID 1 PPID 0 CMD /sbin/init**
    - *Explicación*: Aunque no se entiende muy bien, creo que cuando el ejercicio dice *"el proceso padre de todos los procesos"* se refiere al inicial y el inicial se sabe cual es por el CMD /init

---

## Actividad 3.

### Apartado A - VB de Windows
Apartado 1. Memoria en Windows (Realizar este apartado en una máquina Windows)

1. **¿Cuánta memoria RAM tiene el equipo?**  
   - **RAM instalada**: 8 GB  
2. **¿Cuánta memoria RAM se está consumiendo?**  
   - **Memoria en uso**: 1,4 GB  
    Vista de la Memoria desde la Máquina Virtual:
    ![MemoriadelVB](/Tarea01/img_tareas/Tarea03_1B.png)
    Detalle del consumo de Memoria:
    ![Memoria](/Tarea01/img_tareas/Tarea03_1.png)

3. **Monitor de recursos**
    - **Información general**: En esta sección se muestran los recursos clave del sistema operativo, detallando los procesos según el dispositivo que los gestiona: **CPU, MEMORIA, DISCO y RED**
    ![Informacióngeneral](/Tarea01/img_tareas/Tarea03_2.png)
    Entre los procesos activos resalto:  <abbr title= "Proceso del sistema operativo (núcleo NT). Gestiona operaciones esenciales del sistema.">System</abbr>> con un PID 4, Estado *EN EJECUCIÓN* y CPU 1%

    - **CPU**  En esta sección se muestran los recursos que lleva a cabo la CPU, algunos de los cuales están en azul lo que significa: que están suspendidos o inactivos.
    ![CPU](/Tarea01/img_tareas/Tarea03_5.png)
    En este caso resalto el proceso de <abbr title="Proceso de búsqueda de Windows (Cortana y barra de búsqueda)">SearchApp.exe</abbr> que muestra un PID 4048, Descripción *Search application*, Estado *Suspendido*, CPU 0%

    - **MEMORIA** En esta sección se muestra la cantidad de memoria en uso por los procesos (1201MB), la memoria utilizada y modificada, es decir la que no requiere de acceso al disco (45MB), memoria en espera (797MB) y memoria libre (4MB). Además disponible 801MB, En caché 842MB, Total 2047MB, Instalada 2047MB.
    ![Memoria](/Tarea01/img_tareas/Tarea03_6.png)
    En este caso resalto el proceso de <abbr title="Proceso relacionado con Microsoft Defender - antivirus de windows.">MsMpEng.exe</abbr> que muestra un PID 2216, Errores graves 0, asignación KB 138,552 me parece elevado en comparación con el resto y eso es porque puede estar teniendo trabajo, espacio de trabajo 98,312, se puede compartir 26,108, privada 72,204

    - **DISCO** En esta sección se muestra la actividad relacionada con el disco, reflejando la cantidad de datos que se leen o escriben. 
    ![Disco](/Tarea01/img_tareas/Tarea03_7.png)
    Como no sabía que era he investigado el proceso de **perfmon.exe**, que está vinculado al **Monitor de rendimiento de Windows**. PID 7032

    - **RED** En esta sección se muestra la actividad relacionada con la red, reflejando los procesos que utilizan la conexión a Internet o a una red local.
    ![Red](/Tarea01/img_tareas/Tarea03_8.png)
    En este caso, resalto el proceso **svchost.exe (NetworkService)** con PID 1288. Este proceso es un servicio de Windows que ejecuta varias funciones relacionadas con la red. Aunque su asignación de espacio en memoria no es tan alta (31,736 KB), tiene actividad de red, lo que sugiere que está gestionando comunicaciones entre el sistema y otros dispositivos en la red.

4. **Memoria virtual**
    - Memoria virtual: Un archivo de paginación es un área en el disco duro que Windows usa como si fuese RAM. Tamaño total del archivo de paginación para todas las unidades: **1152 MB**
    ![memoriavirtual](/Tarea01/img_tareas/Tarea03_10.png)

5. **Archivo pagefile.sys en la partición C**. 
    - Tamaño: 1,394,708KB
    ![Pagefile](/Tarea01/img_tareas/Tarea03_9.png)

---
### Apartado B - Memoria Linux
![EjercicioMemoriaLinux](/Tarea01/img_tareas/TareaMemoria02.png)

1. **¿Cuánta memoria RAM tiene el equipo?**
    *Memoria RAM*: 7,7G

2. **¿Cuánta memoria RAM se está consumiendo?**
    *Usando*: 7,6G

3. **¿Cuánta memoria swap tiene el equipo?**
    *Swap - compartida*: 7,8G

4. **¿Cuánta se está consumiendo?**
    *Swap consumida - buffers*: 4G

5. **¿Te parece bien configurada la swap? ¿Cuál debe ser el límite mínimo y máximo?**
    Supongo que sí, si la memoria del equipo es de 8GB de RAM, la RAM debe ser igual o más y en este caso es la misma capacidad: 8GB.
---
## Actividad 4.

### Instalar VirtualBox y Extension Pack  
![Instalar](/Tarea01/img_tareas/Tarea04_0.png)

### Instalar Windows 10  
Dado que ya tenía instalada la VirtualBox con Ubuntu, no seguí la nomenclatura exacta solicitada en la actividad y designé el nombre de la siguiente manera:  
- **Nombre de la máquina**: Windows_10_FP  
![Instalar](/Tarea01/img_tareas/Tarea04_1.png)
- **Nombre del usuario**: "Andrea Dieguez"  
![Instalar](/Tarea01/img_tareas/Tarea04_3.png)

### Requerimientos cumplidos:  
- **Memoria RAM**: 2GB (para instalación de 64 bits)  
- **Disco duro**: 100GB  
![Instalar](/Tarea01/img_tareas/Tarea04_2.png)

- **Versión de Windows**: Instalación de Windows 10 Pro  
![Instalar](/Tarea01/img_tareas/Tarea03_5.png)

- **Partición de Windows**: 50GB  
![Instalar](/Tarea01/img_tareas/Tarea04_6.png)

- **Instalar Guest Additions**  
![Instalar](/Tarea01/img_tareas/Tarea04_8.png)

- **Configurar carpeta compartida**  
![Instalar](/Tarea01/img_tareas/Tarea04_10.png)

- **Máquina virtual configurada**  
![Instalar](/Tarea01/img_tareas/Tarea04_11.png)

---

## Actividad 5.
Manipulaciones en VirtualBox.

1. Buscar archivo .vdi del disco duro de la máquina instalada. ¿Cuánto ocupa actualmente?  
![Instalar](/Tarea01/img_tareas/Tarea05_0.png)

2. Clonar la máquina en VirtualBox. Menú contextual en VirtualBox en el nombre de la máquina.  
![Instalar](/Tarea01/img_tareas/Tarea05_3.png)

3. Crear una instantánea de tu máquina  
![Instalar](/Tarea01/img_tareas/Tarea05_1.png)

**ENLACES DE INTERÉS PARA PODER RESOLVER LOS EJERCICIOS (Ya que con los apuntes, como que difícil)**

1. En mi caso intenté instalar la VirtualBox para MacOS: **imposible**. Está en versión beta para M1 y no da acceso; es más, muestra errores. Por ello instalé UTM ([video UTM](https://www.youtube.com/watch?v=rXggXImM0ks&ab_channel=Jhon3)), pero tiene un problema con el Guest y la pantalla se ve pixelada, no conseguí solucionar el problema. Así que opté por hacer la máquina virtual en mi otro PC con Windows a través de remote - dwservice.

2. [Video sobre instalación en Windows - VB](https://www.youtube.com/watch?v=YFlowDwE-1E&t=125s&ab_channel=ContandoBits)  
3. [Video sobre configuración de Guest](https://www.youtube.com/watch?v=I8dSe9SF3vc&ab_channel=FP%E2%80%9CREDESLOCALES%E2%80%9DINFORMATICA)  
4. [Video sobre Pagefile.sys (minuto 2:18)](https://www.youtube.com/watch?v=Tuc9OIoQToI&ab_channel=AskLeo%21)  
5. [Video sobre .vdi file](https://www.youtube.com/watch?v=8z4jcZgqJ_I&ab_channel=RecursivoWeb)
