# Práctica 7: XML y XSD Personas

Created: November 1, 2021 7:37 PM
Property: Yared Martín Pérez
Tema: Tema 1: Introducción al Lenguaje de Marcas
Type: Informe

![ies.png](Pra%CC%81ctica%207%20XML%20y%20XSD%20Personas%2036a78ffbf59d4f8ea5fcd9c7c7b1652b/ies.png)

# Personas

Proporcionar un XML schema que refleje esta jerarquía suponiendo que **nacimiento**
 es un elemento opcional y hay al menos una dirección. Para la jerarquía
 de datos que se muestra a continuación, y teniendo en cuenta los 
siguientes requisitos:

- Dependiendo de si la persona es *hombre o mujer*, aparecerá en el documento elemento **varón** (como en el gráfico) o el elemento **hembra**.
- Los valores del atributo **día** están comprendidos entre 1 y 31. Definir el tipo **tipoDia** para ello.
Los valores del atributo **mes** son de tipo cadena y tienen que coincidir con uno de los meses del año. Definir el tipo **tipoMes** para ello.
- Los valores del atributo **anyo** están comprendidos entre 1900 y 2011. Definir el tipo **tipoAnyo** para ello.
- Los valores de **nombre**, **calle**, **población** y **provincia** tienen como máximo 50 caracteres. Definir el tipo **tipoNombre** para ello.
- El código postal es un entero de 5 dígitos. Definir el tipo **tipoCodPostal** para ello.

![esquemapersonas.jpeg](Pra%CC%81ctica%207%20XML%20y%20XSD%20Personas%2036a78ffbf59d4f8ea5fcd9c7c7b1652b/esquemapersonas.jpeg)

Generar un fichero XML instancia que referencie al schema y contenga los siguientes datos:

- Elemento 1:
    - Juan Pardo
    - Fecha de nacimiento: 10 de Abril de 1982
    - Dirección: Caoba, 1, Madrid
    - 28005 Madrid
- Elemento 2:
    - María López.
    - Dirección1: Roncato,1, Illescas
    - 45200 Toledo
    - Dirección2: Paseo de la Esperanza 15, 1º A, Madrid
    - 28005 Madrid

### XSD:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"> 
<xsd:simpleType name="tipoDia">
 	<xsd:restriction base="xsd:int">
 		<xsd:minInclusive value="1"/>
 		<xsd:maxInclusive value="31"/>
 	</xsd:restriction>
</xsd:simpleType> 
<xsd:simpleType name="tipoMes">
    <xsd:restriction base="xsd:string">
        <xsd:enumeration value="Enero"/>
        <xsd:enumeration value="Febrero"/>
        <xsd:enumeration value="Marzo"/>
		<xsd:enumeration value="Abril"/>
		<xsd:enumeration value="Mayo"/>
		<xsd:enumeration value="Junio"/>
		<xsd:enumeration value="Julio"/>
		<xsd:enumeration value="Agosto"/>
		<xsd:enumeration value="Septiembre"/>
		<xsd:enumeration value="Octubre"/>
		<xsd:enumeration value="Noviembre"/>
		<xsd:enumeration value="Diciembre"/>
    </xsd:restriction>
</xsd:simpleType> 
<xsd:simpleType name="tipoAnyo">
 	<xsd:restriction base="xsd:int">
	 	<xsd:minInclusive value="1900"/>
 		<xsd:maxInclusive value="2011"/>
 	</xsd:restriction>
</xsd:simpleType> 
<xsd:simpleType name="tipoNombre">
 	<xsd:restriction base="xsd:string">
 		<xsd:maxLength value="50"/>
 	</xsd:restriction>
</xsd:simpleType> 
<xsd:simpleType name="tipoCodPostal">
 	<xsd:restriction base="xsd:int">
 		<xsd:totalDigits value="5"/>
	</xsd:restriction>
</xsd:simpleType>
<xsd:element name="direccion">
 	<xsd:complexType>
 		<xsd:sequence>
 			<xsd:element name="calle" type="tipoNombre"/>
 			<xsd:element name="poblacion" type="tipoNombre"/>
			<xsd:element name="provincia" type="tipoNombre"/>
 			<xsd:element name="cpostal" type="tipoCodPostal"/>
 		</xsd:sequence>
 	</xsd:complexType>
</xsd:element>
<xsd:element name="persona">
 	<xsd:complexType>
 		<xsd:sequence>
		<xsd:element name="nombre" type="tipoNombre"/>
		<xsd:element name="nacimiento">
 	<xsd:complexType>
 		<xsd:simpleContent>
 			<xsd:extension base="xsd:string">
 				<xsd:attribute name="dia" type="tipoDia"/>
 				<xsd:attribute name="mes" type="tipoMes"/>
 				<xsd:attribute name="anyo" type="tipoAnyo"/> 
 			</xsd:extension>
 		</xsd:simpleContent>
 	</xsd:complexType>
</xsd:element> 
<xsd:element ref="direccion"/>
 	<xsd:choice>
		<xsd:element name="varon"/>
		<xsd:element name="hembra"/>
 	</xsd:choice> 
 		</xsd:sequence>
 	</xsd:complexType>
</xsd:element> 
</xsd:schema>
```

XML

```xml
<persona>
    <nombre>Juan Pardo</nombre>
    <nacimiento dia="10" mes="Abril" anyo="1982"/>
    <direccion>
       <calle>Caoba, 1</calle>
       <poblacion>Madrid</poblacion>
       <provincia>Madrid</provincia>
       <cpostal>28005</cpostal>
    </direccion>
    <varon />
</persona>
<persona>
    <nombre>María López</nombre>
    <direccion>
       <calle>Roncato, 1</calle>
       <poblacion>Illescas</poblacion>
       <provincia>Toledo</provincia>
       <cpostal>45200</cpostal>
    </direccion>
    <direccion>
       <calle>Paseo de la Esperanza, 15, 1A</calle>
       <poblacion>Madrid</poblacion>
       <provincia>Madrid</provincia>
       <cpostal>28005</cpostal>
    </direccion>
    <hembra />
</persona>
```