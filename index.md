# Informe Práctica 2: Instalación y configuración de Visual Studio Code

# Introducción

En la segunda práctica de ***Desarrollo de Sistemas Informáticos*** vamos a descargar, instalar y configurar el entorno de desarrollo ***Visual Studio Code***. Este editor de código ligero, como Microsoft lo define, lo usaremos a lo largo del curso para trabajar en esta asignatura.

# Tareas previas
 
Vamos a tener en cuenta que debemos tener hecha unas tareas previas, como es en mi caso, para poder llevar a cabo esta ***práctica 2***. Las tareas son las siguientes:

* Aceptar la asignación de ***Github Classroom***.
* Tener conocimientos previos sobre ***Markdown***, ***Github Pages*** y ***Jekyll***.

# Objetivo

El objetivo principal es instalar y familiarizarnos con el entorno de ***Visual Studio Code***.

# Visual Studio Code

## Instalación

En mi caso, ya tenía instalado el ***VSCode*** debido a que lo he usado en otras asignaturas anteriores en la carrera, sin embargo vamos a explicar como instalar las funcionalidades requeridas.

Para instalar VSCode en Linux Ubuntu/ Debian mediante la terminal, podemos usar dos tipos de comandos sujeridos por el profesor:

´´´bash
[~()]$:~$ sudo apt install code
´´´´

´´´bash
[~()]$:~$ sudo snap install code --classic
´´´

