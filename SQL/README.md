# Ejercicios de SQL

## 5.1 Bases de datos y manipulación

### 5.1.1 Seleccionar datos

**Ejercicio 1:**  ¿Qué columnas de la base de datos son enteros? ¿Cómo realizas esa consulta en SQL?

**Soluciones:**

 - Luis

```sql


```
```output

```
**Ejercicio 2:** Realiza un query de la columna `name` de lde la tabla `Site`.

**Soluciones:**

 - Luis

```sql
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
Luis
```sql
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

```sql
SELECT * FROM Site WHERE ABS(lat) <= 48;

```
```output
name  lat     long
----  ------  -------
DR-3  -47.15  -126.72
```


**Ejercicio 2:** La salinidad normal de las lecturas debería ser entre 0.0 y 1.0. Escribe un query que seleccione todos los registros de `Survey` con valores de salinidad ('sal') fuera de este rango.

**Soluciones:**

```sql
SELECT * FROM Survey WHERE quant = 'sal' AND (reading < 0.0 OR reading > 1.0);


```
```output
taken  person  quant  reading
-----  ------  -----  -------
752    roe     sal    41.6
837    roe     sal    22.5
```

### Ordenar y remover duplicados

**Ejercicio: ** Escribir un query que regrese el nombre completo de los científicos de la tabla `Person` ordenado por apellido.

**Soluciones:**
Luis

```sql
sqlite> SELECT personal || ' ' || family AS nombre_completo FROM Person ORDER BY family;

```
```output
nombre_completo
-----------------
Frank Danforth
William Dyer
Anderson Lake
Frank Pabodie
Valentina Roerich
```

### Filtrar

**Ejercicio 1:** Selecciona todos los sitios que están a lo más a 48 grados del ecuador.
**Soluciones:**
Luis 
```sql
sqlite> SELECT * FROM Site WHERE lat <= 48 AND lat >= -48;

```
```output
name  lat     long
----  ------  -------
DR-3  -47.15  -126.72
```



**Ejercicio 2:** La salinidad normal de las lecturas debería ser entre 0.0 y 1.0. Escribe un query que seleccione todos los registros de `Survey` con valores de salinidad ('sal') fuera de este rango.

**Soluciones:**
Luis
```sql
sqlite> SELECT * FROM Survey WHERE quant = 'sal' AND (reading < 0.0 OR reading > 1.0);

```
```output
taken  person  quant  reading
-----  ------  -----  -------
752    roe     sal    41.6
837    roe     sal    22.5
```

### Calcular nuevos valores


**Ejercicio:** Después de explorar los datos, nos damos cuenta que Valentina Roerich reporto la salinidad como porcentajes. Escribe un query que regrese todas sus mediciones de la tabla `Survey` con los valores divididos por 100.

**Soluciones:**
Luis
```sql
sqlite> SELECT taken, reading / 100 AS reading FROM Survey WHERE person = 'roe' AND quant = 'sal';

```
```output
taken  reading
-----  -------
752    0.416
837    0.225
```

**Ejercicio:** Utiliza UNION para crear una lista consolidada de mediciones de salinidad en la que solo las de Valentina Roerich hayan sido corregidas según el ejercicio anterior. La salida debería ser algo como:

```output
taken  reading
-----  -------
619    0.13
622    0.09
734    0.05
751    0.1
752    0.09
752    0.416
837    0.21
837    0.225
```

**Soluciones:**
Luis
```sql
sqlite> SELECT taken, reading FROM Survey WHERE quant = 'sal' AND person != 'roe' UNION SELECT taken, reading / 100 AS reading FROM Survey WHERE person = 'roe' AND quant = 'sal' ORDER BY taken;

```
```output
taken  reading
-----  -------
619    0.13
622    0.09
734    0.05
751    0.1
752    0.09
752    0.416
837    0.21
837    0.225
```


**Ejercicio 2:** Los sitios de la tabla `Visited` tienen los códigos `DR-1`, `DR-3`, `MSK-4`. 
Las funciones `instr(X, Y)` y `substr(X, I, [L])` nos ayudan para obtener una lista de identificadores principales de sitios únicos. 
- La función `instr(X, Y)` devuelve el índice basado en 1 de la primera aparición de la cadena Y en la cadena X, o 0 si Y no existe en X.
- La función `substr(X, I, [L])` devuelve la subcadena de X que comienza en el índice I, con una longitud opcional L.

**Soluciones:**
Luis
```sql
sqlite> SELECT DISTINCT substr(site, 1, 2) AS id FROM Visited;

```
```output
id
--
DR
MS
```

### Valores faltantes


**Ejercicio: ** Escribe un query que ordene los registros en `Visited` por fecha, omitiendo las entradas para las cuales no se tiene este valor.

**Soluciones:**
Luis
```sql
sqlite> SELECT * FROM Visited WHERE dated IS NOT NULL ORDER BY dated;

```
```output
id   site   dated
---  -----  ----------
619  DR-1   1927-02-08
622  DR-1   1927-02-10
734  DR-3   1930-01-07
735  DR-3   1930-01-12
751  DR-3   1930-02-26
837  MSK-4  1932-01-14
844  DR-1   1932-03-22
```


### Funciones de agregación


**Ejercicio 1:** ¿Cuántas lecturas de temperatura registró Frank Pabodie y cuál fue su valor promedio?
 
**Soluciones:**
Luis
```sql
sqlite> SELECT person, COUNT(reading) AS count, ROUND(AVG(reading), 2) AS avg_temp FROM Survey WHERE person = 'pb' AND quant = 'temp';

```
```output
person  count  avg_temp
------  -----  --------
pb      2      -20.0
```



**Ejercicio 2:** La media de un conjunto de valores es la suma de los valores dividida por el número de valores. ¿Significa esto que la función avg devuelve 2.0 o 3.0 cuando se le dan los valores 1.0, null y 5.0?

**Soluciones:**
Luis
```sql
sqlite> SELECT AVG(a) AS promedio FROM ( SELECT 1 AS a UNION ALL SELECT NULL UNION ALL SELECT 5 );

```
```output
promedio
--------
3.0
```

**Ejercicio 3:** Calcula la diferencia entre cada lectura individual de radiación y el promedio de todas las lecturas de radiación.

**Soluciones:**
Luis
```sql
sqlite> WITH avg_rad AS (SELECT AVG(reading) AS avg_reading  FROM Survey  WHERE quant = 'rad' ) SELECT taken, person, reading, reading - avg_reading AS diff_from_avg FROM Survey, avg_rad WHERE quant = 'rad';

```
```output
taken  person  reading  diff_from_avg
-----  ------  -------  -------------
619    dyer    9.82     3.2575
622    dyer    7.8      1.2375
734    pb      8.41     1.8475
735    pb      7.22     0.6575
751    pb      4.35     -2.2125
752    lake    2.19     -4.3725
837    lake    1.46     -5.1025
844    roe     11.25    4.6875
```



**Ejercicio 4:** a) La función group_concat(field, separator) concatena todos los valores en un campo utilizando el carácter separador especificado (o ',' si el separador no está especificado). Utilízalo para producir una lista de una sola línea con los nombres de los científicos, como:

```output
William Dyer, Frank Pabodie, Anderson Lake, Valentina Roerich, Frank Danforth
```

**Soluciones:**
Luis
```sql
sqlite> SELECT group_concat(personal || ' ' || family, ', ') AS nombres FROM Person;

```
```output
nombres
-----------------------------------------------------------------------------
William Dyer, Frank Pabodie, Anderson Lake, Valentina Roerich, Frank Danforth
```











