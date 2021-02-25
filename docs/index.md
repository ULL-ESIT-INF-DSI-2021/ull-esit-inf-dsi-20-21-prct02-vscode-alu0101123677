# Informe Práctica 2. Instalación y configuración de Visual Studio Code
## 1. Introducción

Informe de la segunda práctica de la asignatura de **Desarrollo de Sistemas Informáticos**. En la práctica propuesta se ha realizado la instalación y configuración inicial del entorno de desarrollo **Visual Studio Code**, realizar pruebas con las sesiones colaborativas con **Visual Studio Live Share** y realizar el primer proyecto en **TypeScript**.

## 2. Objetivos

El objetivo principal de la práctica es la preparación del entorno de desarrollo **Visual Studio Code**. Para conseguirlo se tienen los siguientes objetivos:

* Instalación de **Visual Studio Code** y configuración para **conexión remota**.
* Aprender a utilizar sesiones colaborativas con **Visual Studio Live Share**.
* Realizar un proyecto en **TypeScript**.

## 3. Desarrollo

### 3.1 Tareas previas

Para el desarrollo de la práctica cómo tal primero hay que hacer unas prepariones previas, lo primeros será aceptar la asignación de **GitHub Classroom** asociada a la práctica 2 para conseguir el repositorio correspondiente.

Lo siguiente será realizar la **Github Page** asociada al repositorio de la práctica 2.

### 3.2 Instalación y funcionalidad de VisualStudio Code

En mi caso ya tenía instalado **Visual Studio Code** con anterioridad, pero en el caso de que no se tenga instalado en nuestra máquina local, procedemos a instalarlo con el siguiente comando, siempre que estemos trabajo en una distribución **Linux Debian/Ubuntu**.

```bash
bruno@bruno-X550VX:~$ sudo apt install code
```

![Visual studio code](img/1.%20VIsual%20studio%20code.png)


### 3.3 Configuración de Visual Studio Code para conectarse a una máquina remota por SSH

En este apartado, llevaremos a cabo la configuración necesaria para conectarnos desde **VSCode** a una máquina remota por SSH, en concreto, a nuestra **máquina virtual**.

Al realizar la práctica anterior ya nos hemos asegurado que podemos establecer una **conexión SSH** desde nuestra **máquina local** a nuestra **máquina virtual del IaaS**, lo que debemos hacer ahora es abrir una instancia de **VSCode**, buscar e instalar la extensión de **VSCode** denominada *Remote - SHH*

A continuación, pulsamos la tecla ``F1`` o la combinación de teclas ``Ctrl + Shift + P`` para mostrar la paleta de comandos, tecleamos ``ssh`` y pulse sobre ``Connect to Host...``. Al haber completado la configuración de la primera práctica, entre las opciones del menú desplegables aparecerá el nombre de nuestra máquina virtual. Al establecer la conexión ``ssh`` con la máquina virtual se iniciara una nueva instancia de **VSCode**. Para comprobar que se ha conectado a la máquina virtual de manera remota, abrimos una terminal desde el propio VSCode, pulsando la combinación de teclas ``Ctrl + Shift +``. En la terminal tecleamos el siguiente comando:

```bash
[~()]$hostname
iaas-dsi13
[~()]$
```

Podemos observar que en la esquina inferior izquierda de la interfaz, en un área de color verde, podremos ver el nombre de la máquina virtual a la que acaba de conectarse.

![Conexión remota ssh](img/2.%20Conexi%C3%B3n%20remota%20ssh.png)

### 3.4 Sesiones colaborativas con Visual Studio Live Share

**Visual Studio Live Share** permite colaborar en las tareas de desarrollo en tiempo real. Primero buscamos e instalamos la extensión denominada *Live Share Extension Pack*, así como las extensiones recomendadas.

En un principio, dependiendo de en que instancia de **Visual Studio Code** nos encontremos, si en la ventana de la máquina local o en la máquina virtual, instalaremos las extensiones en una u otra. Podemos elegir si instalar las extensiones en la local, en la virtual o en ambas máquinas.

Una vez instaladas todas las extensiones necesarias podemos iniciar una sesión colaborativa. Podemos compartir el enlace generado con otros usuarios y probar las diferentes funcionalidades cómo los chats, las llamadas o la pizarra.


![live share](img/3%20live%20share.png)


### 3.5 Primer proyecto en TypeScript: "Hola Mundo"

Para empezar nos instalaremos las siguientes extensiones en nuestra máquina virtual

* Vim. Versión mejorada del editor de texto Vi.
* ESLint. Permite realizar comprobaciones de estilo sobre ficheros que incluyan código fuente en **JavaScript** y **TypeScript**.

Continuamos con la instalación del compilador de TypeScript. Para ello usaremos npm:

```bash
[~()]$npm install --global typescript
...
[~()]$tsc --version
Version 4.1.5
```

![instalar typescript](img/4.%20instalar%20typescript.png)

A continuación, ejecutamos los siguientes comandos:

```bash
[~()]$pwd
/home/usuario
[~()]$mkdir hello-world
[~()]$cd hello-world/
[~/hello-world()]$npm init --yes
Wrote to /home/usuario/hello-world/package.json:

{
  "name": "hello-world",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

[~/hello-world()]$ls -lrtha
total 12K
drwxr-xr-x 26 usuario usuario 4,0K feb  9 18:46 ..
drwxrwxr-x  2 usuario usuario 4,0K feb  9 18:48 .
-rw-rw-r--  1 usuario usuario  225 feb  9 18:48 package.json
[~/hello-world()]$
```

El comando ``npm init --yes`` nos permite crear un fichero denominado ``package.json``, el cual se utiliza, entre otras cosas, para establecer las dependencias de desarrollo y ejecución del proyecto a modo de paquetes de los que depende el proyecto actual. Puede observar el contenido de dicho fichero como parte de la salida del comando ``npm init``.

Ahora abrimos el directorio ``~/hello-world`` en el explorador de **Visual Studio Code**. Para ello, vamos al menú ``File`` y hacemos clic en la opción ``Open Folder....`` A continuación, seleccionamos hello-world en el menú desplegable. Se abrirá una instancia de **VSCode** y en el explorador podremos ver el contenido de dicho directorio.

También podemos añadir el directorio a un espacio de trabajo, *workspace*. Para ello, vamos al menú ``File`` y seleccione la opción ``Add Folder to Workspace...``. Seleccionamos ``hello-world`` en el menú desplegable. Si no teniamos un espacio de trabajo creado previamente, se creará uno nuevo y se añadirá el directorio al mismo. Guardamos el espacio de trabajo seleccionando la opción ``Save Workspace As...`` del menú ``File``, escribimos un nombre de fichero y pulsamos el botón ``OK``.

![workspace](img/5.%20workspace.png)

Continuamos creando un fichero en el directorio ``hello-world`` denominado ``tsconfig.json``. Podemos hacerlo haciendo uso de la terminal de **VSCode** o de su explorador. En dicho fichero se especifican las opciones del compilador de **TypeScript**. Incluya las siguientes líneas en dicho fichero:

```bash
[~()]$[~/hello-world()]$touch tsconfig.json
```

En dicho fichero se especifican las opciones del compilador de **TypeScript**. Incluimos las siguientes líneas en dicho fichero:

```bash
{
  "compilerOptions": {
    "target": "ES2018",
    "outDir": "./dist",
    "rootDir": "./src",
    "module": "CommonJS"
  }
}
```
![tsconfig](img/6.%20tsconfig.png)

Estas opciones de configuración le indican al compilador de TypeScript que, en primer lugar, queremos generar código compatible con uno de los últimos estándares de JavaScript. En segundo lugar, que el código JavaScript producto de la compilación se almacenará en un directorio ``dist``. En tercer lugar, especificamos que el código fuente escrito en TypeScript se encuentra en el directorio ``src``. Por último, se indica un estándar para cargar código desde ficheros independientes.

Ahora, añadimos un fichero con código **TypeScript**. Ejecutamos los siguientes comandos en la terminal de **VSCode**

```bash
[~/hello-world()]$pwd
/home/usuario/hello-world
[~/hello-world()]$mkdir src
[~/hello-world()]$cd src
[~/hello-world/src()]$touch index.ts
[~/hello-world/src()]$ls
index.ts
```

## 4. Conclusiones

En conclusión, me parece que este tipo de prácticas introductorias son muy importantes debido a qué si no se ha utilizado entornos de desarrollo como **Visual Studio Code**, son herramientas útiles en el día a día, aportando facilidades en cuanto al trabajo en **conexión por remoto** o en la **colaboración para realizar trabajos en conjunto**.

## 5. Bibliografía

**[Guión Práctica 2](https://ull-esit-inf-dsi-2021.github.io/prct02-vscode/):** Guión de la práctica 2 de la asignatura de Desarrollo de Sistemas Informáticos.

**[Introducción a Markdown](https://guides.github.com/features/mastering-markdown/):** Guía sobre la utilización de Markdown.

**[GitHub Pages](https://docs.github.com/en/github/working-with-github-pages):** Guía para la creación y utilización de GitHub Pages.

**[Web de Jekyll](https://jekyllrb.com):** Sitio Web de Jekyll.

**[What is Visual Studio Live Share](https://docs.microsoft.com/en-us/visualstudio/liveshare/):** Documentación de Visual Studio Live Share.

