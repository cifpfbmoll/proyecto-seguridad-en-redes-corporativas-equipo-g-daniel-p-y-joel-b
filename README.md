# SPRINT 1

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





# SPRINT 3

## 1.Instalación APACHE
Realizar un “ sudo apt update “ para actualizar los repositorios del equipo
Instalar apache desde terminal de comandos con “ sudo apt install apache2 “

Comprobar el estado del servicio apache2

Se ve la página por defecto de apache si buscamos nuestra IP (127.0.0.1) en el navegador

Cambiar contenido de la página mediante “ sudo echo “ Texto que se quiere “ > index.html

## 2. Configuraciones globales
### Ficheros de configuraciones
Los ficheros de configuración se encuentran en /etc/apache2/

Dentro de este directorio se pueden ver diferentes archivos y directorios que permiten configurar de forma global como de forma específica el propio servidor.

El fichero principal es apache2.conf, y es de donde parten todas las configuraciones y donde se incluyen los ficheros que hacen referencia a sitios configurador.

### Configuración de usuarios y grupos
Comprobar que los el usuario y grupo en el archivo “ /etc/apache2/apache.conf “, dispone con estas líneas. 

Comprobar que las variables de entorno apuntan al usuario www-data

Mediante “ ps fauxu |grep apache2 “ se puede comprobar que el usuario www-data es quien corre los procesos de apache2

### Ocultación de versiones
Ocultar la versión puede ayudar a no dar información relativa de posibles vulnerabilidades a nadie, y al mismo tiempo, minimizar opciones de éxito en el ataque.

Antes de realizar cualquier modificación, cualquier persona puede ver que aplicación y versión se usa en la página web.

Por lo tanto, realiza “ sudo nano conf-enabled/security.conf “ para editar el archivo

Modificar para que quede así:
ServerTokens ProductOnly
ServerSignature Off

Reiniciamos el servicio de apache para aplicar la configuración

Ahora solo aparece Apache en el parámetro Server

### Exposición mínima de módulos.
En apache los módulos pueden estar compilados estáticamente o cargados de una forma dinámica.
Un módulo es una extensión que añade funcionalidad a través de la configuración en apache, concretamente, añadiendo directivas propias del módulo.
En la configuración por defecto es habitual encontrar módulos activos que no se usan o no interesan, por lo que es recomendable desactivar los que no están en uso. Esto reducirá la carga y la superficie de exposición de un ataque.

Para ver los módulos disponibles, ejecuta “ apache2ctl -M “, para aplicar los cambios, realiza “ sudo systemctl reload apache2 “.

### Creación de virtualhost con tu nombre y apellido.
Para avanzar trabajo, copiaremos la configuración por defecto de apache ( /etc/apache2/sites-available ), y lo renombraremos con un nombre distintivo para nuestro VirtualHost.
“ sudo cp 000-default.conf   nombre-default.conf “

Editamos el archivo.

Modificamos el archivo para que quede de la siguiente manera:

Creamos el directorio donde estará la base de nuestro VirtualHost (crear el directorio con el mismo nombre asignado en el archivo de configuración anterior).

Asignar permisos al directorio para poder trabajar y editar en él.
“ sudo chmod 755 nombre_directorio “

Ahora mismo podemos crear el archivo principal de nuestra página web. 
Seguimos con crear el archivo index.html y modificamos su contenido para tener algo tal que así (es provisional e puede ser modificado como plazca).

Modificaremos el archivo /etc/hosts para implementar la línea en la IP de localhost (127.0.0.1) el nombre de nuestra página web.

Activaremos la configuración del VirtualHost con “ sudo a2ensite joelbagur-default.conf “

Finalmente, reiniciamos el servicio de apache para implementar la configuración, y poder ver la página desde el navegador.

### Configuración múltiple y de contexto: directiva options
Esta configuración consiste en restringir a los usuarios el modo índice para los usuarios al momento de buscar una carpeta en una página web.

Crearemos un directorio llamado “ privado “. 

Asignamos permisos para poder trabajar con el.

Crea varios archivos para ver que aparecen en el navegador al buscar la pagina_web/privado.

Modificamos los parámetros de nuestro directorio privado (archivo de configuración del Virtual Host), par que nadie pueda ver un índice del contenido del propio directorio, para ello es indispensable asignar “ -Indexes “.,




## 3.Ficheros .htaccess. ¿Para qué sirven?
Los ficheros “.htaccess” permiten personalizar la configuración de directivas y parámetros que se definen en el fichero principal de configuración de Apache. Deben colocarse dentro de un directorio donde se pretende que tenga efecto. Estos ficheros están protegidos desde la directiva del fichero principal, dado un 403 Forbidden en caso de acceder directamente a ellos.

