![](imagenes/portada.png)

# Instalación de JDK en Ubuntu

Created: November 3, 2021 10:50 AM  
Created By: Yared Martín Pérez  
Github: https://github.com/Yared70/Yared-1DAM/tree/main/Entornos-de-Desarrollo/Practica1-Instalacionjavajdk  
Tema: Tema 1: Instalación y uso de entornos de desarrollo  
Type: Informe  



### ¿Qué es Java?

Java es un lenguaje de programación y una plataforma informática. Hay muchas aplicaciones y sitios web que no funcionarán, probablemente, a menos que tengan Java instalado, y cada día se crean más. Java es rápido, seguro y fiable


---


![https://www3.gobiernodecanarias.org/medusa/edublog/iespuertodelacruztelesforobravo/wp-content/uploads/sites/408/2021/06/logotipo-fondo-transparente-4.png](https://www3.gobiernodecanarias.org/medusa/edublog/iespuertodelacruztelesforobravo/wp-content/uploads/sites/408/2021/06/logotipo-fondo-transparente-4.png)


---


### Requisitos previos

Antes de instalar Java debemos actualizar el sistema con:

```xml
sudo apt-get update
```

![01.png](imagenes/01.png)



# Pasos



Vamos a realizar la instalación de Java a través de línea de comandos. Para ello vamos a seguir los siguientes pasos:


## Descarga e instalación de Java


Para instalar Java, ejecutamos el siguiente comando:

```bash
sudo apt-get install default-jdk
```

![02.png](imagenes/02.png)

Y comprobamos la versión que se ha instalado con:

```bash
java --version
```

![03.png](imagenes/03.png)


## **¿Cómo instalar una versión específica de Java?**

Existen varias versiones del jdk, y podemos elegir manualmente cuál queremos instalar con el siguiente comando:

```bash
sudo apt install openjdk-X-jdk
```

Cambiando la X por el número de la versión que queremos, en este caso, la 8:

![04.png](imagenes/04.png)

Aún después de instalar jdk-8 si usamos:

```bash
java --version
```

![05.png](imagenes/05.png)

Podemos ver que sigue usando la versión 11, por lo que tenemos que configurar las variables de entorno

## Configuración de las variables de entorno

El siguiente paso consiste en establecer las variables de entorno. Es necesario porque cuando se usa Java, Linux necesita saber dónde está ubicado el programa para ejecutarlo y qué versión de Java usar de forma predeterminada.

### Listar versiones de JDK instaladas

Empezamos mirando que versiones de Java tenemos instaladas con el comando:

```bash
ls /usr/lib/jvm
```

![06.png](imagenes/06.png)

### Actualización de las variables de entorno

Para cambiar la versión lo podemos hacer desde terminal con el comando:

```bash
sudo update-alternatives --config java
```

Donde en este caso elegimos la selección 2 ya que es la correspondiente a la versión 8

![07.png](imagenes/07.png)

Y por ultimo comprobamos la versión de java en uso:

```bash
java --version
```

![08.png](imagenes/08.png)
