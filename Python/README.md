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

**Ejercicio 1**
Escribe un programa que escriba las letras de la frase "Python es genial" por separado

**Soluciones**

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
###  Compresiones de listas


**Ejercicios** 

Ejercicio 1: Dada una lista de números, crea una lista que contenga los cuadrados de los números pares presentes en la lista dada.

**Soluciones**

Luis

```python
numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
cuadrados_numeros_pares = [x ** 2 for x in numeros if x % 2 == 0]
print(cuadrados_numeros_pares)
        

```
```output
[4, 16, 36, 64, 100]
```

Ejercicio 2: Dada una lista de cadenas, crea una nueva lista que contenga todas las cadenas convertidas a mayúsculas. Por ejemplo, si tienes la lista siguiente:

```python

palabras = ['hola', 'python', 'mundo', 'programación']
```
Lo que quieres obtener es:

```python

['HOLA', 'PYTHON', 'MUNDO', 'PROGRAMACIÓN']
```
Luis:

```python
cadenas = ['hola', 'python', 'mundo', 'programación']
cadenas_mayusculas = [cadena.upper() for cadena in cadenas]
print(cadenas_mayusculas)


```
```output

['HOLA', 'PYTHON', 'MUNDO', 'PROGRAMACIÓN']
```

Ejercicio 3: Dada una lista de números enteros, crea una lista que contenga solo los números primos de la lista dada, sin definir una función adicional.

Luis: 

```python
numeros_enteros = [1,2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
numeros_primos = [numero for numero in numeros_enteros if numero > 1 and all(numero % i != 0 for i in range(2, int(numero**0.5) + 1))]

print(numeros_primos)

```
```output
[2, 3, 5, 7, 11, 13]
```

##  Numpy 
### Operaciones Básicas con NumPy

**Ejercicio 1** Crea un array unidimensional con los números del 1 al 10 e imprímelo.

Luis

```python
array = list(range(1, 11))
print(array)

```
```output
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

**Ejercicio 2** Crea una matriz 3x3 con todos los elementos iguales a 5 e imprímela.

Luis

```python
matriz = np.full((3, 3), 5)
print(matriz)

```
```output
[[5 5 5]
 [5 5 5]
 [5 5 5]]
```

**Ejercicio 3** Calcula la suma de los elementos de la siguiente matriz:
```python
matriz = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]]

```

**Soluciones**
Luis 

```python
matriz = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
suma_elementos = np.sum(matriz)
print(suma_elementos) 

```
```output
45
```

### Indexación y Rebanado

**Ejercicio 1** Considera es siguiente array, extrae usando este tipo de indexado las letras O,M,G y W, O, Z. 

```python
np.array(list("ABCDEFGHIJKLMNOPQRSTUVWXYZ1234")).reshape(5,6)

```
```output
array([['A', 'B', 'C', 'D', 'E', 'F'],
       ['G', 'H', 'I', 'J', 'K', 'L'],
       ['M', 'N', 'O', 'P', 'Q', 'R'],
       ['S', 'T', 'U', 'V', 'W', 'X'],
       ['Y', 'Z', '1', '2', '3', '4']], dtype='<U1')
```

** Soluciones **

Luis

```python
array = np.array(list("ABCDEFGHIJKLMNOPQRSTUVWXYZ1234")).reshape(5,6)

letras_extraidas = array[[2, 2, 1, 3, 2, 4], [2, 0, 0, 4, 2, 1]]
print(letras_extraidas)

```

```output
['O' 'M' 'G' 'W' 'O' 'Z']
```

**Ejercicio 2** Considerea el siguiente array y extrae el array [ 5, 6, 7, 8, 9, 10, 11] usando una máscara boleana:
```python

np.arange(12).reshape(4,3)
```

```output
## array([[ 0,  1,  2],
##        [ 3,  4,  5],
##        [ 6,  7,  8],
##        [ 9, 10, 11]])
```

**Soluciones**

```python


```
```output