## 4.¿Cómo podemos evitar el hotlinking? Compruébalo.
Inserta una imagen en tu archivo donde se aloja tu página web (localhost). Esta imagen debe estar en el mismo directorio que esta página web, para facilitar el trabajo.

En este momento, si comprobamos la página que realiza hostlinking (la página de Dani está realizando hostlinking a mi imagen), veremos que mi imagen se refleja en su página. 

Para remediar, creamos el archivo .htaccess en el directorio de la página web, en mi caso /var/www/html/joelbagur.com. En el archivo se incluyen las siguientes lineas.

Una vez guardado, actualiza el servicio de apache “ sudo systemctl restart apache “, y al momento de visitar la página que nos realizaba el hostllinking, veremos que nuestra imagen ya no aparece (es interesante borrar la caché, ya que si la página está guardada en ella la imagen nos puede seguir apareciendo)

## 5. Configuración HTTPS mediante OpenSSL. Crea los certificados para que tu virtualHost sea seguro, y obligatoriamente los accesos sean por HTTPS.
El primer paso es instalar OpneSSL.
“sudo apt install openssl “

Con el comando “ sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout  /etc/ssl/private/apache-selfsigned.key -out “, creamos el certificado para nuestra página web.
Al momento de crearlo responde a las preguntas pertinentes, estas respuestas se reflejaran en el certificado y son visibles para los usuarios.

En el fichero de configuración de nuestro virtualhost, añade las dos líneas marcadas, estas cumplirán la función de especificar donde se encuentra el certificado.
También cambia la primera línea del virtual host para que responda al puerto 443 (actualmente 80) para garantizar una conexión segura mediante HTTPS.

Habilita ssl para habilitar el certificado pueda ser visible con “ sudo a2enmod ssl “ y reinicia el servidor apache “ sudo systemctl restart apache2 ”.

Ahora mismo, para acceder a la página se realiza mediante “ https://tupagina “, y al primer momento de acceder nos dirá que no es seguro (realmente es porque nos hemos autocreado el certificado y no es creado por una organización especifica para este proposito).

Finalmente, podemos ver el certificado con la información que rellenamos al crearlo.

## 6. Módulo mod_security. ¿Qué es mod_security?
ModSecurity es un módulo de seguridad para servidores web, como Apache, Nginx y IIS, que actúa como un firewall de aplicaciones web (WAF). Su función principal es proteger las aplicaciones web de ataques como inyecciones SQL, XSS, y otros riesgos al inspeccionar el tráfico HTTP. Utiliza reglas de seguridad para detectar patrones maliciosos, bloquear amenazas en tiempo real, y generar registros detallados para auditorías y monitoreo. Además, es configurable y permite personalizar reglas para adaptarse a necesidades específicas, mejorando así la protección web y la visibilidad del tráfico.

Para instalar mod_security, ejecuta “ sudo apt install libapache2-mod-security2 “

Habilita con “ sudo a2enmod security2 “ 

## 7. Realiza la descarga de Kali Linux y realiza un ataque DoS mediante Metasploit (Slowloris) y comprueba que efectivamente el servidor está inaccesible.
Inicia la máquina virtual con Kali (el usuario y contraseña es Kali). Abre la seccion de aplicaciones y abre metasploit-framework.

Al pedir la contraseña ingresaremos Kali (contraseña por defecto de la maquina que tenemos)

Buscaremos el ataque DoS Slowloris mediante “ search slowloris “.

Para acceder a él ejecutaremos “ use 0 “, ya que es el número identificador para este.
Una vez dentro de él, con el comando “ info 0 “, podemos ver la información que nos proporciona el propio Kali.

Para poder indicar la IP al equipo donde queremos ralizar el ataque, usaremos el comando 
“ set rhost 192.168.1.66 “ y al ejecutar un “ info “, este nos aparece.

Ejecuta con un “ run “ y el ataque empezará.

A recalcar que con este ataque no causa muchos problemas para mi equipo actual, la única diferencia que se aprecia es que la página web tarda más en cargar, pero es bastante leve.

## 8.Clona e instala las reglas recomendadas OWASP. Habilita mod_security
Primeramente, instala git “ sudo apt install git “
Clona el repositorio de OWASP CRS.

Si el directorio no es accesible, asigna permisos para poder entrar en él.

Este es el contenido del directorio al momento de clonar la configuración.

Habilita el módulo mod security (si no se realizo anteriormente)

## 9.Realiza de nuevo el ataque DoS y comprueba que el servidor está accesible.
Si se realiza otro ataque, se puede comprobar que la página está disponible y asimismo esta ya no tiene el problema de carga lenta como anteriormente.


# SPRINT 4




[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)
