# Software de un Sistema Informático

Un **sistema informático** es un **conjunto de partes que trabajan en conjunto para cumplir un objetivo específico.**  
Está compuesto por tres elementos principales:

1. **Hardware**: Elementos físicos del sistema (CPU, memoria, disco duro, etc.).
2. **Software**: Elementos lógicos, como programas y sistemas operativos.
3. **Usuarios**: Las personas que interactúan con el sistema.

---

## Tipos de Software

### **1. Software de Propósito General**
Programas que cumplen funciones amplias y no específicas.  
Ejemplos:
- **Bases de datos**: Microsoft Access, Base de LibreOffice.
- **Editores de contenido**: Microsoft FrontPage (HTML, XML).
- **Paquetes ofimáticos**: Microsoft Office, Google Workspace.
- **Compresores de archivos**: WinRAR, 7-Zip.

### **2. Software de Propósito Específico**
Programas diseñados para tareas concretas.  
Ejemplos:
- **Entornos de desarrollo**: C, Java, Visual Studio, Borland Builder C++.
- **Administración de bases de datos**: Oracle, phpMyAdmin.
- **Edición de imágenes**: Photoshop, GIMP.

---

## Licencias de Software

Las licencias determinan cómo puede ser usado el software. Aquí los principales tipos:

### **1. GNU**
Licencia de software libre que garantiza:
- Libertad para usar, copiar, estudiar y modificar el software.
- Ejemplo: Linux (distribuciones como Ubuntu o Fedora).

### **2. CLUF (Contrato de Licencia para Usuario Final)**
Acuerdo legal entre el desarrollador y el usuario que establece:
- Permisos y restricciones del uso del software.
- Ejemplo: Al instalar Windows, aceptas un CLUF.

### **3. OEM (Original Equipment Manufacturer)**
Software vendido junto con hardware específico:
- Está preinstalado en el dispositivo.
- Ejemplo: Windows preinstalado en ordenadores nuevos.

### **4. Licencia por Volumen**
Usada por empresas para instalar software en varios equipos:
- Permite activar múltiples copias con una única clave.
- Ejemplo: Microsoft Office para empresas.

---

### Software de un Sistema Informático

El **sistema operativo** es la capa que permite usar el ordenador sin interactuar directamente con el hardware o software a bajo nivel.  

#### **El Kernel o Núcleo**
- Parte central del sistema operativo, cargada en la RAM.  
- Administra servicios y recursos (procesos, memoria, dispositivos, etc.).

### Tipos de Sistemas Operativos (por estructura)

1. **Monolíticos**: Todo en un único núcleo. Ejemplo: MS-DOS.  
2. **Jerárquicos**: Funciones organizadas por niveles. Ejemplo: UNIX.  
3. **Por Capas**: Dividido en niveles independientes. Ejemplo: THE.  
4. **Microkernel**: Núcleo mínimo, funciones externas. Ejemplo: MINIX.  
5. **Cliente-Servidor**: Clientes solicitan servicios a servidores. Ejemplo: Windows Server.  
6. **Máquina Virtual**: Simulan hardware para ejecutar varios sistemas. Ejemplo: VMware.

---

## Estados de los Procesos y Bloque de Control

### Proceso
La ejecución de un programa genera un **proceso** principal que controla subprocesos o hilos de ejecución.  

### **Estados de los Procesos**
1. **Ejecución**: En curso. Solo uno por núcleo.  
   - Ejemplo: Un navegador cargando una página.  
2. **Preparado**: Listo, esperando procesador.  
   - Ejemplo: Una aplicación en segundo plano.  
3. **Bloqueado**: Pausado, esperando recurso.  
   - Ejemplo: Un archivo pendiente de impresión.  
4. **Muerto**: Finalizado por éxito o error.  
   - Ejemplo: Cierre de un editor de texto.  

El **planificador de procesos** gestiona los cambios de estado.

### **Bloque de Control de Procesos (BCP)**
El sistema operativo almacena:  
- **PID**: Identificador único.  
- **Estado**: Actual del proceso.  
- **Prioridad**: Orden de ejecución.  
- **Memoria**: Dirección de datos.  
- **Tiempos**: Inicio, espera, ejecución restante.  

