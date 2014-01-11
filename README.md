# Práctica 3: Diseño de máquinas virtuales

## Francisco Manuel Sánchez Ramos

Para la realización de esta práctica voy a instalar dos máquinas virtuales haciendo uso de "VirtualBox", software de virtualización para arquitecturas x86/amd64. En cada máquina voy a instalar dos sistemas opeativos distintos y voy a ir modificandolos con distintas configuraciones para el tamaño de memoria así poder compararlos y determinar cuales son los recursos necesários para el correcto funcionamiento de cada una de nuestras máquinas.

El primer sistema operativo que voy a instalar va a ser Debian7.3.0 que podemos descargar desde la [web](http://www.debian.org/index.es.html). El segundo sistema operativo que usaré va a ser Centos6.5 que podemos descargar desde su [web](http://isoredirect.centos.org/centos/6/isos/x86_64/CentOS-6.5-x86_64-bin-DVD1.iso).

Voy a comparar las maquinas con Apache Benchmark que sirve para hacer pruebas de carga a un servidor apache.

He usado una licencia GPLV3. Esta licencia la he generado al crear el proyecto seleccionando como tipo de licencia "LICENCE GPLV3".

Empezamos instalando VirtualBox de la siguiente forma:

    sudo apt-get install virtualbox

A continuación voy a explicar como he instalado cada máquina virtual para las distíntas configuraciónes. Por cada configuración no voy a instalar nuevamente la máquina sino que una vez instaladas las dos máquinas simplemente lo que haŕe será desde virtualbox en la opción sistema modificar el tamaño de la memoria de cada máquina cada vez que lo deseemos sin tener que volver a instalarlas desde cero.

Debian7.3.0
===========

Lanzamos VirtualBox:

    virtualbox &
    
Una vez abierto virtualbox le damos a crear una nueva máquina virtual.

![v1](https://dl.dropbox.com/s/i4yexop4ow62de4/v1.png)

Elegimos el nombre de nuestra máquina junto con el sistema operativo que deseamos instalar.

![v2](https://dl.dropbox.com/s/cnmn79lcjrxvja2/v2.png)

En la siguiente pantalla se nos pedirá el tamaño de la memoria RAM. Escogeré como primera configuración un tamaño de memoria de 384 MB

![v3](https://dl.dropbox.com/s/63jaelauek2tvcy/v3.png)

La nueva pantalla nos pedirá si deseamos o no crear un nuevo disco duro virtual. Yo le doy a que si.

![v4](https://dl.dropbox.com/s/in4dlzo3d1g72s6/v4.png)

Selecciono como tipo de archivo para la unidad de disco duro QCOW

![v5](https://dl.dropbox.com/s/1n83qayrzqwpcnu/v5.png)

Ahora seleccionamos el tamaño que queramos que tenga nuestra máquina.

![v6](https://dl.dropbox.com/s/642yzuq01cs4814/v6.png)

Pulsamos sobre iniciar, nos pedirá que insertemos la ruta de donde se encuentra nuestra image "iso" y los demás pasos ya todos los conocemos. 

Ya tenemos instalada nuestra primera máquina virtual con el sistema operativo Debian, ahora vamos a sacar los resultados para las distintas configuraciones de esta máquina:






