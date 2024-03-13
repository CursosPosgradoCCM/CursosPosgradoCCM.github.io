# Ejercicios de Python

## Tipos de datos

### Listas

**Ejercicio 1:** Dada una lista de números, intercambia cada par de elementos adyacentes. Por ejemplo, si la lista es `[1, 2, 3, 4, 5]`, el resultado sería `[2, 1, 4, 3, 5]`.

**Soluciones:**

- Solución 1: explicación

Solucion 1 Luis
numeros=[1,2,3,4,5,6]
par=numeros[:-1:2]
impar=numeros[1::2]
numeros[:-1:2]=impar
numeros[1::2]=par
numeros


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
numeros=[1,2,3,4,5,6,7,8,9]
pos_par=numeros[:-1:2]
pos_impar=numeros[1::2]
numeros[:-1:2]=pos_impar
numeros[1::2]=pos_par
numeros
```

Resultado

```output
[2, 1, 4, 3, 6, 5, 8, 7, 9]
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
