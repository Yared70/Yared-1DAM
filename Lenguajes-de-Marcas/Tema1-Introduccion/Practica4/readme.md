![](img/portada.png)

# Práctica4: XML Sistema de Información

Created: November 3, 2021 12:45 PM  
Github: https://github.com/Yared70/Yared-1DAM/blob/main/Lenguajes-de-Marcas/Tema1-Introduccion/Practica4/readme.md  
Property: Yared Martín Pérez  
Tema: Tema 1: Introducción al Lenguaje de Marcas  
Type: Informe  

![ies.png](img/ies.png)

# Práctica 4: **Sistema de Información**

Diseñar un documento XML válido que permita estructurar la información para permitir su gestión informática de los alumnos de un modulo del ciclo formativo DAW. Aplicarlo al módulo de Lenguajes de Marcas y Sistemas de Gestión de Información sabiendo que tiene asignadas 4 horas semanales y es de carácter obligatorio. El modulo se imparte entre el 15 de septiembre de 2010 y el 30 de junio de 2022. Hay matriculados dos alumnos:

- Ana Fernández Gutiérrez con nif 16965696L teléfono 789654321 email [ana.fdezgtrrez@hotmail.com](mailto:ana.fdezgtrrez@hotmail.com), su dirección es C/ El Percebe, 13 de Santander CP 39302 No hay información sobre las faltas de asistencia o sus notas hasta el momento.
- Pepito Grillo con nif 98765432H teléfono 656566555 email [yhyh@yahoo.com](mailto:yhyh@yahoo.com), su dirección es Avd. El Pez, 5 de Suances CP 39401. Su nota es "apto" y no tiene faltas de asistencia.

## XML:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<modulo nombre="Lenguajes de Marcas y Sistemas de Gestión de Información" horas_semanales="4" caracter="Obligatorio">

	<fecha_inicio dia="15" mes="septiembre" año="2010"/>
	<fecha_fin dia="30" mes="junio" año="2022"/>

	<alumno>
		<nombre>Ana</nombre>
		<apellidos>Fernández Gutiérrez</apellidos>
		<nif>16965696L</nif>
		<telefono>789654321</telefono>
		<email>ana.fdezgtrrez@hotmail.com</email>
		<direccion>
			<calle>El Percebe</calle>
			<numero>13</numero>
			<ciudad>Santander</ciudad>
			<codigo_postal>39302</codigo_postal>
		</direccion>
		<faltas></faltas>
		<notas></notas>
	</alumno>

	<alumno>
		<nombre>Pepito</nombre>
		<apellidos>Grillo</apellidos>
		<nif>98765432H</nif>
		<telefono>656566555</telefono>
		<email>yhyh@yahoo.com</email>
		<direccion>
			<calle>Avenida el Pez</calle>
			<numero>5</numero>
			<ciudad>Suances</ciudad>
			<codigo_postal>39401</codigo_postal>
		</direccion>
		<faltas>0</faltas>
		<notas>Apto</notas>
	</alumno>

</modulo>
```
