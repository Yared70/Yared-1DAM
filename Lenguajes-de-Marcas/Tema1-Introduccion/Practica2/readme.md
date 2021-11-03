![](img/portada.png)

# Práctica2: XML Agenda Telefónica

Created: November 3, 2021 12:18 PM  
Github: https://github.com/Yared70/Yared-1DAM/blob/main/Lenguajes-de-Marcas/Tema1-Introduccion/Practica2/readme.md  
Property: Yared Martín Pérez  
Tema: Tema 1: Introducción al Lenguaje de Marcas  
Type: Informe  

![ies.png](img/ies.png)

---

![](img/tarea.png)

# Práctica 2: XML Agenda Telefónica

Diseñar un documento válido en XML que permita estructurar la información de una agenda de teléfonos, suponer que la información que podemos tener de una persona es su nombre y apellidos, su dirección y sus teléfonos, que pueden ser el teléfono de casa, el móvil y el teléfono del trabajo.

### XML:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<agenda titulo="Agenda de contactos">
	<contacto>
		<nombre>Javier</nombre>
		<apellido1>Perez</apellido1>
		<apellido2>Gonzalez</apellido2>
		<direccion>
			<calle>maritima</calle>
			<numero>5</numero>
			<piso>1A</piso>
			<localidad>Sta cruz de tenerife</localidad>
			<provincia>Sta cruz de tenerife</provincia>
		</direccion>
		<telefonos>
			<casa>922454745</casa>
			<movil>645645346</movil>
			<trabajo>606439346</trabajo>
		</telefonos>
	</contacto>

	<contacto>
		<nombre>Tanausu</nombre>
		<apellido1>Negrin</apellido1>
		<apellido2>Gonzalez</apellido2>
		<direccion>
			<Calle>acoran</Calle>
			<numero>7</numero>
			<piso>2B</piso>
			<localidad>Cruz Santa</localidad>
			<provincia>Sta cruz de Tenerife</provincia>
		</direccion>
		<telefonos>
			<casa>922786534</casa>
			<movil>685923786</movil>
			<trabajo>609574382</trabajo>
		</telefonos>
	</contacto>
</agenda>
```