#### Ejemplos:
- **Windows**: Ver procesos con Ctrl+Alt+Supr → *Procesos*.  
- **Linux**: Usar `ps -efl` para listar procesos.  

## Planificador de Procesos y Algoritmos

### Multitarea
Aunque **solo un proceso** puede ejecutarse por núcleo, los sistemas operativos son **multiproceso**: el procesador cambia de tarea tan rápido que parece que se ejecutan múltiples tareas al mismo tiempo. Ejemplo: escuchar música y navegar por internet simultáneamente.

---

### **Algoritmos de Planificación**
El **planificador de procesos** decide qué proceso se ejecuta en cada momento. Existen varios algoritmos, cada uno con sus ventajas y desventajas.

1. **FIFO (First In, First Out)**: El primer proceso que llega, es el primero en ejecutarse.
   - Ejemplo: Colas en tiendas, el primero en llegar, primero en ser atendido.
   
2. **SJF (Shortest Job First)**: Ejecuta primero el proceso con menor tiempo de ejecución.
   - Ejemplo: Priorizar una tarea rápida, como abrir un archivo pequeño, antes que uno más pesado.

3. **SRT (Shortest Remaining Time)**: Interrumpe un proceso activo si llega uno más corto.
   - Ejemplo: Si un proceso está por terminar en 3 unidades, pero llega uno que termina en 1, el primero se suspende.
   - Expropiativo: Un proceso activo puede ser detenido.

4. **Round Robin (RR)**: Se asigna un tiempo de ejecución fijo (time slice) a cada proceso, pasando al siguiente cuando se cumple.
   - Ejemplo: Como un turno circular, cada tarea recibe tiempo limitado para ejecutarse.
   - Desventaja: El cambio de proceso constante ralentiza el sistema.

5. **Prioridades**: El proceso con mayor prioridad se ejecuta primero. La prioridad puede ser asignada por el usuario o el sistema.
   - Ejemplo: Un proceso urgente, como un antivirus, tiene mayor prioridad que otros.

   **Prioridad por envejecimiento**: Si un proceso lleva mucho tiempo esperando, su prioridad aumenta para evitar que se quede bloqueado indefinidamente.

---

### **Combinación de Algoritmos**
Los sistemas actuales combinan algoritmos como **SRT con prioridades** o **Round Robin con prioridades** para optimizar el rendimiento. FIFO y SJF se usan para desempatar en algunos casos.

---

### Gestión de la Memoria: Tipos de Particiones

1. **Particiones Fijas**  
   - La memoria se divide en bloques de tamaño fijo. Cada proceso se asigna a una partición.  
   - **Ejemplo**: En MS-DOS, con 4 MB de RAM, 3,5 MB se dividían en 3 particiones de 512 KB, 1 MB y 2 MB.
   - **Desventaja**: Fragmentación interna (espacio no aprovechado dentro de las particiones).

2. **Particiones Variables**  
   - Cada proceso recibe solo el espacio necesario. Los bloques se liberan y se reasignan cuando el proceso termina.  
   - **Ejemplo**: Si un proceso ocupa 3 MB, se le asigna solo esa cantidad.  
   - **Desventaja**: Fragmentación externa (espacios pequeños no aprovechables entre procesos).

3. **Paginación**  
   - La memoria se divide en páginas de igual tamaño. Los procesos usan las páginas necesarias, no tienen que ser contiguas.  
   - **Ejemplo**: Si un proceso necesita 31 KB, usará 8 páginas de 4 KB, aunque no estén juntas.  
   - **Ventaja**: Alta eficiencia, casi sin fragmentación.  
   - **Desventaja**: Requiere mayor poder de procesamiento y gestión.  
   - El sistema operativo realiza compactación para organizar las páginas.

---
## Memoria Virtual (Windows) vs Memoria Swap (Linux)

### Memoria Virtual en Windows
- **Función**: Extiende la capacidad de la RAM utilizando el disco duro como memoria adicional.
- **Cómo funciona**: Al llenar la RAM, el sistema mueve datos al disco duro (archivo `pagefile.sys`). Si se necesita esa información, se vuelve a cargar en la RAM.
- **Ventaja**: Permite simular más RAM (por ejemplo, con 2 GB de RAM, puedes tener hasta 6 GB de memoria total).
- **Desventaja**: El disco duro es más lento que la RAM, lo que reduce el rendimiento.
- **Tamaño**: Suele ser entre 1 y 2 veces el tamaño de la RAM.