En el caso de Windows, puedes acceder al siguiente enlace para descargar.
[Descargar VSCode para Windows](https://code.visualstudio.com/)

## Configuración VSCode para conectarse por SSH

Vamos a configurar ***VSCode*** para poder conectarnos desde ***SSH*** a una máquina remota, en nuestro caso a la ***máquina virtual del IaaS***.

Para llevar a cabo este apartado es necesario tener completada la ***"Práctica 1: Configuración de máquina virtual en el IaaS"***. En mi caso, ya había realizado todos los pasos. Sin embargo el link sobre la práctica 1 es el siguiente:
[Práctica 1 DSI](https://ull-esit-inf-dsi-2021.github.io/prct01-iaas/)

Luego, es necesario descargar la extensión para poder conectar por SSH desde tu VSCode a tu máquina remota. Para ello, tenemos que hacer click en la parte izquierda en ***"Extensiones"*** o con el comando ***"Ctrl+Shift+X"***, una vez hecho esto, en el buscador escribimos ***"Remote- SSH"*** e instalamos el paquete. En el siguiente enlace podrás consultar con más detenimiento como funcionan las extensiones en VSCode.
[Extensiones VSCode](https://code.visualstudio.com/docs/editor/extension-gallery)

Como nos indica el profesor, Pulsando ***F1*** ó ***Ctrl + Shift + P***, abriremos un desplegable que muestra una serie de comandos. Vamos a escribir ***"Remote SSH - Connect to host"*** y haremos click en el nombre de nuestra respectiva máquina virtual, luego se abrirá otra ventana donde se iniciará la conexión SSH con nuestra máquina remota.

Sin embargo hay otra manera de conectarse, en la siguiente imagen podemos ver que en la esquina inferior izquierda hay dos simbolos ***"<>"*** con unn fondo verde. Al hacer click nos abrirá el desplegable dicho anteriormente pero solamente con los comandos relacionados con la extension de SSH descargada previamente. 
![Image](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/Captura.PNG)

Para comprobar que estamos conectados a la máquina virtual, abrimos una terminal mediante el comando ***"Ctrl + Shift + ñ"***, en el caso de Windows, y escribiremos el siguiente comando para ver el nombre del host de la máquina virtual a la que está conectada.

´´´bash
[~()]$hostname
´´´

## Visual Studio Live Share

Visual Studio Live Share es una herramienta que nos permite trabajar de manera colaborativa en tiempo real con otros usuarios en la máquina actual en la que estés conectado, sea la remota o la local. Se puede descargar igual que la extension de SSH pero escribiendo en el buscador ***Visual Studio Live Share*** o mediante el siguiente enlace.
[Live Share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack)

Esta herramienta es interesante para poder trabajar en grupo ya sea en una práctica o en un entorno laboral para que a las personas relacionadas le sea más fácil compartir instantaneamente el proyecto actual, hacer llamadas de voz, enviar aplicaciones web de localhost, etc.

En el siguiente enlace tendrá información más detallada al respecto
[Información Live Share](https://docs.microsoft.com/en-us/visualstudio/liveshare/)

## Proyecto "Hola Mundo" en Typescript

Vamos a proceder a instalar las siguientes extensiones en la máquina virtual del Iaas para realizar este proyecto:

* ***Vim***, es una extensión recomendada por el profesor si estás familiarizado con el editor Vim (***OPCIONAL***).
* ***ESLint***, es una extensión que nos permite hacer comprobaciones de estilo sobre ficheros del tipo JavaScript y TypeScript (***OBLIGATORIO***)

Abriremos una terminal en el VSCode y seguiremos los siguientes pasos.

Para instalar el compilador de TypeScript, deberemos usar el comando ***npm install --global typescript***, como se indica en la imagen siguiente.

![Image1](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/1.PNG)

Después, usaremos los siguientes comandos:
* pwd: para saber el directorio actual en el que nos encontramos.
* mkdir: para crear un nuevo directorio.
* cd: para movernos de un directorio a otro.
* npm init --yes: Es un comando que nos va a permitir crear un fichero llamado ***package.json***, ***"el cual se utiliza, entre otras cosas, para establecer las dependencias de desarrollo y ejecución del proyecto a modo de paquetes de los que depende el proyecto actual"***, como lo explicó el profesor Eduardo Segredo en el guión de la práctica 2.
* ls -lrtha: para listar un determinado archivo en el directorio.

Se puede apreciar en la siguiente imagen la utilización de los mismos.

![Image2](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/2.PNG)

Una vez hecho esto, vamos a la esquina superior derecha de la pantalla, hacemos click en ***File*** y en el desplegable, elegiremos ***Open Folder***. Seleccionamos ***hello-word*** y se nos abrirá otra ventana donde podremos ver ese directorio. Luego, vamos a añadir el directorio ***hello-word*** a un ***workspace***. Para ello, en el mismo menú ***file*** que ultilizamos antes, buscamos la opción ***Add folder to workspace...***,seleccionamos hello-word y lo guardamos haciendo click en ***Save workspace as...***

Procedemos a crear un fichero en el directorio actual (hello-word) mediante el comando ***touch***, llamado ***tsconfig.json*** y mediante el comando ***cat*** escribiremos las siguientes líneas de código:

´´´bash
[~/hello-world()]$cat tsconfig.json 
{
  "compilerOptions": {
    "target": "ES2018",
    "outDir": "./dist",
    "rootDir": "./src",
    "module": "CommonJS"
  }
}
´´´

Donde en orden indicamos al compilador que queremos generar código compatible con los estándares de JavaScript, el código producido se almacenará en el directorio ***./dist***, que el código fuente TypeScript se encuentra en el directorio ***./src*** e indicamos un stándar para cargar códigos desde ficheros independientes. Como podemos ver en la siguiente imagen.

![Image3](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/3.PNG)


Crearemos otro fichero en el mismo directorio ***hello-word*** de la siguiente manera:

![Image4](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/4.PNG)

Donde podemos apreciar como en el directorio actual, creamos un directorio llamado ***src*** y dentro de dicho directorio creamos un fichero llamado ***index.ts***, en el cual escribiremos el siguiente código de TypeScript.

´´´index.ts
let myString: string = "Hola Mundo";
console.log(myString);
´´´

Una vez guardado el contenido del fichero, vamos a proceder a compilarlo mediante el comando ***tsc***, que va a crear un directorio llamado ***dist***, como se puede apreciar en la siguiente imagen.

![Image5](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/5.PNG)

Si miramos el contenido del fichero ***/.src/index.ts*** y lo comparamos con ***./dist/index.js*** podremos apreciar ciertas diferencias en las declaraciones de la variable ***mystring***. Esto ocurre debido a que TypeScript usa ciertas funcionalidades para corregir problemas que surgen con JavaScript.

![Image6](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/6.PNG)

En último lugar, procederemos a ejecutar el programa mediante el comando ***node dist/index.js***, donde nos tiene que imprimir por pantalla ***"Hola Mundo"***

![Image7](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-lucianosekulic/blob/main/7.PNG)

## Conclusiones

Por un lado, en esta práctica 2, en cuanto a VSCode, aunque ya lo había utilizado en otras ocasiones, he aprendido funcionalidades nuevas como el Live Share y a crear un nuevo workspace para poder desarrollar el código requerido.

Por otro lado, ha sido muy productivo el aprendizaje sobre TypeScript, tanto crear los ficheros y escribir código (aunque no haya sido mucho), como compilarlo. Al solo tener conocimientos de c++ me pareció al principio un poco raro manejar este lenguaje, pero una vez ya leída la bibliografía recomendada y llevar a cabo la práctica, me he sentido un poco más seguro.

Sin duda va a ser para mí todo un reto aprender a utilizar un nuevo lenguaje ya que la programación no es mi lado fuerte y he tenido ciertos problemas sobre todo para entender TypeScrip. Sin embargo, leyendo el libro que recomendó el profesor, viendo ciertos vídeos sobre el tema y concluyendo esta práctica con éxito, he podido encaminar los problemas que tuve y superarlos.


## Bibliografía

* [Guión de la práctica 2](https://ull-esit-inf-dsi-2021.github.io/prct02-vscode/)
* [VSCode](https://code.visualstudio.com/)
* [Funcionalidades VSCode alternativa](https://blog.aitana.es/2020/02/11/tips-utilizar-visual-studio-code-vscode/)
* [Comandos básicos Linux](https://www.hostinger.es/tutoriales/linux-comandos)




















