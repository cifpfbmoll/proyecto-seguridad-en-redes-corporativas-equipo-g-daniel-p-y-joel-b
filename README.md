# SPRINT 1
## Instalación de la máquina virtual

Procedimiento de instalación de la máquina virtual Ubuntu Vr22, ya que la versión 24 nos daba demasiados problemas. He omitido los pasos de configuración desde virtual box, como durante el proceso de configuración de inicio de Ubuntu recién instalado, todo está predefinido como estándar, le dejo aquí unas pequeñas capturas de mi máquina ya instalada.

## Auditoría e implementación del Cis_leve2

A continuación nos disponemos a leer  la documentación, el artículo del CIS, resulto interesante pero un poco apabullante la cantidad de terminología. 
Nos disponemos a leer el manual de la guía de seguridad de Ubuntu.

### 1º Paso
Leemos la guía, entendemos los conceptos básicos de seguridad, como podemos implementarlos  y la necesidad de utilizar el cliente pro

### 2º Paso
La instalación del Ubuntu Pro y upgradear nuestra cuenta.

### 3º Paso
Verificamos que si se nos has actualizado al PRO.
Podemos ver que no estamos habilitados, por eso utilizamos la siguiente comanda para revertir esto.Nos registramos en Ubuntu y actualizamos  a la versión pro desde la página web.

### 4º Paso
Habilitamos la guía de seguridad de Ubuntu.

### 5º Paso
Procedemos a auditar nuestro equipo con el Ubuntu pro activado. Esto nos genera un HTML y un XML, que nos  muestra el nivel de seguridad, donde si cogemos el HTML nos abre una página donde podemos ver que somos muy vulnerables según la auditoría, ya que nuestros defensas son muy bajas o directamente por qué no tenemos los protocolos de seguridad bien implementados.

### 6º Paso
Desactivamos el cortafuegos por medio de la terminal, pero más adelante los haremos por medio de un tailor XML, pero eso será mas adelante.

### 7º Paso
Generamos el archivo tailor con la siguiente comanda.En este punto cambiamos algunos valores del archivo a false para poder implementarlos de forma exitosa , sin que nuestra interfaz gráfica sufra, y cumpliendo todos los puntos demandados , como  deshabilitar los cortafuegos también en este xml. Con el archivo ya modificado, procedemos a implementarlo con el siguiente comando

# Asegura las configuraciones globales.

## Configuración del arranque GRUB.

No sé a qué se refiere con la configuración del arranque GRUB, no sé si quería que se habilitara desde él inició y que nos salga la pantalla GNU GRUB, lo que yo hice fue lo siguiente

## Establecer una contraseña de arranque.

En este apartado, lo que hice fue seguir la guía del video. Entendía el motivo de esta , ya que es establecer una contraseña de arranque con una ya codificada.

## Establecer permisos fichero de configuración de arranque

Esto fue relativamente sencillo, solo fue poner un sudo nano init-pwd, en la ruta correspondiente, claro está,  luego poner la contraseña encriptada más una estructura indicada en el video.

## Obligar al uso de contraseña en el modo “single user”

Aquí establecí, una nueva contraseña, claramente más complicada que la anterior que tenía. Esto de las contraseñas y el grado de seguridad que nos pide ,creo que es gracias ha haber implantado los protocolos de seguridad.



# Configuración  de usuarios y grupos

Configuración de usuarios y grupos. Crea un usuario administrador con la inicial de tu nombre y apellido, por ejemplo, en mi caso “rgion”, y añade este al grupo sudoers.

Como le comente, cree el usuario, puedo entrar con el , pero no tome las capturas pertinentes, como lo de meterle en el grupo de sudos, pero de esta manera te puedo enseñar , que ambos usuarios, a partir de la codificación, pertenecen al grupo de Sudores.

En la siguiente captura, le puedo demostrar que puedo iniciar sesión con este usuario,

# Normas sobre las actualizaciones de software.

