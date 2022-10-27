# Paso de parámetros por valor y por referencia

# ¿Qué es el paso de parámetros?

Cuando llamamos a una función (o procedimiento), podemos pasarle argumentos (~="variables") que contienen valores que la propia función utiliza para realizar sus cálculos (=su cometido).

# Definición de la función tmedia

## OJO: temp1 y temp2 son los parámetros formales.
### indican lo que se espera que reciba esta función cuando alguien la llame.

    Funcion tmedia <- calcularTemperaturaMedia(temp1,temp2)
	  Definir tmedia Real
	  tmedia<-(temp1+temp2)/2
    FinFuncion
 
# Llamada a la función tmedia

## OJO: temp1 y temp2 son los argumentos. Es lo que se le pasa a la función, por tanto temp1 valdría 25.5 y temp2 31.7 después de realizar la llamada.

    calcularTemperaturaMedia(25.5,31.7)
    
## La manera que tenemos de gestionar el cómo llegan los valores desde la llamada de la función hasta la definición de la función. Como los argumentos se asignan a los parámetros formales.

# Por valor

En el paso por parámetros por valor lo que se la pasa a la función es el VALOR DEL ARGUMENTO.

![Paso por valor](https://i.imgur.com/p52Mfj2.png)