```

### Ordenamiento

**Ejercicio 1**   Para el array a=np.ones((5,5,5)), responde lo siguiente para cada caso:
* ¿Cuál es su dimensión?

* ¿Es una vista o una copia?

Después verifica tu respuesta.

v = a[1, ::2, ::2]

v = a[2,:]

v = a[[0, 1],:]

v = a[[2,3], [2,3]]

**Soluciones**

```python
import numpy as np

a = np.ones((5,5,5))

v1 = a[1, ::2, ::2]
v2 = a[2,:]
v3 = a[[0, 1],:]
v4 = a[[2,3], [2,3]]

print("Dimensiones de v1:", v1.ndim)
print("Es vista:", v1.base is a)
print("Dimensiones de v2:", v2.ndim)
print("Es vista:", v2.base is a)
print("Dimensiones de v3:", v3.ndim)
print("Es vista:", v3.base is a)
print("Dimensiones de v4:", v4.ndim)
print("Es copia:", v4.base is None)

```

```output
Dimensiones de v1: 2
Es vista: True
Dimensiones de v2: 2
Es vista: True
Dimensiones de v3: 3
Es vista: False
Dimensiones de v4: 2
Es copia: True
```
**Ejercicio 2** Ejercicio 2: Recrea los siguientes plots usando lo siguiente:

Realiza un array de solo ceros que será tu base.

Cambia los valores correspondientes a 1.

Usa plt.matshow(nombre_array) para hacer el plot.

Para importar el paquete para hacer el plot realiza lo siguiente: 

```python

%matplotlib inline
from matplotlib import pyplot as plt #libreria para hacer plots
```
![Ejercicio de ASPP Latam](C:/Users/ABC/Documents/curso/git/phyton/CursosPosgradoCCM.github.io/Imagenes/ordenamientoeje2.png)

**Soluciones**

Luis 4
```python
tablero = np.zeros((11, 11))
tablero[::2, ::2] = 1
tablero[1::2, 1::2] = 1
tablero_invertido = 1 - tablero
plt.matshow(tablero_invertido)  
plt.show()

```
```python
![Ejercicio de ASPP Latam](C:/Users/ABC/Documents/curso/git/phyton/CursosPosgradoCCM.github.io/Imagenes/ordenamientosol.png)
```

**Ejercicio 3:** Comienza creando un  array 3x3:

```{python}
ej = np.array([[6,2,3], [1,7,2], [7,6,5]])
ej
```

a) Ordena la última fila en forma ascenderte de manera `in-place`.

b) Ahora, ordena la primera y segunda columna (ascendentemente) de dos formas distintas:

  - Usando fancy-index
  
  - `in-place`, usando rebanadas o índices.

**Soluciones**

Luis:

```python
ej = np.array([[6,2,3], [1,7,2], [7,6,5]])

# Ordenar la última fila en orden ascendente
ej[-1].sort()

print(ej)

import numpy as np

ej1 = np.array([[6, 2, 3], [1, 7, 2], [7, 6, 5]])

# fancy-indexing
sorted_indices_col1 = np.argsort(ej1[:, 0])
sorted_indices_col2 = np.argsort(ej1[:, 1])

ej1[:, 0] = ej1[sorted_indices_col1, 0]
ej1[:, 1] = ej1[sorted_indices_col2, 1]
# in-place
print(ej1)

ej2 = np.array([[6, 2, 3], [1, 7, 2], [7, 6, 5]])
ej2[:, 0].sort()
ej2[:, 1].sort()

print(ej2)


```
```output
[[6 2 3]
 [1 7 2]
 [5 6 7]]

[[1 2 3]
 [6 6 2]
 [7 7 5]]

[[1 2 3]
 [6 6 2]
 [7 7 5]]
```


## 4.8 Visualización de datos
### 4.8.2.2 Scatter plot o gráfico de dispersión

**Ejercicio 1: ** Usando `seaborn`, carga la base de datos `iris` y crea un gráfico de dispersión con matplotlib (sin dividir por color la especie) de la longitud del sepalo vs la anchura del sepalo. 

```{python}
import seaborn as sns