### Memoria Swap en Linux
- **Función**: Similar a la memoria virtual de Windows, pero utiliza una partición específica del disco duro llamada "swap".
- **Ventaja**: No depende de la partición de datos y, si está en la primera partición, mejora la velocidad.
- **Monitoreo**: En Linux, se puede ver el uso de la RAM y swap con el comando `free`.
- **Tamaño**: Generalmente, se recomienda entre 1 y 2 veces el tamaño de la RAM.

### Diferencias y Tendencias Actuales
- **Con RAM grande**: Hoy en día, las PCs suelen tener suficiente RAM, lo que ha llevado a cuestionar si es necesario configurar memoria virtual o swap.
- **Configuración**: En equipos con mucha RAM, el tamaño de la memoria virtual o swap se iguala al de la RAM. Si la RAM es limitada, se recomienda el doble de swap.

**Resumen**: Ambos conceptos permiten expandir la memoria disponible, pero la memoria swap en Linux ofrece algunas ventajas de rendimiento al estar en una partición separada. Con equipos modernos de gran capacidad RAM, la necesidad de estas configuraciones es menor.

---

### Estructura y transferecnia de datos

Controladores de dispositivos

---

## Estructura y Transferencia de Datos en los Sistemas Operativos

### Controladores de Dispositivo (Drivers)
- **Función**: Los controladores permiten que los programas de aplicación se comuniquen con los dispositivos periféricos. Dado que existen muchos tipos de periféricos de diferentes fabricantes, tanto el sistema operativo como los fabricantes deben estandarizar el acceso a los dispositivos.
- **Definición**: Un controlador o driver es un software proporcionado por el fabricante del dispositivo o el desarrollador del sistema operativo. Actúa como una interfaz entre el hardware (dispositivos periféricos) y los programas de aplicación.

### Estructura de Datos de Entrada/Salida (E/S)
- **Spool**: Los datos de salida se almacenan temporalmente en una cola en un dispositivo de almacenamiento (spool) hasta que el dispositivo periférico esté libre. Esto evita que el programa se quede esperando si el periférico no está disponible. Se usa especialmente en dispositivos como impresoras, que no pueden realizar múltiples tareas al mismo tiempo.
- **Buffers**: Se utilizan para manejar datos que provienen de diferentes fuentes o que van hacia dispositivos con diferentes velocidades. El buffer retiene temporalmente los datos para que el dispositivo los procese a su propio ritmo. Por ejemplo, en una grabadora de DVD, el buffer retiene la información para que la grabadora no se quede esperando a que la CPU le entregue más datos.

### Transferencia de Datos de E/S
Existen varias formas de transferir datos entre la memoria y los dispositivos periféricos, con diferentes niveles de intervención de la CPU. De menor a mayor eficiencia:

1. **E/S Programada**: La CPU es la responsable de iniciar y ejecutar toda la transferencia de datos. Esto puede ralentizar el proceso, ya que la CPU debe interrumpir otras tareas para manejar la E/S.
  
2. **E/S por Interrupciones**: En esta modalidad, la CPU no consulta constantemente al dispositivo; en cambio, el dispositivo avisa a la CPU cuando está listo para realizar la transferencia. Esto optimiza el uso de la CPU, ya que solo interviene cuando es necesario.

3. **Acceso Directo a Memoria (DMA)**: En este tipo de transferencia, un controlador especializado se encarga de mover los datos entre la memoria y el dispositivo, sin necesidad de intervención de la CPU. Esto libera a la CPU y acelera significativamente el proceso de E/S.

### Resumen
- **Drivers**: Intermediarios entre los dispositivos y los programas de aplicación.
- **Estructura de datos**: Spool y buffers se usan para gestionar la información de los dispositivos periféricos.
- **Transferencia de datos**: Existen distintas técnicas (programada, por interrupciones, y DMA) que varían en eficiencia y uso de la CPU.

---

## Organización Lógica: Directorios y Archivos

