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

Luis: 

```python
numero = 5

if numero % 2 == 0:
    print("El número es par.")
else:
    print("El número es impar.")
    
    #subir ejercicio
```

```output
El número es impar.
```


## Bucles

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
**Ejercicio 2: **
Crea un programa que calcule la suma de los números del 1 al 100 utilizando un bucle for.
**Soluciones**

Luis:
```python
suma = 0

for numero in range(1, 101):
    suma += numero

print("La suma de los números del 1 al 100 es:", suma)

```

```output
La suma de los números del 1 al 100 es: 5050
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

Luis: 
```python
for numero in range(1500, 2701):
    if numero % 7 == 0 and numero % 5 == 0:
        print(numero)
        break
```


```output
1505
```

## Iteraciones sobre secuencias

**Ejercicio 1 **
Escribe un programa que escriba las letras de la frase "Python es genial" por separado

**Soluciones **

Luis:

```python
mensaje = "Python es genial"

for indice, letra in enumerate(mensaje):
    print(f'Índice: {indice}, Letra: {letra}')
```


```output
Índice: 0, Letra: P
Índice: 1, Letra: y
Índice: 2, Letra: t
Índice: 3, Letra: h
Índice: 4, Letra: o
Índice: 5, Letra: n
Índice: 6, Letra:  
Índice: 7, Letra: e
Índice: 8, Letra: s
Índice: 9, Letra:  
Índice: 10, Letra: g
Índice: 11, Letra: e
Índice: 12, Letra: n
Índice: 13, Letra: i
Índice: 14, Letra: a
Índice: 15, Letra: l
```

Francisco Santiago:
```python
mensaje ="Python es genial"
caracter = enumerate(mensaje)
for i, letra in caracter:
    if letra !=" ":
        print(letra)
```
```output
P
y
t
h
o
n
e
s
g
e
n
i
a
l
```
