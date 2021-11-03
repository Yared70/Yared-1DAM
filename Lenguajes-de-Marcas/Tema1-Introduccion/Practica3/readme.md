![](img/portada.png)

# Práctica3: XML Receta de Cocina

Created: November 3, 2021 12:26 PM  
Github: https://github.com/Yared70/Yared-1DAM/blob/main/Lenguajes-de-Marcas/Tema1-Introduccion/Practica3/readme.md  
Property: Yared Martín Pérez  
Tema: Tema 1: Introducción al Lenguaje de Marcas  
Type: Informe  

![ies.png](img/ies.png)

---

![](img/tarea.png)

# Práctica 3: XML Receta de Cocina

Diseñar un documento válido en XML que permita estructurar la información de las recetas de cocina de un restaurante y aplicarlo a la siguiente receta de cocina. Hay que hacerlo de modo que un sistema informático pueda realizar búsquedas por ingredientes, cantidad de comensales o nombre de la receta.

**Sopa de cebolla (4 personas)**

Ingredientes:

- 1 Kg. de cebollas.
- 2 l. de caldo de carne.
- 100 gr. mantequilla.
- 1 cucharada de harina.
- 100 gr. de queso emmental suizo o gruyére rallado.
- Pan tostado en rebanadas.
- Tomillo.
- 1 hoja de laurel.
- Pimienta.

Proceso:

- Pelar y partir las cebollas en rodajas finas.
- Rehogarlas con la mantequilla, sal y pimienta a fuego lento hasta que estén transparentes sin dorarse.
- Añadir la harina sin dejar de remover.
- Ponerlo en una cazuela con el caldo, el tomillo y el laurel.
- Dejar cocer a fuego lento durante unos 15 minutos. -Poner las rebanadas de pan encima, espolvorear el queso y gratinar al horno.

### XML:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<receta>
	<nombre_receta>Sopa de cebolla</nombre_receta>
	<comensales>4</comensales>
	<ingrediente cantidad="1" medida="Kg" nombre="Cebollas" />
	<ingrediente cantidad="2" medida="Litros" nombre="Caldo de carne" />
	<ingrediente cantidad="100" medida="Gramos" nombre="Mantequilla" />
	<ingrediente cantidad="1" medida="Cucharada" nombre="Harina" />
	<ingrediente cantidad="100" medida="Gramos" nombre="Queso emmental suizo o gruyére rallado" />
	<ingrediente cantidad="" medida="" nombre="Pan tostado en rebanadas" />
	<ingrediente cantidad="" medida="" nombre="Tomillo" />
	<ingrediente cantidad="1" medida="Hoja" nombre="Laurel" />
	<ingrediente cantidad="" medida="" nombre="Pimienta" />
	<preparacion>
		<paso numero="1">Pelar y partir las cebollas en rodajas finas.</paso>
		<paso numero="2">Rehogarlas con la mantequilla, sal y pimienta a fuego lento hasta que estén transparentes sin dorarse.</paso>
		<paso numero="3">Añadir la harina sin dejar de remover.</paso>
		<paso numero="4">Ponerlo en una cazuela con el caldo, el tomillo y el laurel.</paso>
		<paso numero="5">Dejar cocer a fuego lento durante unos 15 minutos.</paso>
		<paso numero="6">Poner las rebanadas de pan encima, espolvorear el queso y gratinar al horno.</paso>
	</preparacion>
</receta>
```