En este apartado veremos como podemos limitar las actualizaciones del software en la máquina virtual, solo permitiendo los paquetes certificados como seguros por los proveedores centrales y que cumplan las normas.  Para ello con el root, nos disponemos a viajar hasta la ruta que tenga el documento sources.list, esto contiene enlaces que hacen posible la actualización del sistema.

Dentro de este documento podemos encontrar muchos enlaces, unos son restrictivos, otros son más permisivos y otros directamente son enlaces de paquetes de dudosa procedencia. Lo que haremos será deshabilitar todos menos los restrictivos.

# Auditoria Final

Después de haber completado cada una de las tareas pedidas en este proyecto, con la ayuda del manual y los videos de seguridad, finalmente podemos hacer otra prueba de auditoria para poder comprobar el nivel de seguridad

# Volvemos a auditar

Como puede ver, ha subido significativamente nuestro valor de seguridad en nuestra máquina virtual, de manera que hemos realizado la implementación de los cis_level2 de manera exitosa, claramente , todavía se puede mejorar, aunque sea un pequeño margen, pero sí se puede mejorar. 
Esta auditoria lo hice después de implementar el cis_level2, sin establecer protocolo grub ni restricción de actualizaciones en el software.

Y esta es la auditoria que he realizado al final del todo, con todos los demás puntos aplicados, no llego a entender por qué me ha disminuido el nivel de seguridad si técnicamente los demás puntos daban más seguridad al sistema, es probable que haya cometido un error de configuración que ha hecho que disminuyera el nivel de seguridad. 

# Conclusiones Finales

El proyecto , en gran medida, ha sido interesante, además de informativo, no tenía idea de la vulnerabilidad que pueden sufrir nuestro equipo, sobre todo Ubuntu.

La parte más pesada ha sido leer los artículos, porque hay conceptos , que todavía no termine de comprender , pero sí otros que me ayudaron entender un poco más la importancia de esta práctica.

El sistema Ubuntu, nos da unas herramientas de seguridad muy buenas, me sorprendió gratamente todas las medidas posibles que se pueden implementar para un solo equipo, también la protección de los usuarios.

También ha habido partes negativas, muchas veces no tenía ni idea de como proseguir con algunos pasos, por suerte tenía a compañeros que me ayudaron en todo este proceso, también ayudo tener instantáneas de la máquina, ya que a la hora de aplicar el taylor, si no tocabas los valores correspondientes a determinadas líneas, a la hora de ejecutarla, podías borrar tu interfaz gráfica, o directamente cargarte tu máquina virtual.

Me gustaría haber hecho, la práctica, con más capturas de pantalla y más explicaciones, pero he dado tantas vueltas, que me ha sido imposible escribir y poner todo lo que quería, por todas las vueltas que daba. En la próxima práctica intentaré ser más organizado a la hora de documentarlo, 




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

# SPRINT 6
## Instalación y Configuración de pfSense
En esta ocasión se nos solicita que se nos añada tres tarjetas de red a la máquina virtual de Pfsense, por lo cual nos disponemos a añadirlas



Como puede ver más abajo , ya con la máquina virtual completamente instalada (también se puede bajar una imagen ya configurada para saltarse el proceso de instalación y configuración). Hemos configurado el dhcp  en la WAN

### Wan (adaptador puente)
Desde un equipo externo , podemos entrar a pfSense a través de la ip de la WAN

Usuario: admin / Contraseña: pfsense

### Lan DMZ (Red interna 10.0.3.0/24) 
Este paso es relativamente sencillo , en este apartado tendremos que configurar manualmente la IP, y otros parámetros.


Como puedes ver, la he liado con la ip, solo he tenido que utilizar la opción 2  y volver a reasignarle la IP como toca, recordar, que este no tiene opción de DHCP, ya que este va orientado al servidor

### Lan Empleados (Red interna 10.0.2.0/24).
Como pudo ver en las anteriores imágenes,  solo nos salía dos tarjetas de red, por lo cual tendremos que habilitar el tercer puerto siguiendo las siguientes opciones
Primero le damos a la opción 1

Luego darle luego a no a habilitar VLAN

