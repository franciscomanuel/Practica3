# Práctica 3: Diseño de máquinas virtuales

## Francisco Manuel Sánchez Ramos

Para la realización de esta práctica voy a instalar dos máquinas virtuales haciendo uso de "VirtualBox", software de virtualización para arquitecturas x86/amd64. En cada máquina voy a instalar dos sistemas opeativos distintos y voy a ir modificandolos con distintas configuraciones para el tamaño de memoria así poder compararlos y determinar cuales son los recursos necesários para el correcto funcionamiento de cada una de nuestras máquinas.

El primer sistema operativo que voy a instalar va a ser Debian7.3.0 que podemos descargar desde la [web](http://www.debian.org/index.es.html). El segundo sistema operativo que usaré va a ser Centos6.5 que podemos descargar desde su [web](http://isoredirect.centos.org/centos/6/isos/x86_64/CentOS-6.5-x86_64-bin-DVD1.iso).

Voy a comparar las maquinas con Apache Benchmark que sirve para hacer pruebas de carga a un servidor apache.

He usado una licencia GPLV3. Esta licencia la he generado al crear el proyecto seleccionando como tipo de licencia "LICENCE GPLV3".

Empezamos instalando VirtualBox de la siguiente forma:

    sudo apt-get install virtualbox

A continuación voy a explicar como he instalado cada máquina virtual para las distíntas configuraciónes. Por cada configuración no voy a instalar nuevamente la máquina sino que una vez instaladas las dos máquinas simplemente lo que haŕe será desde virtualbox en la opción sistema modificar el tamaño de la memoria de cada máquina cada vez que lo deseemos sin tener que volver a instalarlas desde cero.





