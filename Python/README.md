# Ejercicios de Python

## Tipos de datos

### Listas

**Ejercicio 1:** Dada una lista de números, intercambia cada par de elementos adyacentes. Por ejemplo, si la lista es `[1, 2, 3, 4, 5]`, el resultado sería `[2, 1, 4, 3, 5]`.

**Soluciones:**

- Solución 1: explicación Luis

```python
lista_1=[1,2,3,4,5,6]
par=lista_1[:-1:2]
impar=lista_1[1::2]
lista_1[:-1:2]=impar
lista_1[1::2]=par
lista_1
```


```python
lista = [1, 2, 3, 4, 5]
```

Escribir resultado

```output
[2,1,4,3,5]
```

- Solución 2:

- Solución Francisco Esp:

```python
numeros = [0, 1, 2, 3, 4, 5, 6, 7, 8]
#Se cambian guardan los elementos que están en las posiciones pares o impares
pos_par = numeros[:-1:2]
pos_impar = numeros[1::2]
#Se cambian los elementos en posiciones pares por los elementos en las posiciones impares y vicesversa
numeros[:-1:2] = pos_impar
numeros[1::2] = pos_par
numeros
```

Resultado

```output
[1, 0, 3, 2, 5, 4, 7, 6, 8]
```

**Ejercicio 2:** Dada una lista de letras, invierte el orden de los elementos en grupos de tres. Por ejemplo, si la lista es `[‘a’, ‘b’, ‘c’, ‘d’, ‘e’, ‘f’, ‘g’, ‘h’, ‘i’]`, el resultado sería `[‘c’, ‘b’, ‘a’, ‘f’, ‘e’, ‘d’, ‘i’, ‘h’, ‘g’]`.

**Soluciones:**

 
- Solución 1(Atenea):

```python
lista = ['a','b','c','d','e','f','g','h','i']
sublista_1,sublista_3 = lista[::3],lista[2::3]
lista[::3] = sublista_3
lista[2::3] = sublista_1
lista
``` 

```

- Solución Frnacisco Santiago:

```python
lista=["a","b","c","d","e","f","g","h","i"]
nueva_lista=lista[0:3][::-1] +lista[3:6][::-1]+lista[6:9][::-1]
print(nueva_lista)

``` 

```

```output
['c', 'b', 'a', 'f', 'e', 'd', 'i', 'h', 'g']
```

## Diciconarios

**Ejercicio 1:**

1) Crea una lista que contenga los nombres de tres amigos tuyos.

2) Crea un diccionario que represente la información de un libro (título, autor, año de publicación).

3) Realiza la suma de dos números y guarda el resultado en una variable.

4) Concatena dos cadenas de caracteres y muestra el resultado.

**Soluciones**
Francisco Santiago:

```python
#1
amigos = [ "Andres", "Brenda", "Cecilia"]
#2
diccionario = { "título": "María", "autor": "Jorge Isaacs", "año de publicación": 1881}
#3
suma = 1+3
#4
print("cadena 1" + " cadena2")
```


Luis:
```python

# 1) Crear una lista que contenga los nombres de tres amigos tuyos.
amigos = ["Mariel", "Francisco", "Karina"]

# 2) Crear un diccionario que represente la información de un libro (título, autor, año de publicación).
libro = {
    "título": "La biblia de los caídos",
    "autor": "Fernando Trujillo Sanz",
    "año_publicación": 2010
}

# 3) Realizar la suma de dos números y guardar el resultado en una variable.
num1 = 10
num2 = 5
resultado_suma = num1 + num2

# 4) Concatenar dos cadenas de caracteres y mostrar el resultado.
cadena1 = "Hola, "
cadena2 = "¿cómo estás?"
resultado_concatenacion = cadena1 + cadena2

# Mostrar resultados
print("Ejercicio 1:")
print("Lista de amigos:", amigos)
print("\nEjercicio 2:")
print("Información del libro:", libro)
print("\nEjercicio 3:")
print("Resultado de la suma:", resultado_suma)
print("\nEjercicio 4:")
print("Resultado de la concatenación:", resultado_concatenacion)

```

```output
Ejercicio 1:
Lista de amigos: ['Mariel', 'Francisco', 'Karina']

Ejercicio 2:
Información del libro: {'título': 'La biblia de los caídos', 'autor': 'Fernando Trujillo Sanz', 'año_publicación': 2010}

Ejercicio 3:
Resultado de la suma: 15

Ejercicio 4:
Resultado de la concatenación: Hola, ¿cómo estás?

```


## Flujo de Control


##Condicionales

**Ejercicio 1:**
Escribe un programa que verifique si un número es positivo, negativo o cero.
**Soluciones**

Francisco Santiago:
```python
number=0
if number > 0:
    print(number, " es positivo")
elif number == 0:
    print("es 0")
else:
    print(number, "es negativo")
```

```output
es 0
```
**Ejercicio 2**
Crea un programa que determine si un número es par o impar.


##Bucles

**Ejercicio 1:**
Escribe un programa que muestre los números del 1 al 10 utilizando un bucle while.
**Soluciones**

Francisco Santiago:
```python
i=0
while i<10:
    i += 1
    print(i)
```
```output
1
2
3
4
5
6
7
8
9
10
```
## Interrupción

**Ejercicio 1:**
Escribe un programa que encuentre el primer número divisible entre 7 y 5, entre 1500 y 2700.

**Soluciones**

Francisco Santiago:
```python
for i in range(1500,2701):
    if i%35 == 0:
        print(i)
        break
```
```output
1505
```


