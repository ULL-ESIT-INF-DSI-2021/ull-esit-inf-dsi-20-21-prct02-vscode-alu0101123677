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

 
### 3.4 Sesiones colaborativas con Visual Studio Live Share



### 3.5 Primer proyecto en TypeScript: "Hola Mundo"

## 4. Conclusiones

En conclusión, me parece que este tipo de prácticas introductorias son muy importantes debido a qué si no se ha utilizado entornos de desarrollo como **Visual Studio Code**, son herramientas útiles en el día a día, aportando facilidades en cuanto al trabajo en **conexión por remoto** o en la **colaboración para realizar trabajos en conjunto**.

## 5. Bibliografía

**[Guión Práctica 2](https://ull-esit-inf-dsi-2021.github.io/prct02-vscode/):** Guión de la práctica 2 de la asignatura de Desarrollo de Sistemas Informáticos.

**[Introducción a Markdown](https://guides.github.com/features/mastering-markdown/):** Guía sobre la utilización de Markdown.

**[GitHub Pages](https://docs.github.com/en/github/working-with-github-pages):** Guía para la creación y utilización de GitHub Pages.

**[Web de Jekyll](https://jekyllrb.com):** Sitio Web de Jekyll.

**[What is Visual Studio Live Share](https://docs.microsoft.com/en-us/visualstudio/liveshare/):** Documentación de Visual Studio Live Share.

