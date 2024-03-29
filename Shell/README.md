# Ejercicios de Shell

## 2.1 Navegar en archivos y directorios


**Ejercicio 1** Ejercicio: ¿Qué hace la opción -l? ¿Cómo podemos listar en orden de creación e inverso?

**Soluciones:**

- Solución 1: explicación

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 2**  ¿Qué es una ruta relativa?

- Solución 1: explicación

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 3** ¿A donde nos lleva cd -? y si volvemos a colocar cd - ¿a donde nos lleva? ¿Cuál es la diferencia entre cd .. y cd -?

- Solución 1: explicación

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 4** Ejercicio: Supongamos que tenemos el siguiente árbol de datos en nuestra computadora y que estamos en /Users/thing/. ¿Si colocamos en la terminal ls -F ../backup que nos mostrará?

- Solución 1: explicación

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 5**  Explora las opciones -s y -S. ¿Hay diferencia entre mayúsculas y minúsculas?

## 2.2 Manipulación de archivos y directorios
	
**Ejercicio 1** ¿Cual es el output de la siguiente colección de comandos?
```output
1. $ pwd
```
```output
2. /Users/haydee/Curso
```

```output
3. $ ls -F
```

```output
4. archivo.txt carpeta/
```

Escribir resultado

```output
Espacio Resultado 1
```

```output
Espacio Resultado 2
```

```output
Espacio Resultado 3
```

```output
Espacio Resultado 4
```

**Ejercicio 2** Supon que en el directorio data tienes dos archivos. ¿Cuál de los siguientes comandos te daría como resultado: ethane.pdb methane.pdb.

```output
1. ls *t*ane.pdb

2. ls *t?ne.*

3. ls *t??ne.pdb

4. ls ethane.*
```

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```



## 2.3 Tuberías y filtros

**Ejercicio 1** ¿Cuál opción nos permite extraer solo la cantidad de líneas del archivo?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 2** De los archivos que están en la carpeta alkane, ¿cuál tiene la menor cantidad de líneas?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 3**  Realiza las siguientes instrucciones dos veces cada una. Explora las diferencias. ¿Qué hace el operador >>?

```output
$ echo hola > test1.txt
```

```output
$ echo hola >> test2.txt
```

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 4** Considera el archivo /exercise-data/animal-counts/animals.csv. Después de aplicar los siguientes dos comandos, ¿qué hay en el archivo animals-subset.csv?

```output
$ head -n 3 animals.csv > animals-subset.csv
$ tail -n 2 animals.csv >> animals-subset.csv
```

### 2.3.1 Tuberías

**Ejercicio 1** De los archivos que están en la carpeta alkanes, obten los 3 archivos con la menor cantidad de líneas.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 2** Explora el archivo exercise-data/animals-counts/animals.csv. ¿Cuál será el resultado de la siguiente instrucción? 

```output
$ cat animals.csv | head -n 5 | tail -n 3 | sort -r > final.txt
```

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 3** ¿Porqué se necesita colocar el sort antes del uniq?
```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 4** Si quisiéramos ver cuantos animales hay de cada tipo, ¿que instrucción tendríamos que usar?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

## 2.4 Ciclos

**Ejercicio 1** Crea un ciclo que muestre en pantalla (echo) todos los números del 0 al 9.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 2** Ve a la carpeta shell-lesson-data/exercise-data/alkanes y lista lo que hay. 1) ¿Cuál es el output del siguiente código?

```python
$ for datafile in *.pdb
> do
>     ls *.pdb
> done
```

2) ¿Y de este código?

```python
$ for datafile in *.odb
> do 
>     ls $datafile
> done
```
Explica las diferencias.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 3**  En el directorio shell-lesson-data/exercise-data/alkanes, ¿cuál sería el output del siguiente código?

```python
$ for filename in c*
> do
>     ls $filename
> done
```
Y si en lugar de c* usamos c?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 4** Explora el siguiente código. ¿Cuál es el efecto de guardar en este ciclo?

```python
$ for alkanes in *.pdb
> do
>     echo $alkanes
>     cat $alkanes > alkanes.pdb
> done
```
¿Cuál sería la diferencia si usamos ahora >>?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 5**  Crea un ciclo que muestre las últimas 20 líneas de cada archivo en la carpeta creatures.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 6** Crea un ciclo for que copie los dos archivos a dos nuevos archivos llamados original-basilisk.dat, original-unicorn.dat y original-minotaur.dat.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 7** Supongamos que queremos previsualizar los comandos que el siguiente ciclo va a realizar en lugar de correrlo primero para asegurarnos de que está haciendo lo que queremos.


