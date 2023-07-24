# Guía de comandos de terminal Linux/Unix para Coding Dojo

## ¿Qué es la terminal?
La terminal, es una herramienta incluída en la mayoría de sistemas operativos disponibles en la actualidad. Esta permite interactuar con el sistema operativo sin la necesidad de un entorno gráfico. Esta intereacción se realiza a través de palabras claves llamadas **comandos**. Cada comando es interpretado por la terminal como una *instrucción a realizar*.

Cada sistema operativo puede tener sus propias terminales y comandos. Esta guía está enfocada para el uso de terminales *linux y unix*, por lo que muchos de estos comandos y explicaciones **no** serán validas para máquinas con entorno Windows.

## ¿Qué es un intérprete de comandos?

El intérprete de comandos es el encargado de verificar qué código e instrucciones deben ejecutarse al momento de llamar a un comando. En el caso de linux/unix, existen múltiples intérpretes de comandos. Sin embargo, para esta guía nos enfocaremos en el intérprete **Bourne Again Shell (bash)**.

## Estructura de un comando
Un comando en una terminal normalmente tiene la siguiente estructura:
```bash
    <nombre_comando> [-<opción(es)>] [<entrada(s)>]
```
Ej

```bash
    ls -l /home/miusuario/
```
En este caso, el comando ```ls``` se llama con la opción ```-l``` y se le entrega como entrada la ubicación ```/home/miusuario/``` dentro del computador


A continuación se presenta una guía rápida de algunos de los comandos más útiles para terminal linux/unix.

## Índice de comandos
<div id="indice" />

