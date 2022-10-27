# Paso de parámetros por valor y por referencia

# Ámbito de las variables: las variables que existen en el programa principal no existen en la definición de la función.

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

## En el paso por parámetros por valor lo que se la pasa a la función es el VALOR DEL ARGUMENTO.

![Paso por valor](https://i.imgur.com/p52Mfj2.png)

### Ojo: En el paso por valor ninguna de las variables de la función definida en la parte derecha de la imagen tiene acceso a ninguna variable de las que están a la izquierda de la imagen.

# Por referencia

[Memoria]([http://www.limni.net](https://docs.google.com/presentation/d/1KzSXcWUTSumkybbLSoRjAFRlSVSPJyHXyh59A7knBws/edit?usp=sharing))

# En el paso de parámetros por referencia lo que se le pasa a la función es la dirección de memoria donde está el argumento.

## En lugar de pasar (copiar) esos valores lo que paso es la dirección de memoria donde está almacenado el 25.5 y la dirección de memoria donde está almacenado el 31,7.

## Un primer ejemplo

	Proceso PorValor
		Definir edad Como Entero
		edad <- 20
		CumplirAnyos(edad)
		Escribir "Edad actual: ",edad
	FinProceso

	Funcion CumplirAnyos(x)
		x<-x+1;	
	FinFuncion
	
### Edad vale 20
### Pasamos un 20 como argumento
### x tiene una copia del valor, en este caso 20
### La x vale 21. Edad no cambia, sigue valiendo 20

	Proceso Porreferencia
		Definir edad Como Entero;
		edad <- 20;
		CumplirAnyos(edad);
		Escribir "Edad actual ",edad;
	FinProceso

	Funcion CumplirAnyos(x Por Referencia)
		x<-x+1;	
	FinFuncion

### Edad vale 20
### Pasamos la dirección de edad como argumento
### La x apunta a la dirección de edad 20
### Tanto edad como x ahora valen 21
	

## Un ejemplo completo de la diferencia entre paso por valor y referencia

Comprobamos que los parámetros pasados por valor no modifican a los argumentos.

    num1 <- CalcularMaximo(5,6)

    Funcion PasoPorValor(num)
        num <- num +1
        Escribir num
    FinFuncion    

    Proceso Prueba
        Definir numero1 Como Entero;
        numero1<-5
        PasoPorValor(numero1)
        Escribir numero1
    FinProceso

El resultado será 5 y 6. Hemos incrementado el valor del parámetro formal, pero no se ha modificado el real.

Veamos ahora el mismo programa pero pasando el parámetro por referencia.

    Funcion PasoPorReferencia(num Por Referencia)
        num <- num +1
        Escribir num
    FinFuncion    

    Proceso Prueba
        Definir numero1 Como Entero
        numero1<-5
        PasoPorReferencia(numero1)
        Escribir numero1
    FinProceso

El resultado será 6 y 6. Hemos modificado el parámetro formal y se modificado el real.

## Importante: Los tipos de datos simples: enteros, lógicos, caracteres y demás, por defecto se pasan por valor

## Importante: Los tipos de datos complejos como los arrays por defecto se pasan por referencia.

## Llamada a la función

Para llamar a una función se debe utilizar su nombre y entre paréntesis los parámetros reales que se mandan. La llamada a una función se puede considerar una expresión cuyo valor y tipo es el retornado por la función.
Evidentemente si estamos llamando un procedimiento, la llamada no tendrá ningún tipo.

## Ejemplos de llamadas:

    num1 <- CalcularMaximo(5,6)
    Escribir CalcularMaximo(1,2)