# Cargar el conjunto de datos de iris
iris = sns.load_dataset('iris')

```
**Soluciones: **

Luis: 

```python
import seaborn as sns
import matplotlib.pyplot as plt

iris = sns.load_dataset("iris")

plt.figure(figsize=(8, 6))
sns.scatterplot(x="sepal_length", y="sepal_width", hue="species", data=iris)
plt.xlabel("Longitud del sépalo")
plt.ylabel("Anchura del sépalo")
plt.title("Longitud del sépalo vs Anchura del sépalo por especie")
plt.legend()
plt.show()

```
```output
Imagen pendiente 417
```

**Ejercicio 2:** Usando la base de datos `penguins` de `seaborn` crea el siguiente gráfico de dispersión.

```{python, echo = FALSE}
penguins = sns.load_dataset('penguins')

# Ejercicio 2: Scatter Plot
plt.figure(figsize=(8, 6))
sns.scatterplot(data=penguins, x='bill_length_mm', y='bill_depth_mm', hue='species')
plt.title('Relación entre Longitud y Profundidad del Pico')
plt.xlabel('Longitud del Pico (mm)')
plt.ylabel('Profundidad del Pico (mm)')
plt.show()
```


**Soluciones: **

```python
import seaborn as sns
import matplotlib.pyplot as plt

penguins = sns.load_dataset("penguins")
plt.figure(figsize=(8, 6))
plot = sns.scatterplot(x="bill_length_mm", y="bill_depth_mm", hue="species", palette="viridis", data=penguins)
plt.xlabel("Longitud del pico (mm)")
plt.ylabel("Profundidad del pico (mm)")
plt.title("Relación entre Longitud y Profundidad del Pico")
plt.grid(True)
plt.legend(loc = 'lower left')

plt.show()

```
```output
Pendiente imagen Colab
```

### 4.8.2.3 Gráfico de barras

**Ejercicio:** Usando la base de datos `penguins` de seaborn, crea un gráfico de barras que muestre la cantidad promedio de pingüinos de cada especie en la base de datos.

```{python, echo = FALSE}
penguins = sns.load_dataset('penguins')

# Ejercicio 1: Barplot
plt.figure(figsize=(8, 6))
sns.barplot(data=penguins, x='species', y='bill_length_mm', ci=None)
plt.title('Promedio de Longitud del Pico por Especie')
plt.xlabel('Especie')
plt.ylabel('Longitud del Pico (mm)')
plt.show()
```

**Soluciones: **
```python
import seaborn as sns
import matplotlib.pyplot as plt

data = sns.load_dataset("penguins")

plt.figure(figsize=(8, 6))
sns.barplot(x="species", y="bill_length_mm", data=data, hue="species",  palette="viridis")
plt.xlabel("Especie")
plt.ylabel("Longitud de pico  (mm)")
plt.title("Promedio de longitud del pico por especie")
plt.show()

```
```output
Pendiente imagen colab
```

#### 4.8.2.4 Gráfico de pastel
**Ejercicio:** Usando la base de datos `penguins` de seaborn, crea un gráfico de pastel que muestre la proporción de cada especie de pingüino en la base de datos.

```{python, echo = FALSE}
# Ejercicio 4: Pie Plot
plt.figure(figsize=(8, 6))
penguins['species'].value_counts().plot(kind='pie', autopct='%1.1f%%')
plt.title('Proporción de Especies de Pingüinos')
plt.ylabel('')
plt.show()
```

**Soluciones: **
Luis: 

```python
import seaborn as sns
import matplotlib.pyplot as plt
penguins = sns.load_dataset("penguins")
species_counts = penguins['species'].value_counts()
plt.figure(figsize=(8, 6))
plt.pie(species_counts, labels=species_counts.index, autopct='%1.1f%%', startangle=140)
plt.title('Proporción de especies de pingüinos')
plt.axis('equal') 
plt.show()

