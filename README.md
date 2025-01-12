SPRINT 1

# SPRINT 2

## 1. Instalación Duplicati
### Modificar archivo de repositorios 

Para poder instalar Duplicati, primero tendremos que especificar a nuestro servidor, que pueda descargar desde cualquier repositorio (ya que en la práctica anterior restringimos este aspecto), por lo tanto, quitamos los “ # “ para poder buscar en más repositorios, sean o no programas probados y verificados.

### Instalar paquetes .deb
Por mi parte, instalaremos el paquete .deb por interficie gráfica, aunque por terminal de comandos también se puede realizar mediante 
“ wget https://updates.duplicati.com/beta/duplicati_2.0.2.1-1_all.deb “

### Ejecutar los paquetes .deb y restringir repositorios

Para poder ejecutar el paquete .deb, primero le damos permisos de ejecución con el siguiente comando: “ sudo chmod +x duplicati_…….. “ 

Seguidamente, ejecutamos con: “ sudo dpkg -i duplicati_…… “


Al intentar instalar Duplicati, nos dará diferentes errores de instalación, para remediarlo, realizamos un “ sudo apt-get install -f “


Para finalizar, comentamos los repositorios del documento “ sources.list “ (no se comentarán las dos líneas que aparecen a color en la siguiente captura)


	





## 2. Copia “Documentos”	
Una vez realizada la instalación, podemos comprobar que al abrirla, nos aparecerá una interficie tal que así:

Nos dirigimos a crear una nueva copia de seguridad, para ello, iremos al apartado “Añadir copia de seguridad”, “Configurar nueva copia de seguridad”

Asignamos el nombre a este proceso de copias de seguridad, en este caso será “Documentos”, asignaremos un cifrado AES-256


A continuación indicamos donde queremos guardar estas copias de seguridad, en este caso será nuestro Google Drive personal. Por lo tanto, en el desplegable de “Tipo de Almacenamiento” elegiremos Google Drive.
Si clicamos en AuthorID, podremos loguear en nuestro propio Google Drive.

Elegiremos la carpeta de la cual queremos realizar las copias de seguridad.

Uno de los pasos finales será elegir la frecuencia en la que queremos realizarlas. En nuestro caso será de lunes a, y como máximo queremos perder la información de una hora de trabajo, asignaremos que se realizarán cada 30 minutos. (ahora mismo la hora a la que empiezanempieza las copias no es relevante, ya que es un entorno simulado, en el caso de ser un entorno de trabajo real, quizá se asignaronasignarían horas diferentes).

Para finalizar, podremos elegir el tamaño de volumen, como ahora mismo no hay demasiados archivos, podemos decir que estos volúmenes sean de 50 MBytes.

## 3. Copia “Imágenes”
Nos dirigiremos a crear una nueva copia de seguridad, para ello, iremos al apartado “Añadir copia de seguridad”, “Configurar nueva copia de seguridad”.

Asignaremos el nombre a este proceso de copias de seguridad, en este caso será “Imágenes” y no asignaremos ningún cifrado.

Igual que anteriormente, guardaremos las copias de seguridad en nuestro Google Drive

Seleccionaremos que carpeta a la cual queremos realizar la copia de seguridad, en este caso es la carpeta “Imágenes”.

Asignaremos la frecuencia con la que queremos realizar esta copia de seguridad, por ejemplo, todos los días de la semana, con repetición en un lapso de un día, como sería en nuestro caso.


Para finalizar, podremos elegir el tamaño de volumen, como ahora mismo no hay demasiados archivos, podemos decir que estos volúmenes sean de 50 MBytes.


Podemos comprobar que nos aparecen las dos copias de seguridad que creamos anteriormente en la pestaña “Inicio”

## 4. Recuperación “Documentos”
Creamos diferentes documentos de prueba, ya que ahora mismo nuestro directorio está vacío, y recuperar archivos no creados sería inútil.

Asimismo, forzaremos que se ejecute la copia de seguridad (para no esperar el tiempo que está configurado por defecto). Realizamos esta acción para que, al terminar, borremos algunos archivos (simulamos que el borrado es un encriptado de algún malware) para posteriormente poder recuperarlos.