**Índice**
1. [cd](#cd)
2. [cat](#cat)
3. [pwd](#pwd)
4. [ls](#ls)
5. [mkdir](#mkdir)
6. [rm](#rm)
7. [touch](#touch)
8. [mv](#mv)
9. [cp](#cp)
10. [sudo](#sudo)

<div id='cd' />

### 1. Change Directory (```cd```)

Permite cambiar el directorio activo de trabajo para la terminal en ejecución. Para ello se debe utilizar el árbol de directorios (para más información respecto al árbol de directorios, revisar [aquí](https://computernewage.com/2015/06/14/el-arbol-de-directorios-de-linux-al-detalle-que-contiene-cada-carpeta/)) 

Ejemplos de uso:
```bash
[miusuario@localhost]$ cd /home/miusuario/ # Se cambia al directorio siguiendo la ruta completa /home/miusuario/ 
[miusuario@localhost]$ cd ~/ # Se cambia al directorio home de miusuario (misma ruta anterior abreviada)
[miusuario@localhost]$ cd . # Se cambia al directorio actual (no cambia de directorio)
[miusuario@localhost]$ cd Images/jpg/ # Se cambia a la carpeta Images/jpg a partir del directorio actual
[miusuario@localhost]$ cd ../ # Se retrocede un directorio
```

Documentación ```cd```: https://man7.org/linux/man-pages/man1/cd.1p.html

<div id='cat' />

### 2. Concatenate command (```cat```)

Muestra el contenido de uno o múltiples archivos a través de la terminal. Solo permite visualizar archivos, mas no editarlos.

Ejemplos de uso:

```bash
[miusuario@localhost]$ cat archivo.txt # Muestra contenido de archivo.txt
Este es el contenido de un 
archivo de texto plano.
Puede ser fácilmente visualizado
a través del comando cat.
[miusuario@localhost]$ cat -n archivo.txt # Muestra el contenido con líneas enumeradas
1  Este es el contenido de un 
2  archivo de texto plano.
3  Puede ser fácilmente visualizado
4  a través del comando cat.
[miusuario@localhost]$ cat archivo.txt archivo2.txt # Muestra el contenido de dos archivos
Este es el contenido de un 
archivo de texto plano.
Puede ser fácilmente visualizado
a través del comando cat.
Este es el contenido de otro 
archivo de texto plano.
Al igual que archivo.txt,
también puede ser fácilmente 
visualizado a través del comando cat.
```

Documentación ```cat```: https://man7.org/linux/man-pages/man1/cat.1.html

<div id='pwd' />

### 3. Print Working Directory (```pwd```)

Muestra la ruta completa del directorio activo en la terminal

Ejemplo de uso:

```bash
[miusuario@localhost]$ pwd # Muestra la ruta del directorio activo
/home/miusuario
```

Documentación ```pwd```: https://man7.org/linux/man-pages/man1/pwd.1.html

<div id='ls' />

### 4. List (```ls```)

Lista todo el contenido de un directorio. Por omisión, ```ls``` muestra el contenido del directorio activo, sin embargo es posible entregarle como parámetro de entrada la ruta del directorio que se desea explorar.
```ls``` admite también permite una variedad de opciones que permiten modificar la formar de visualizar este contenido dentro del directorio.

Ejemplos de uso:

```bash
[miusuario@localhost]$ ls # Muestra los archivos y carpetas que se encuentran en el directorio activo
archivo2.txt  archivo.txt Images
[miusuario@localhost]$ ls /home/miusuario/Images/ # Muestra los archivos y carpetas que se encuentran en el directorio Images
foto1.jpg foto2.jpg foto3.jpg
[miusuario@localhost]$ ls -l # Muestra los archivos y carpetas con un extenso listado de detalles
total 12
-rw-rw-r-- 1 miusuario miusuario  151 Mar 20 22:24 archivo2.txt
-rw-rw-r-- 1 miusuario miusuario  113 Mar 20 22:21 archivo.txt
drwxrwxr-x 2 miusuario miusuario 4096 Mar 20 22:33 Images
[miusuario@localhost]$ ls -a # Muestra todos los archivos y carpetas, incluídos aquellos ocultos (parten su nombre con ".")
.  ..  archivo2.txt  archivo.txt  .escondido  Images
```

Documentación ```ls```: https://man7.org/linux/man-pages/man1/ls.1.html

<div id='mkdir' />

### 5. Make Directory (```mkdir```)

Permite crear nuevas carpetas. Por omisión, se crea una nueva carpeta en el directorio activo. Sin embargo, es posible entregar la ruta completa donde se encontrará la nueva carpeta, siempre y cuando esta ruta **exista**.

Ejemplos de uso:

```bash
[miusuario@localhost]$ mkdir new_folder # Crea una nueva carpeta llamada "new_folder" en el directorio activo
[miusuario@localhost]$ mkdir Images/jpg_folder # Crea una nueva carpeta llamada "jpg_folder" en el directorio con ruta Images/
```

Documentación ```mkdir```: https://man7.org/linux/man-pages/man1/mkdir.1.html

<div id='rm' />

### 6. Remove (```rm```)

Permite eliminar los archivos cuyos nombres se entregan como entrada. Por omisión, estos archivos deben encontrarse en el directorio activo, pero es posible eliminar archivos en otras ubicaciones siempre y cuando se entregue su ruta respectiva.
También puede usarse para eliminar carpeta con la opción *-r, recursiva*. En otro caso, utilizar el comando **Remove Directory (```rmdir```)**

Ejemplos de uso:

```bash
[miusuario@localhost]$ rm archivo.txt # Borra archivo.txt
[miusuario@localhost]$ rm archivo.txt archivo2.txt # Borra los archivos archivo.txt y archivo2.txt
[miusuario@localhost]$ rm /home/miusuario/archivo.txt # Borra archivo.txt utilizando su ruta de acceso 
```
**Nota importante**: Borrar un archivo utilizando el comando ```rm``` elimina el archivo de forma **permanente**.

Documentación ```rm```: https://man7.org/linux/man-pages/man1/rm.1.html

<div id='touch' />

### 7. Touch (```touch```)

Archivo que permite modificar la fecha de creación de un archivo tomando su nombre como entrada. Si dicho archivo no existe previamente, se crea un archivo vacío con dicho nombre.

Ejemplos de uso:

```bash
[miusuario@localhost]$ ls -lh # Listando los datos de los archivos existentes
total 8.0K
-rw-rw-r-- 1 miusuario miusuario 151 Mar 20 22:24 archivo2.txt
-rw-rw-r-- 1 miusuario miusuario 113 Mar 20 22:21 archivo.txt
[miusuario@localhost]$ touch archivo.txt # Modifica la fecha de creación de archivo.txt
[miusuario@localhost]$ ls -lh
total 8.0K
-rw-rw-r-- 1 miusuario miusuario 151 Mar 20 22:24 archivo2.txt
-rw-rw-r-- 1 miusuario miusuario 113 Mar 20 23:00 archivo.txt
[miusuario@localhost]$ touch archivo3.txt # Crea el archivo vacío archivo3.txt con fecha de creación actual 
[miusuario@localhost]$ ls -lh
total 8.0K
-rw-rw-r-- 1 miusuario miusuario 151 Mar 20 22:24 archivo2.txt
-rw-rw-r-- 1 miusuario miusuario   0 Mar 20 23:01 archivo3.txt
-rw-rw-r-- 1 miusuario miusuario 113 Mar 20 23:00 archivo.txt
```

Documentación ```touch```: https://man7.org/linux/man-pages/man1/touch.1.html

<div id='mv' />

### 8. Move (```mv```)

Permite mover archivos y carpetas de una ruta de origen a una ruta de destino. También es utilizado en ocasiones para renombrar archivos, aunque se recomienda el comando ```rename``` para esta tarea.

Ejemplos de uso:

```bash
[miusuario@localhost]$ ls # Listando archivos y carpetas existentes en directorio activo
archivo.txt archivo2.txt Images
[miusuario@localhost]$ mv archivo.txt Images/ # Mueve archivo.txt dentro de la carpeta Images/
[miusuario@localhost]$ ls 
archivo2.txt Images
[miusuario@localhost]$ ls Images/
archivo.txt foto1.jpg foto2.jpg foto3.jpg
[miusuario@localhost]$ mv Images/archivo.txt ./ # Moviendo nuevamente archivo.txt al directorio activo
[miusuario@localhost]$ ls
archivo.txt archivo2.txt Images
```

Documentación ```mv```: https://man7.org/linux/man-pages/man1/mv.1.html

<div id='cp' />

### 9. Copy (```cp```)

Permite copiar uno o múltiples archivos desde una ruta de origen a una ruta de destino. También es posible cambiar el nombre del archivo de destino en la copia.

Ejemplos de uso:

```bash
[miusuario@localhost]$ ls # Listando archivos y carpetas existentes en directorio activo
archivo.txt archivo2.txt Images
[miusuario@localhost]$ ls Images/ # Listando archivos y carpetas en carperta Images/
foto1.jpg foto2.jpg foto3.jpg
[miusuario@localhost]$ cp archivo.txt Images/ # Copia archivo.txt dentro de la carpeta Images/
[miusuario@localhost]$ ls
archivo.txt archivo2.txt Images
[miusuario@localhost]$ ls Images/
archivo.txt foto1.jpg foto2.jpg foto3.jpg
```

Documentación ```cp```: https://man7.org/linux/man-pages/man1/cp.1.html

<div id='sudo' />

### 10. Super User Do (```sudo```)

En ocasiones, debido a su potencial peligrosidad, existen contextos en los que no cualquier usuario puede ejecutar ciertos comandos y solo el **administrador** del sistema puede usar estos permisos. El comando ```sudo``` permite solicitar estos permisos de administrador (si se los tiene) para ejecutar comandos que normalmente no se podría ejecutar.

Ejemplos de uso:

```bash
[miusuario@localhost]$ apt update # Comando para actualización de repositorios para distribuciones linux basadas en Debian
Reading package lists... Done
E: Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)
E: Unable to lock directory /var/lib/apt/lists/
W: Problem unlinking the file /var/cache/apt/pkgcache.bin - RemoveCaches (13: Permission denied)
W: Problem unlinking the file /var/cache/apt/srcpkgcache.bin - RemoveCaches (13: Permission denied)
[miusuario@localhost]$ sudo apt update # Solicitud de ejecución con permisos de administrador
[sudo] password for miusuario: # Se solicita password de administrador
Get:1 file:/var/cuda-repo-ubuntu2004-11-5-local  InRelease
Ign:1 file:/var/cuda-repo-ubuntu2004-11-5-local  InRelease
Get:2 file:/var/cudnn-local-repo-ubuntu2004-8.3.1.22  InRelease
Ign:2 file:/var/cudnn-local-repo-ubuntu2004-8.3.1.22  InRelease
Get:3 file:/var/cuda-repo-ubuntu2004-11-5-local  Release [564 B]
...
Get:31 http://security.ubuntu.com/ubuntu focal-security/multiverse amd64 DEP-11 Metadata [2,464 B]
Fetched 1,154 kB in 1s (861 kB/s)                                             
Reading package lists... Done
Building dependency tree       
Reading state information... Done
All packages are up to date. # Ejecución correcta!

```

Documentación ```sudo```: https://man7.org/linux/man-pages/man8/sudo.8.html