```python
$ for filename in *.pdb
> do
>     cat $filename >> all.pdb
> done
```
¿Cuál de los siguientes dos códigos sería el correcto para revisar los comando a ejecutarse con el ciclo?

```python
# Versión 1
$ for filename in *.pdb
> do
>     echo cat $filename >> all.pdb
> done
```

```python
# Versión 2
$ for filename in *.pdb
> do
>    echo "cat $filename >> all.pdb"
> done
```
Corre los dos códigos y explora el contenido del archivo all.pdb.


```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 8** En la carpeta norht-pacific-gyre se encuentran dos scripts (.sh) y una lista de archivos. Esta lista de archivos tiene terminaciones A, B y en el caso de que la terminación sea Z significa que el archivo está corrupto.

**8.1**¿Cómo podrías darte cuenta que los archivos con terminación Z están corruptos?
```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```
Supongamos que queremos ejecutar el script llamado goostats.sh, este script necesita recibir dos cosas, el archivo de entrada y el nombre del archivo de salida. Supongamos que queremos correr este script para todos los archivos con terminación A y B y que queremos que los archivos de salida se llamen stats-$datafile

**8.2** Crea un ciclo que te muestre en pantalla el nombre del archivo a usar como input.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**8.3** Crea un ciclo que te muestre en pantalla el nombre del archivo de salida con el formato indicado. Pero quieres asegurarte que para el archivo input sea el nombre correcto el del archivo de salida.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**8.4** Crea un ciclo que muestre los comandos a usarse para correr el script con los archivos de entrada y de salida del paso 2 y 3. Para correr un script como se indica, se usa el comando bash nombre_archivo.sh input output.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**8.5** Agrega un echo $datafile para saber en que archivo va tu ciclo.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

## 2.5 Scripts

**Ejercicio 1** El archivo animals.csv ya vimos que es un archivo separado por comas que indica las especies y la cantidad de cada uno. Crea un script que se pueda aplicar a cualquier cantidad de archivos con ese formato y que te diga las especies únicas de cada archivo. Crea 3 archivos similares al animals.csv (copia y modifica) y prueba tu script.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 2** Corre el siguiente comando:
```python
$ history | tail -n 5 > recientes.sh
```

¿Qué contiene ese archivo? ¿Observa la última línea del archivo? ¿Porqué guarda esa línea?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 3** En la carpeta alkanes supongamos que tenemos un script.sh que contiene lo siguiente:
```python
$ head -n $2 $1
$ tail -n $3 $1
```
Dentro del directorio alkanes, corre lo siguiente:
```python
$ bash script.sh '*.pdb' 1 1
```
¿Qué esperas obtener?

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```
**Ejercicio 4** Crea un script llamado longest.sh que reciba como argumentos un directorio y una extensión de archivos y que te devuelva el archivo en el directorio, que tenga esa extensión, con el mayor número de líneas.

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 5**  Considera los archivos que están en la carpeta alkanes. Explica que hace cada uno de los siguientes scripts al correrlos como bash script1.sh *.pdb, bash script2.sh *.pdb y bash script3.sh *.pdb.

```python
# Script 1
echo *.*
```

```python
# Script 2
for filename in $1 $2 $3
do
  cat $filename
done
```

```python
# Script 3
echo $@.pdb
```

```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```


**Ejercicio 6** (Debugging) Supongamos que tienen el siguiente script do-errors.sh en la carpeta north-pacific-gyre:
```python
# Calcular estadisticas para los archivos
for datafile in "$@"
do
  echo $datafile
  bash goostats.sh $datfile stats-$datafile
done
```
Corre en la línea de comandos:

```python
$ bash do-errors.sh NENE*A.txt NENE*B.txt
```
No muestra ninguna salida. Para ver porque, vamos a correrlo de nuevo con la opción -x:

```python
$ bash -x do-errors.sh NENE*A.txt NENE*B.txt
```
¿Cuál es el output? ¿Cuál es la línea responsable del error?


## 2.6  Buscando y encontrando cosas




















