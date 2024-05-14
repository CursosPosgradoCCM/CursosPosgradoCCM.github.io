# Ejercicios de SQL

## 5.1 Bases de datos y manipulación

### 5.1.1 Seleccionar datos

**Ejercicio 1:**  ¿Qué columnas de la base de datos son enteros? ¿Cómo realizas esa consulta en SQL?

**Soluciones:**

 - Luis

```python


```
```output

```
**Ejercicio 2:** Realiza un query de la columna `name` de lde la tabla `Site`.

**Soluciones:**

 - Luis

```python
sqlite> SELECT name FROM Site;

```
```output
name
-----
DR-1
DR-3
MSK-4
```

### Ordenar y remover duplicados
**Ejercicio: ** Escribir un query que regrese el nombre completo de los científicos de la tabla `Person` ordenado por apellido.

**Soluciones:**

```python
sqlite> SELECT personal || family AS nombre_completo FROM Person ORDER BY family;

```
```output
nombre_completo
----------------
FrankDanforth
WilliamDyer
AndersonLake
FrankPabodie
ValentinaRoerich
```

### Filtrar

**Ejercicio 1:** Selecciona todos los sitios que están a lo más a 48 grados del ecuador.

**Soluciones:**

```python
SELECT * FROM Site WHERE ABS(lat) <= 48;

```
```output
name  lat     long
----  ------  -------
DR-3  -47.15  -126.72
```


**Ejercicio 2:** La salinidad normal de las lecturas debería ser entre 0.0 y 1.0. Escribe un query que seleccione todos los registros de `Survey` con valores de salinidad ('sal') fuera de este rango.

**Soluciones:**

```python
SELECT * FROM Survey WHERE quant = 'sal' AND (reading < 0.0 OR reading > 1.0);


```
```output
taken  person  quant  reading
-----  ------  -----  -------
752    roe     sal    41.6
837    roe     sal    22.5
```





















