# Práctica 3: Diseño de máquinas virtuales

## Francisco Manuel Sánchez Ramos

Para la realización de esta práctica voy a instalar dos máquinas virtuales haciendo uso de "VirtualBox", software de virtualización para arquitecturas x86/amd64. En cada máquina voy a instalar dos sistemas opeativos distintos con una CPU y voy a ir modificandolos con distintas configuraciones para el tamaño de memoria RAM para así poder compararlos y determinar cuales son los recursos necesários para el correcto funcionamiento de cada una de nuestras máquinas.

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

    Debian --> su
               apt-get install apache2
         
    kubuntu --> sudo apt-get install apache2
    
Ahora instalamos apache benchmark:

    Debian --> su
               apt-get install apache2-utils
           
    kubuntu --> sudo apt-get install apache2-utils
    
Voy a subir mi aplicación usada en las dos prácticas anteriores a localhost en los dos sistemas operativos.
    
Para tenerla en localhost lo que hago es darle permisos al directorio www/:

    sudo chmod 755 /var/www
    
ahora copiamos todos los archivos en /var/www y reiniciamos servidor apache:

    service apache2 restart
    
Ya tenemos la aplicación corriendo en localhost en mis dos sistemas operativos.

![Debian](https://dl.dropbox.com/s/1l04epodzvlg3zc/debianlocalhost.png)

![kubuntu](https://dl.dropbox.com/s/tsuw1wiaxr17yys/localhostk.png)

Voy a ejecutar ab con 100.000 peticiones y 10 usuarios simultaneos sobre "localhost", y voy a comparar los resultados para las distintas configuraciones de las distintas máquinas:

    Sintaxis ab: ab-n [número de conexiones]-c [número de usuarios simultáneos] [url]
    ab -n 100000 -c 10 http://localhost/
    
## Resultados obtenidos

En los siguientes enlaces podemos ver los resultados completos obtenidos para las distintas configuraciones en las máquinas.

[Resultados Debian](https://github.com/franciscomanuel/Practica3/blob/master/ResultadosDebian.md)

[Resultados kubuntu](https://github.com/franciscomanuel/Practica3/blob/master/ResultadosKubuntu.md)

Ahora voy a sacar los resultados que usaré para comparar las configuraciones y realizaré gráficas con dichos resultados:

En todas las configuraciones se han realizado 100.000 peticiones con una concurrencia de 10 usuarios al servidor localhost. El total trasferido ha sido de: 794100000 bytes y el HTML transferido ha sido de: 771700000 bytes


### Resultados kubuntu

                     memoria RAM  Tiempo empleado  Solicitudes por seg  Tº por petición  Velocidad de transferencia
    configuracion1:     384 MB      30.039 s           3329.00            3.004 ms        25816.04 Kbytes/seg
    configuracion2:     512 MB      29.672 s           3370.22            2.967 ms        26135.66 Kbytes/seg
    configuracion3:    1024 MB      28.000 s           3571.46            2.800 ms        27696.23 Kbytes/seg
    configuracion4:    2048 MB      28.268 s           3537.55            2.827 ms        27433.28 Kbytes/seg
    configuracion5:    4096 MB      28.389 s           3522.50            2.839 ms        27316.58 Kbytes/seg

**Gráfica para el tiempo empleado en realizarse el benchmark en cada configuración**

![grafica1](https://dl.dropbox.com/s/pgzy14pgbzr8mqz/grafica1.png)

**Gráfica para el número de solicitudes por segundo para las distintas configuraciones**

![grafica2](https://dl.dropbox.com/s/o6ul0suoq1cm5rs/grafica2.png)

**Gráfica para el tiempo por petición para las distintas configuraciones**

![grafica3](https://dl.dropbox.com/s/y3u5q5yc23tdfrl/grafica3.png)

**Gráfica para la velocidad de transferencia en las distintas configuraciones**

![grafica4](https://dl.dropbox.com/s/dz4vkza8iufb7mg/grafica4.png)

**Conclusión**

Con estas gráficas podemos concluir que a partir de 1024 MB tanto el tiempo empleado, como el número de solucitues por segundo, como el tiempo por petición y la velocidad de transferencia son similares, por lo tanto podemos concluir que una máquina virtual con el sistema operativo kubuntu y una memoria RAM de 1024 MB es suficiente para que esta funcione correctamente.

### Resultados Debian

                     memoria RAM  Tiempo empleado  Solicitudes por seg  Tº por petición  Velocidad de transferencia
    configuracion1:     384 MB       19.324 s           5174,89            1.932 ms           40408.64 Kbytes/s
    configuracion2:     512 MB       18.794 s           5320.80            1.879 ms           41547.97 Kbytes/s  
    configuracion3:    1024 MB       18.521 s           5399.30            1.852 ms           42160.95 Kbytes/s
    configuracion4:    2048 MB       18.735 s           5337.55            1.874 ms           41678.74 Kbytes/s
    configuracion5:    4096 MB       18.985 s           5267.37            1.898 ms           41130.77 Kbytes/s
    
**Gráfica para el tiempo empleado en realizarse el benchmark en cada configuración**

![grafica1_1](https://dl.dropbox.com/s/wnik24m5ihog47n/graficad_1.png)

**Gráfica para el número de solicitudes por segundo para las distintas configuraciones**

![grafica2_2](https://dl.dropbox.com/s/tx9xgb5swusyozj/graficad_2.png)

**Gráfica para el tiempo por petición para las distintas configuraciones**

![grafica3_3](https://dl.dropbox.com/s/qibdr3ycpcjdar7/graficad_3.png)
*
*Gráfica para la velocidad de transferencia en las distintas configuraciones**

![grafica4_4](https://dl.dropbox.com/s/igca83033ukdkju/graficad_4.png)

**Conclusión**

Con estos resultados podemos concluir que con una memoria RAM de 512 MB es suficiente para que funcione correctamente una máquina virtual con Debian, puesto que los resultados obtenidos para este tamaño de RAM son similares a los resultados obtenidos para las demás configuraciones (1024 MB, 2048 MB, 4096 MB).

## Conclusión final

Con estas comparaciones realizadas podemos decir que Debian necesita menos tamaño de RAM que Kubuntu para que funcione correctamente, por lo tanto si yo tuviera que escoger entre los dos sistemas opearativos eligiría Debian sin ninguna duda. Solo tengo una queja con respecto a Debian: he necesitado 4 horas para instalarlo, pero por lo demás he podido comprobar que va un mejor que kubuntu. Por ejemplo: para la configuración de 384 MB de RAM he podido notar que debian iba mas fluido que Kubuntu al navegar por dentro del sistema operativo.





    

    