En la siguiente imagen se puede ver como he configurado esta parte

Después de estos cambios, necesitamos asignarle la red estática que le corresponde, ponemos la opción 2

el resto de opciones que saldrán son sencillas de responder, solo tiene que negar todas las que te ofrezcan un DHCP, u opciones de la IPv6.  Solo le permitiremos la opción de dar DCHP a otros.


### Configurar empleados
Configura el equipo del empleado adjudicando a su tarjeta de red Lan Empleados (debes simular que este equipo es un Windows).
Como hemos visto más arriba, puede ser que exista un problema  a la hora de asignar las ip de forma correcta, por lo cual he realizado estos cambios

Bien, utilizamos el Windows, con una configuración de red de LAN empleado. Gracias a las configuraciones realizadas en pfSense, nos dará una ip automática en el rango que le dimos en la configuración. En nuestro caso me dio la 10.0.2.2
Ahora probamos a acceder al pfSense desde la ip 10.0.2.1



Aproveche para cambiarle el nombre a la interface em2 y le puse la de DMZ

### Configuración del DMZ
Configura el servidor adjudicando a su tarjeta de red Lan DMZ, y estableciendo una ip fija al servidor.
Ahora le toca a nuestro servidor, qué será nuestro Ubuntu de seguridad. Le metemos una ip de forma manual 

Como en este apartado DNZ no tiene reglas que bloquen o permitan  el acceso a la red, directamente no podremos conectarnos a esta. Por lo cual copiaremos esta regla de la LAN empleados  para poder  conectarnos a internet 

Esta captura, se puede ver el apartado DMZ, en el cual le he añadido una regla más (que se verá más adelante), en principio, solo tendría que estar la primera

Con esto ya establecido podemos establecer la conexión con pfSense

## Preguntas antes de configurar las reglas
Antes de comenzar a configurar reglas, haremos una serie de comprobaciones, con el objetivo de conocer la situación actual, por tanto, responde a las siguientes preguntas, justificando la respuesta:
¿El servidor web y SSH es accesible desde el exterior?
En principio no , ya que el servidor  no cuenta con estas configuraciones habilitadas para estos servicios. Una medida de seguridad 
¿El servidor tiene acceso a internet?
Técnicamente, no  , ya que no se pudo realizar un ping a Google, no se puedo  establecer una comunicación. No se puede acceder a internet
¿El equipo de los empleados tiene internet?
Técnicamente, sí que dispone de internet, en mi caso si que se ha generado  las reglas que permitían él acceso de a la conexión a internet. 
¿El servidor web es alcanzable desde el equipo de los empleados? ¿Y viceversa?  
Sí que se pueden ver, se hacen ping y de hecho , desde el equipo de empleados, si se pone la IP del server se puede acceder al pfSense
## Configuración de las Reglas
Configurar las reglas necesarias para:
### El servidor tenga acceso a internet.
Lo primero que tenemos que hacer es ir  a  Firewall->Rules, Después meternos en el DMZ que es nuestro server Ubuntu, añadimos la siguiente regla:
En este caso es una acción pasiva, es no bloque ni deniega, el protocolo es el IPV4 Any, el source será el DMZ subnets y en la destination le he puesto a todos (any), también le he puesto una pequeña descripción .


Con esto ya tendremos acceso a internet en el servidor DMZ:

## Los empleados tengan acceso a internet.
En este caso , por suerte mía en el firewall->rules, en el apartado LAN empleado , ya dispone de las reglas para conectarse a internet, las configuraciones son iguales al anterior ejemplo


### El servidor web sea accesible únicamente por el puerto 443 y redirija el tráfico del 80 al 443.
Para poder hacer este apartado tuve que cambiar de red.  Por lo cual, generar otro dhcp en mi pfSense

Y desde la interfaz gráfica de pfsense en Interfaces->WAN, procedemos ha des clicar estas dos opciones

Esto es un protocolo que se ha de implementar en la NAT


Desde mi ordenador anfitrión, abriendo el buscador, probamos entrar en el server, aquí la prueba.

El servidor SSH sea accesible únicamente desde el puerto que elegiste en el Sprint de Hardening SSH. 
Esto es como el anterior ejercicio, nos dirigimos a Interface-> NAT, nos disponemos a clear una regla


Bueno, con esta regla ya configurada, lo ponemos a prueba.

### Una regla que no permita el tráfico directo entre el servidor y los empleados, y al revés. 
Esto lo he realizado a traves de unas reglas en Firewall->Rules, hemos de  implantar las siguientes reglas
En LAN

Como se puede ver esta regla lo que hace es bloquear la LAN a Dnz por el protocolo IPV4 y6 any

En la DMZ
En este caso en ves de poner en el campo Protocol Any, le podemos poner ICMP.

Es lo mismo que hicimos en la LAN pero esta vez de forma inversa en DMZ
Ahora  probamos las conexiones
LAM

DMZ

### Regla anti ciberataques
Imagina que hemos sufrido un ciberataque en el servidor, y queremos bloquear el tráfico para que no nos exfiltren más información. Crea una regla que bloquee el tráfico. Comprueba que funciona. Deshabilita (no la borres), y comprueba que has recuperado el tráfico. La idea es tener una regla preparada y comprobada por si sucede el incidente, de manera que si sucede solo hay que habilitarla. 
Esta regla se tiene que implementar en la DMZ , nuestro server ubuntu.

Básicamente, lo que hace es bloquear el acceso al server ubuntu, desde cualquier sitio
Ahora lo que procede es probarlo en ubuntu server

Ahora procederemos deshabilitar esta regla

Como puede mirar esto deshabilita la regla

### Bloquear una ip en concreto
Se han detectado un ciberataque desde una ip concreta (de un compañero, por ejemplo). Comprueba que tu compañero tiene acceso al servidor web, y que es capaz de hacer un ataque DOS. Una vez configurada la regla que bloquea el tráfico, comprueba que efectivamente es así y no puede acceder al servidor web.
Bien, esta vez se ha de configurar una regla para el WAM, es decir, directamente que afecte al pfSense, el que da salida al exterior

Como puede ver , he bloqueado el ping del ordenador que se quiere conectar, por lo cual, cuando se aplica la regla, este ordenador no podrá acceder a la pagina.

Aquí la prueba

### Regla propia (bloquear una página web)
Con la situación actual, podríamos decir que tenemos nuestra infraestructura segura y funcional. Piensa en alguna regla que te gustaría añadir a la configuración actual y comprueba su funcionamiento.
Bueno, yo considero que con las reglas actuales estaría bien como base, pero creo yo que podríamos implementar una regla para que, en el caso de que en el server DMZ, no pudiera acceder a la página softonic. 
Lo primero que haríamos sería ir al firewall->Aliases, y crear un nuevo alias al softonic



## Conclusión
En este apartado se explicará un poco sobre mi experiencia durante esta actividad, por suerte, el pfSense no se me genero ningún tipo de problema en su instalación y configuración, lo que sí que tengo que decir es que el programa es un poco complicado de instalar y configurar, seguramente sea por el primer contacto, pero se dé muchos compañeros que se nos dificultó este proceso.
Que puedo decir de pfSense, realmente es una herramienta muy útil como cortafuegos, me pareció realmente increíble como este servidor puede hacer tantas cosas, como a la hora de dar conexión a internet, denegar accesos externos, evitar que maquina dentro de la red interna no se puedan ver, etc.
Es verdad que a la hora de configurar algunas reglas, se nos complicó por cosas que no estaban explicadas o cosas como que se tenía que desactivar ciertos campos para poder ejecutar la regla de forma correcta, por lo resto, es un programa relativamente fácil de utilizar.
Una cosa sí que es cierta, algunos compañeros que disponemos de la misma configuración, hemos tenido resultados completamente diferentes, un ejemplo es en el apartado de darle conexión a internet a un equipo DMZ, pues algunos compañeros, a pesar de tener la misma regla que yo, no consiguieron el objetivo.


# SPRINT 4




[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/A04QAW6X)
