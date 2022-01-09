![img](img/portada.jpg)

# Análisis de Aplicación de Áreas

Created: October 24, 2021 6:22 PM  
Created By: Yared Martín Pérez  
Github: https://github.com/Yared70/Yared-1DAM/tree/main/Entornos-de-Desarrollo/Practica7-AnalisisDeAplicacionDeAreas  
Tema: Tema 2: Desarrollo de Software  
Type: Informe  



![software-development-life-cycle-removebg-preview.png](img/software-development-life-cycle-removebg-preview.png)

## **Cálculo de Áreas**

Se plantea:

![68747470733a2f2f7777772e70726f6665736f72656e6c696e65612e636c2f67656f6d6574726961696d6167656e2f617265617330312e676966.gif](img/68747470733a2f2f7777772e70726f6665736f72656e6c696e65612e636c2f67656f6d6574726961696d6167656e2f617265617330312e676966.gif)



# Ejercicio



Realiza el análisis para una aplicación que pretende realizar el cálculo de las áreas que muestra la imagen. Define clases y métodos necesarios que creas oportunos.



## Fase de Análisis



El software a desarrollar para el cliente debe hallar el área de la figura geométrica que elija el usuario usando la fórmula que corresponda. Las figuras geométricas son:

1. Cuadrado
2. Rectángulo
3. Rombo
4. Romboide
5. Trapecio
6. Pentágono
7. Círculo
8. Triángulo

## Fase de Diseño



El programa se dividirá en varias funciones. La función main, donde se le solicitará al usuario con un mensaje, que introduzca el número, de una lista, de la figura geométrica de la cual quiere saber el área. 

Se creará una función para cada figura geométrica de la siguiente forma:

1. cuadrado(l)
2. rectángulo(b, h)
3. rombo(D, d)
4. romboide(b, h)
5. trapecio(B, b, h)
6. pentágono(P, a)
7. círculo(r)
8. triángulo(b, h)

Tras el mensaje inicial, se le preguntará al usuario en que unidades quiere introducir los valores y en que unidades quiere los resultados. Tras esto y dependiendo de la elección del usuario, se le pedirá que introduzca el valor o valores necesarios para realizar el cálculo dependiendo de la función a utilizar, de forma que, por ejemplo, si el usuario elije el 1, se le solicitará que indique la longitud del lado del cuadrado, o la longitud de la base y la altura si quiere hallar el área del rectángulo, triángulo o romboide.

Por último, después de llamar a la función y calcular el área, se le preguntará en que unidades quiere el área y se realizará la conversión de unidades si fuera necesario para mostrar al usuario el resultado final.

### Anotaciones:

Debido al uso de divisiones para hallar algunas áreas, se utilizarán todas las variables en float salvo las que se le pidan al usuario que serán convertidas posteriormente.

## Resultado final:

 Al final, se le mostrará al usuario el resultado final con decimales con el siguiente mensaje de ejemplo para el cuadrado:

Al área del cuadrado de lado 2 metros es: 4m^2
