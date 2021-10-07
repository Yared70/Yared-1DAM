![portada.png](imagenes/portada.png)

# Práctica5: XML Seguridad Social

Created: October 7, 2021 1:43 PM  
Github: https://github.com/Yared70/Yared-1DAM/tree/main/Lenguajes-de-Marcas/Tema1-Introduccion/Practica5  
Property: Yared Martín Pérez  
Tema: Tema 1: Introducción al Lenguaje de Marcas  
Type: Informe  

![ies.png](imagenes/ies.png)

# Práctica 5: XML y DTD Seguridad Social

La Seguridad Social necesita un formato de intercambio unificado para distribuir la información personal de los afiliados.

Todo archivo XML contiene un listado de uno o mas afiliados Todo afiliado tiene los siguientes elementos:

- **DNI** o **NIE**
- **Nombre**
- **Apellidos**
- **Situación laboral**: que tiene que ser una y solo una de entre estas posibilidades: en_paro, *en_activo*, *jubilado*, *edad_no_laboral*
- F**echa de nacimiento**: que se desglosa en los elementos obligatorios día, mes y anio.
- **Listado de bajas**: que indica las situaciones de baja laboral del empleado. Dicho listado consta de una repetición de 0 o más bajas:
    - Una baja consta de tres elementos: causa (obligatoria), fecha de inicio (obligatorio) y fecha de final (optativa),
- **Listado de prestaciones cobradas:** consta de 0 o más elementos prestación, donde se indicará la cantidad percibida (obligatorio), la fecha de inicio (obligatorio) y la fecha de final (obligatorio).

### XML:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<!DOCTYPE Lista_Afiliados [
	<!ELEMENT Lista_Afiliados (Afiliado+, DNI, Nombre, Apellidos, Situacion_Laboral, F_Nacimiento, L_Bajas*, L_Prestaciones*)>
		<!ELEMENT Afiliado (#PCDATA)>
		<!ELEMENT DNI (#PCDATA)>
		<!ELEMENT Nombre (#PCDATA)>
		<!ELEMENT Apellidos (#PCDATA)>
		<!ELEMENT Situacion_Laboral (En_Paro | En_Activo | Jubilado | Edad_No_Laboral)>
		<!ELEMENT F_Nacimiento (Dia, Mes, Anio)>
		<!ELEMENT L_Bajas (Causa, Fecha_Inicio_Baja, Fecha_Final_Baja?)>
		<!ELEMENT L_Prestaciones (Cantidad_Percibida, Fecha_Inicio, Fecha_Final)>
]>

<Lista_Afiliados>
	<afiliado>
		<DNI>7694894B</DNI>
		<Nombre>pepe</Nombre>
		<Apellidos>perez</Apellidos>
		<Situacion_Laboral>En_paro</Situacion_Laboral>
		<F_Nacimiento>
			<Dia>15</Dia>
			<Mes>4</Mes>
			<Anio>1998</Anio>
		</F_Nacimiento>
		<L_Bajas>
			<Causa>Accidente</Causa>
			<Fecha_Inicio_Baja>15 abril</Fecha_Inicio_Baja>
			<Fecha_Final_Baja/>
		</L_Bajas>
		<L_Prestaciones>
			<Cantidad_Percibida>1200</Cantidad_Percibida>
			<Fecha_Inicio>18 abril</Fecha_Inicio>
			<Fecha_Final>6 agosto</Fecha_Final>
		</L_Prestaciones>
	</afiliado>

		<afiliado>
		<DNI>7694894B</DNI>
		<Nombre>pepe</Nombre>
		<Apellidos>perez</Apellidos>
		<Situacion_Laboral>En_paro</Situacion_Laboral>
		<F_Nacimiento>
			<Dia>15</Dia>
			<Mes>4</Mes>
			<Anio>1998</Anio>
		</F_Nacimiento>
		<L_Bajas>
			<Causa>Accidente</Causa>
			<Fecha_Inicio_Baja>15 abril</Fecha_Inicio_Baja>
			<Fecha_Final_Baja/>
		</L_Bajas>
		<L_Prestaciones>
			<Cantidad_Percibida>1200</Cantidad_Percibida>
			<Fecha_Inicio>18 abril</Fecha_Inicio>
			<Fecha_Final>6 agosto</Fecha_Final>
		</L_Prestaciones>
	</afiliado>

</Lista_Afiliados>
```