Eliminaremos estos documentos, por ejemplo. Así que el directorio documentos nos quedara con solo tres archivos al momento de eliminar los tres primeros.
Se usa < rm “nombre del fichero” > para eliminarlo y < ls -l > para ver el contenido del directorio

Para recuperarlos, vamos a “Restaurar” en Duplicati.

Una vez en “Restaurar” tendremos diferentes características, es interesante porque nos aparecen las distintas copias de seguridad programadas en el sistema (ejemplo “Documentos” o “Imágenes”). 
Vamos a “Documentos”, donde están las copias que nos interesan.

Elegimos que copia de seguridad de la que queremos recuperar algún archivo, en mi caso es la que está marcada en la siguiente imagen.

Nos dirigiremos a la carpeta donde están los archivos existentes antes de ser eliminados, en mi caso “Documentos”, y se puede observar que todos los archivos están en dicha carpeta.

Por lo tanto, elige los archivos que se quieran recuperar, en mi caso son: 
doc.txt
doc4.txt
doc5.txt

Antes de continuar vamos a crear un directorio en el escritorio para poder situar los documentos que recuperemos con la copia de seguridad.

Para crear un directorio, nos dirigiremos a este mediante < cd “ruta del directorio” > y con <mkdir “nombre” > creamos el directorio.

A continuación, elegimos la ubicación donde colocar los archivos que se recuperan, como manejarlos y si restaurar los permisos.
En mi caso, elijo el directorio creado anteriormente en el escritorio, los sobreescribo y restauro los permisos (la captura dice lo contrario, pero, pensándolo mejor una vez echo, sería importante para que el usuario no tenga que volver a asignar los permisos a cada archivo)

Tarda un momento para recuperar los archivos desde la copia en el Google Drive, y al finalizar, nos saldrá una alerta donde nos dirá que todo fue restaurado con éxito.

Si nos dirigimos al directorio que creamos anteriormente, veremos que estos archivos están en esta.


## 4. Recuperación “Imágenes”
Creamos diferentes archivos de prueba, para comprobar si la restauración de las copias de seguridad funciona correctamente. Creamos algunos archivos para hacer visual que la recuperación funciona. En mi caso son estos, pero puede ser cualquier fichero, de cualquier extensión y de cualquiercualcuier nombre.

Nos dirigimos a la parte de “Inicio” de Duplicati y nos situaremos donde nos aparece nuestra copia de seguridad con el nombre “Imágenes”, desplegamosdesplegaremos el submenú y en “Operaciones” clicamos en “Ejecutar ahora” para forzar una copia de seguridad y no tener que esperar las 24 horas que tarda en realizarse.

Seguidamente, nos dirigimos a “Restaurar” para empezar la recuperación, seguidamente seleccionamos de que copia de seguridad queremos recuperar los archivos correspondientes, en este caso, queremos enfocarnos en la copia de seguridad “Imágenes”.

Antes de iniciar la recuperación, eliminaremos algunos de los archivos, simulando fallo en el equipo, encriptado o eliminación errónea del usuario.
Se usa < rm “nombre del fichero” > para eliminarlo y < ls -l > para ver el contenido del directorio.

También crearemos un directorio en el escritorio para situar los archivos que se van a restaurar, para seguir con las buenas prácticas.
Para crear un directorio, nos dirigiremos a este mediante < cd “ruta del directorio” > y con <mkdir “nombre” > creamos el directorio.

Una vez, los archivos ya no están en el equipo, seguimos con la recuperación desde Duplicati.
Elegimos la última versión de la copia de seguridad (es la que forzamos anteriormente) y elegimos los archivos que queremos recuperar, en esta prueba son los que eliminamos anteriormente.

A continuación, elegimos la ubicación donde colocar los archivos que se recuperan, como manejarlos y si restaurar los permisos.
En mi caso, elijo el directorio creado anteriormente en el escritorio, los sobreescribo y restauro los permisos (la captura dice lo contrario, pero, pensándolo mejor una vez echo, sería importante para que el usuario no tenga que volver a asignar los permisos a cada archivo)

La recuperación tardará un momento, y al aparecer el siguiente mensaje de “Los archivos y carpetas han sido restaurados con éxito”, podremos revisar la carpeta donde quisimos realizar la recuperación, y todo listo, Los archivos vuelven a estar en manos del usuario.






SPRINT 3

SPRINT 4




[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)