### Sistema de Archivos
Cada sistema operativo utiliza su propio sistema de archivos, pero las operaciones comunes que se pueden realizar son muy similares en todos ellos. Uno de los conceptos fundamentales en cualquier sistema de archivos son los **directorios** o **carpetas**, que permiten organizar los archivos en el sistema.

### Objetivos Principales en la Implementación de un Sistema de Archivos
1. **Optimización del rendimiento**: Acceso rápido a los archivos para recuperar la información de manera eficiente.
2. **Fácil actualización**: Añadir, borrar o modificar archivos de manera sencilla tanto para el usuario como para las aplicaciones.
3. **Economía de almacenamiento**: Minimizar el desperdicio de espacio en disco, evitando la fragmentación.
4. **Mantenimiento sencillo**: Las operaciones deben ser fáciles de gestionar para los usuarios, ocultando detalles complejos del sistema.
5. **Fiabilidad**: Asegurar que los datos escritos o leídos sean correctos y fiables.
6. **Seguridad y permisos**: Proteger los archivos de accesos no autorizados mediante el control de permisos (lectura, escritura, ejecución).
7. **Control de concurrencia**: Gestionar el acceso a archivos por parte de múltiples usuarios simultáneamente, bloqueando archivos durante modificaciones para evitar errores.

### Organización Lógica del Sistema de Archivos
Los sistemas de archivos deben facilitar el uso del almacenamiento de manera intuitiva y organizada. Esto se logra mediante el uso de directorios (carpetas) que funcionan como contenedores para los archivos.

- **Directorios/Carpetas**: Son contenedores que agrupan archivos, pero no contienen información por sí mismos. La información se encuentra exclusivamente en los archivos.
  
### Características de un Archivo
Cada archivo dentro de un sistema tiene atributos que lo identifican:
- **Nombre**: Las reglas para nombrar archivos varían según el sistema operativo (longitud, caracteres permitidos).
- **Extensión**: Indica el tipo de contenido del archivo (ej. `.TXT` para texto, `.EXE` para ejecutables).
- **Permisos**: Controlan qué usuarios pueden realizar ciertas operaciones (lectura, escritura, ejecución).
- **Propietario**: El usuario que posee el archivo (generalmente quien lo crea).
- **Fecha de creación**: Momento en que se creó el archivo.
- **Fecha del último acceso**: Última vez que se accedió al archivo.
- **Fecha de la última modificación**: Momento en que se modificó el archivo por última vez.
- **Tamaño**: El tamaño del archivo en bytes, es decir, el espacio que ocupa en el disco.

### Operaciones Básicas sobre Archivos y Carpetas
Los sistemas de archivos permiten realizar varias operaciones comunes, como:
- Crear
- Borrar
- Abrir
- Cerrar
- Leer
- Renombrar
- Crear enlaces (accesos directos)

### Jerarquía de Directorios y Árboles de Archivos
La organización de los archivos en la mayoría de los sistemas operativos sigue una estructura jerárquica similar a un árbol, donde cada directorio puede contener otros directorios y archivos.

#### Unidades Físicas vs. Unidades Lógicas
- **Unidades físicas**: Son los dispositivos reales de almacenamiento, como discos duros, disquetes o CD-ROM.
- **Unidades lógicas**: Son las representaciones que el sistema operativo hace de las unidades físicas, gestionando el acceso a ellas.

Por ejemplo, un disco duro con 3 particiones se representa en Windows como unidades lógicas C:, D:, y E:. En sistemas como Linux, las unidades lógicas no se representan por letras, sino que están montadas en un único árbol de directorios.

#### Ejemplo de Jerarquía:
- **Windows**: El sistema tiene varias unidades lógicas, cada una con su propio árbol de archivos.
- **Linux**: Aunque tenga varias particiones, el sistema usa un único árbol jerárquico para gestionar todos los archivos y directorios.

### Conclusión
La organización lógica de archivos en los sistemas operativos es fundamental para la gestión eficiente del almacenamiento y el acceso a los datos. El uso de directorios, la definición de atributos de archivos y las operaciones básicas sobre ellos proporcionan un sistema sencillo y funcional para el manejo de archivos en el día a día.
