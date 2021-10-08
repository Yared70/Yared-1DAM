# Práctica 6: Sistema de un Almacén de pedidos

Created: October 8, 2021 5:53 PM  
Github: https://github.com/Yared70/Yared-1DAM/blob/main/Lenguajes-de-Marcas/Tema1-Introduccion/Practica6  
Property: Yared Martín Pérez  
Tema: Tema 1: Introducción al Lenguaje de Marcas  
Type: Informe  

![ies.png](Pra%CC%81ctica%206%20Sistema%20de%20un%20Almace%CC%81n%20de%20pedidos%200b36c77132e34f98a0cabe6ae254662f/ies.png)

# Práctica 6: Sistema de un Almacén de pedidos

Se necesita un formato de archivo para intercambiar productos entre 
almacenes de productos de jardinería y se desea una DTD que incluya 
estas restricciones:

Debe haber un elemento raíz pedido que puede constar de plantas, 
flores y/o utensilios. Los tres elementos pueden aparecer repetidos y en
 cualquier orden. También pueden aparecer por ejemplo 4 plantas, 2 
flores y luego 4 utensilios de nuevo.

- Todo planta tiene un atributo obligatorio nombre.
- Los elementos flores tiene un atributo optativo color.
- Todo elemento utensilio debe tener dentro un elemento obligatorio número.

### XML:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes" ?>
<!DOCTYPE Pedido [
	<!ELEMENT Pedido (plantas*, flores*, utensilios*)>
	
	<!ELEMENT plantas (#PCDATA)>
	<!ATTLIST platas nombre CDATA #REQUIRED>

	<!ELEMENT flores (#PCDATA)>
	<!ATTLIST flores color CDATA #IMPLIED>

	<!ELEMENT utensilios (numero)>

]>

<Pedido>
	<plantas nombre="rosas">4</plantas>
	<flores color="rojas">2</flores>
	<utensilios>
		<numero>6</numero>
	</utensilios>
	<flores color="amarillas">6</flores>
	<utensilios>
		<numero>2</numero>
	</utensilios>
</Pedido>
```
