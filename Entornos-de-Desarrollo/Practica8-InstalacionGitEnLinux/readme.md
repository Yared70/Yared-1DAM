# Tarea1: Instalación de Git en Linux

Created: November 2, 2021 6:34 PM
Created By: Yared Martín Pérez
Github: https://github.com/Yared70/Yared-1DAM/tree/main/Entornos-de-Desarrollo/Practica6-InstalacionVSCode
Tema: Tema 3: Documentación y Sistemas de control de versiones
Type: Informe

---

### ¿Qué es Git?

Git es un software de control de versiones diseñado por Linus
Torvalds, pensando en la eficiencia, la confiabilidad y compatibilidad
del mantenimiento de versiones de aplicaciones cuando estas tienen un
gran número de archivos de código fuente

---

![https://www3.gobiernodecanarias.org/medusa/edublog/iespuertodelacruztelesforobravo/wp-content/uploads/sites/408/2021/06/logotipo-fondo-transparente-4.png](https://www3.gobiernodecanarias.org/medusa/edublog/iespuertodelacruztelesforobravo/wp-content/uploads/sites/408/2021/06/logotipo-fondo-transparente-4.png)

## Índice

---

---

### Requisitos previos

---

Necesitará un servidor Ubuntu 20.04 con una cuenta de superusuario no root.

Una vez que tenga el servidor y el usuario configurados, estará listo para comenzar.

# Pasos

---

### Instalación de Git con paquetes predeterminados

---

La opción de instalar con paquetes predeterminados es recomendable si quiere activar y ejecutar con Git rápidamente, si prefiere una versión estable ampliamente utilizada o si no busca las funciones más recientes disponibles.

Empezamos comprobando si git está instalado de base

```bash
git --version
```

![01.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/01.png)

Al no tenerlo instalado empezamos actualizando el índice de paquetes con:

```bash
sudo apt update
```

![02.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/02.png)

---

Tras esto instalamos git usando

```bash
sudo apt install git
```

![03.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/03.png)

Y comprobamos que versión se instaló con:

```bash
git --version
```

![04.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/04.png)

### Instalación de Git desde la fuente

Si busca un método más flexible para instalar Git, puede optar por compilar el software desde la fuente, lo cual explicaremos en esta sección. Esto toma más tiempo y no se mantendrá en su administrador de paquetes, pero le permitirá descargar la versión más reciente y le brindará mayor control sobre las opciones que incluya si quiere personalizarlo.

Antes de comenzar, debe instalar el software necesario para Git. Todo se encuentra disponible en los repositorios predeterminados, de modo que podemos actualizar nuestro índice local de paquetes y luego instalar los paquetes pertinentes.

```bash
sudo apt update
sudo apt install libz-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev gettext cmake gcc
```

![05.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/05.png)

Tras haber instalado las dependencias necesarias, cree un directorio
temporal y vaya a él. Aquí es donde descargaremos nuestro tarball de
Git.

```bash
mkdir tmp
cd /tmp
```

![06.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/06.png)

Desde el sitio web del proyecto Git, podemos navegar a la lista de tarball disponible en [https://mirrors.edge.kernel.org/pub/software/scm/git/](https://mirrors.edge.kernel.org/pub/software/scm/git/) y descargar la versión que quiera utilizar.Utilizaremos curl y enviaremos el archivo que descarguemos a git.tar.gz.

```bash
curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.33.1.tar.gz
```

![08.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/08.png)

Descomprimimos el archivo tarball y nos movemos a la carpeta de git:

```bash
tar -zxf git.tar.gz
```

![09.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/09.png)

Ahora, creamos el paquete y lo instalamos escribiendo estos dos comandos:

```bash
make prefix=/usr/local all
sudo make prefix=/usr/local install
```

![10.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/10.png)

![12.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/12.png)

Ahora, sustituimos el proceso de shell para que se utilice la versión de Git que acabamos de instalar:

```bash
exec bash
```

![13.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/13.png)

Y comprobamos la versión de git en uso:

```bash
git --version
```

![14.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/14.png)

### Configuración de Git

Una vez instalado Git debemos configurar Git de modo que los mensajes de confirmación que genere contengan la  información correcta.

Esta configuración se hace con el comando git config. 
Debemos indicar nuestro nombre y nuestra dirección de correo electrónico debido a que Git inserta esta información en cada confirmación que hacemos. Podemos añadir esta información escribiendo lo siguiente:

```bash
git config --global user.name "Your Name"
git config --global user.email "youremail@domain.com"
```

![18.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/18.png)

Comprobamos como ha quedado con:

```bash
git config --list
```

![19.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/19.png)

Esta información se almacena en un archivo de configuración que podemos modificar manualmente en:

```bash
~/.gitconfig
```

![20.png](Tarea1%20Instalacio%CC%81n%20de%20Git%20en%20Linux%20d6299e02c3b143b2b8f5fa8c2b60e831/20.png)