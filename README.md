# Práctica 3: Diseño de máquinas virtuales

## Francisco Manuel Sánchez Ramos

Para la realización de esta práctica voy a instalar dos máquinas virtuales haciendo uso de "VirtualBox", software de virtualización para arquitecturas x86/amd64. En cada máquina voy a instalar dos sistemas opeativos distintos y voy a ir modificandolos con distintas configuraciones para el tamaño de memoria así poder compararlos y determinar cuales son los recursos necesários para el correcto funcionamiento de cada una de nuestras máquinas.

El primer sistema operativo que voy a instalar va a ser Debian7.3.0 que podemos descargar desde la [web](http://www.debian.org/index.es.html). El segundo sistema operativo que usaré va a ser Kubuntu13.10 que podemos descargar desde su [web](http://www.kubuntu.org/getkubuntu).

Voy a comparar las maquinas con Apache Benchmark que sirve para hacer pruebas de carga a un servidor apache.

He usado una licencia GPLV3. Esta licencia la he generado al crear el proyecto seleccionando como tipo de licencia "LICENCE GPLV3".

Empezamos instalando VirtualBox de la siguiente forma:

    sudo apt-get install virtualbox

A continuación voy a explicar como he instalado cada máquina virtual para las distíntas configuraciónes. Por cada configuración no voy a instalar nuevamente la máquina sino que una vez instaladas simplemente lo que haŕe será desde virtualbox en la opción "sistema", modificar el tamaño de la memoria de cada máquina cada vez que lo deseemos sin tener que volver a instalarlas desde cero.

Con el fin de evitar que el archivo README.md sea muy extenso dejo estos enlaces correspondientes a dos archivos donde explico como he realizado la instalación de cada una de mis máquinas.

[Instalación de mi máquina virtual Debian](https://github.com/franciscomanuel/Practica3/blob/master/CreacionMaquinaVirtualDebian.md)

[Instalación de mi máquina virtual Kubuntu](https://github.com/franciscomanuel/Practica3/blob/master/CreacionMaquinaVirtualKubuntu.md)

Una vez instaladas, con apache benchmark compararé cada máquina para cinco configuraciones distintas de memoria RAM (383 MB, 512MB, 1024MB, 2048MB y 4096MB) y sacaré mis conclusiones. 

Para poder hacer uso de apache benchmark tenemos que instalar previamente el servidor apache:

    debian --> su apt-get install apache2
    kubuntu --> sudo apt-get install apache2
    
Ahora instalamos apache benchmark:

    debian --> su apt-get install apache2-utils
    kubuntu --> sudo apt-get install apache2-utils
    