```
```output
Imagen pendiente
```


#### 4.8.2.5 Boxplot 
**Ejercicio:** Usando la base de datos `penguins` de seaborn, crea un boxplot que compare las longitudes del pico para cada especie de pingüino en la base de datos.

```{python, echo = FALSE}
# Ejercicio 5: Boxplot
plt.figure(figsize=(8, 6))
sns.boxplot(data=penguins, x='species', y='bill_length_mm')
plt.title('Comparación de Longitud del Pico por Especie')
plt.xlabel('Especie')
plt.ylabel('Longitud del Pico (mm)')
plt.show()
```
**Soluciones: **
Luis: 

```python

import seaborn as sns
import matplotlib.pyplot as plt
penguins = sns.load_dataset('penguins')
plt.figure(figsize=(10, 6))
sns.boxplot(x='species', y='bill_length_mm', data=penguins, hue="species")
plt.title('Comparación de longitudes del pico por especie de pingüino')
plt.xlabel('Especie')
plt.ylabel('Longitud del pico (mm)')
plt.show()
```
```output
Imagen pendiente
```

#### 4.8.2.6 Histograma

**Ejercicio:** Usando la base de datos `penguins` de seaborn, crea un histograma que muestre la distribución de las longitudes del pico para todas las especies de pingüinos.

```{python, echo=FALSE}
# Ejercicio 3: Histogram
plt.figure(figsize=(8, 6))
plt.hist(penguins['bill_length_mm'], bins=20, density=False, color='skyblue', edgecolor='black')
plt.title('Distribución de Longitud del Pico')
plt.xlabel('Longitud del Pico (mm)')
plt.ylabel('Frecuencia')
plt.grid(True)
plt.show()
```

**Soluciones: **
```python
penguins = sns.load_dataset('penguins')

plt.figure(figsize=(8, 6))
sns.histplot(data=penguins, x='bill_length_mm', bins=20, kde=True,hue="species")
plt.title('Distribución de Longitudes del Pico')
plt.xlabel('Longitud del Pico (mm)')
plt.ylabel('Frecuencia')
plt.show()

```
```output
Imagen pendiente 22
```

#### 4.8.2.8 Imshow

**Ejercicio: ** Supongamos que tenemos la siguiente función:

\[ f(x, y) = \sin(x) \cdot \cos(y) \]

1. Generar una cuadrícula de valores para \( x \) y \( y \) en el rango de \([-2\pi, 2\pi]\).

2. Calcular los valores de la función \( f(x, y) \) para cada par de puntos \( (x, y) \).

3. Visualizar la función utilizando `imshow` para mostrar la función como una imagen y `contour` para mostrar las curvas de nivel.

4. Tu resultado debe ser similar al siguiente:

```{python, echo = FALSE}

# Paso 1: Generar una cuadrícula de valores para x y y
x = np.linspace(-2*np.pi, 2*np.pi, 100)
y = np.linspace(-2*np.pi, 2*np.pi, 100)
X, Y = np.meshgrid(x, y)

# Paso 2: Calcular los valores de la función f(x, y)
Z = np.sin(X) * np.cos(Y)

# Paso 3: Visualizar la función utilizando imshow y contour
plt.figure(figsize=(10, 5))

# Imshow
plt.subplot(1, 2, 1)
plt.imshow(Z, extent=[-2*np.pi, 2*np.pi, -2*np.pi, 2*np.pi], cmap='viridis')
plt.colorbar(label='f(x, y)')
plt.title('Imagen de f(x, y)')
plt.xlabel('x')
plt.ylabel('y')

# Contour
plt.subplot(1, 2, 2)
contour_plot = plt.contour(X, Y, Z, cmap='viridis')
plt.colorbar(contour_plot, label='f(x, y)')
plt.title('Curvas de Nivel de f(x, y)')
plt.xlabel('x')
plt.ylabel('y')

plt.tight_layout()
plt.show()
```

**Soluciones: **
```python


```
```output

```










































