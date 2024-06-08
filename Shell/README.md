# Ejercicios de Shell

## 2.1 Navegar en archivos y directorios


**Ejercicio 1** Ejercicio: ¿Qué hace la opción -l? ¿Cómo podemos listar en orden de creación e inverso?

**Soluciones:**

- Solución 1(Atenea): explicación

```python
-'ls -l' se utiliza para mostrar información 
detallada sobre cada archivo o directorio en la lista. 
El resultado de ls -l incluirá, para cada entrada:permiso,entrada,
enlaces,propietario,tamaño, fecha de modificación y nombre.
-La opción 'ls -t' lista los ficheros por orden de la marca 
de tiempo (fecha de modificación por defecto).
-La opción 'ls -r'  revierte el orden de clasificación.

```

Escribir resultado

```output
total 640
-rw-rw-r-- 1 johanna johanna    205 may 29 21:46 Base_.Rproj
drwxrwxr-x 2 johanna johanna   4096 may 29 21:46 SQL
-rw-rw-r-- 1 johanna johanna    468 may 29 21:46 README.md
-rw-rw-r-- 1 johanna johanna 623431 may 29 21:46 README.html
drwxrwxr-x 2 johanna johanna   4096 may 29 21:46 Imagenes
-rw-rw-r-- 1 johanna johanna    154 may 29 21:46 _config.yml
drwxrwxr-x 2 johanna johanna   4096 may 29 22:48 Python
drwxrwxr-x 2 johanna johanna   4096 may 30 10:50 Shell

```

**Ejercicio 2**  ¿Qué es una ruta relativa?

- Solución (Atenea): explicación

```python
Las rutas relativas indican el camino para encontrar un elemento, 
pero basándonos en el directorio desde el que se ejecuta la orden. 
```

**Ejercicio 3** ¿A donde nos lleva cd -? y si volvemos a colocar cd - ¿a donde nos lleva? ¿Cuál es la diferencia entre cd .. y cd -?

- Solución 1: explicación

```python
-'cd -' imprime el directorio en el que estuvimos anteriormente y 
nos cambia a él, si lo volvemos a ejecutar una seguda vez imprime el
directorio actual y nos cambia al directorio actual.
-La diferencia entre 'cd -' y 'cd ..' es que el primero nos redirecciona 
al directorio en el que anteriormente estabamos, mientras que el segundo
comando nos direcciona al directorio padre del directorio en el que actualmente
estamos.
```

Escribir resultado. Por ejemplo, supongamos que estamos en el directorio 
`/Descargas/Curso_Comp_Cien/Python` entonces suponiendo que el directorio 
que estuvimos anteriormente fue `/Descargas 'cd -'` nos direccionara a este último, 
mientras que `'cd ..'` nos direccionara a `/Descargas/Curso_Comp_Cien`.


**Ejercicio 4** Ejercicio: Supongamos que tenemos el siguiente árbol de datos en nuestra computadora y que estamos en /Users/thing/. ¿Si colocamos en la terminal ls -F ../backup que nos mostrará?
![ej_shell](https://github.com/CursosPosgradoCCM/CursosPosgradoCCM.github.io/blob/main/Imagenes/ej_shell.png)

- Solución 1 (Mariel): La instrucción solicita listar los archivos que se encuentran en la dirección /Users/backup/ indicando cuales de estos son directorios al imprimir su nombre seguido del símbolo '/' 

`original/ pnas_final/ pnas_sub/`

Escribir resultado

```output
Espacio Resultado
```

**Ejercicio 5**  Explora las opciones -s y -S. ¿Hay diferencia entre mayúsculas y minúsculas?

 Solución(Atenea):

```python
'ls - s' muestra los archivos y el tamaño de cada archivo respectivamente.
'ls -S' muestra los archivos ordenados por tamaño, comenzando con el más grande. 
```

Output con 'ls -s':

```output
total 40
 4 Untitled1.ipynb   4 Untitled2.ipynb  32 Untitled.ipynb
```
Output con 'ls -S':
```output
Untitled.ipynb  Untitled1.ipynb  Untitled2.ipynb
```


## 2.2 Manipulación de archivos y directorios
	
**Ejercicio 1** ¿Cuál es el output de la siguiente colección de comandos?

Soluciones (Mariel)

```output
1. $ pwd
```
Este comando imprime el directorio de trabajo, es decir, la dirección absoluta del directorio en que se encuentra.

```output
2. /Users/haydee/Curso
```
La terminal arroja un error, puesto que esa serie de caracteres no es un comando reconocido por bash.

```output
3. $ ls -F
```
La terminal lista los archivos y/o directorios que se encuentran el la ubicación en que se escribió el comando con la especificación de cuales de estos archivos son directorios por medio del nombre del directorio seguido del símbolo '/'.

```output
4. archivo.txt carpeta/
```
La terminal arroja un error, puesto que esa serie de caracteres no es un comando reconocido por bash.


**Ejercicio 2** Supon que en el directorio data tienes dos archivos. ¿Cuál de los siguientes comandos te daría como resultado: ethane.pdb methane.pdb.

```output
1. ls *t*ane.pdb

2. ls *t?ne.*

3. ls *t??ne.pdb

4. ls ethane.*
```
Solución(Atenea):

```python
ls *t*ane.pdb,
ls *t??ne.pdb
```




## 2.3 Tuberías y filtros

**Ejercicio 1** ¿Cuál opción nos permite extraer solo la cantidad de líneas del archivo?

```python
$ wc -l *.pdb
```

**Ejercicio 2** De los archivos que están en la carpeta alkane, ¿cuál tiene la menor cantidad de líneas?

Solución (Atenea):

```python
$ wc -l *.pdb
```

Escribir resultado

```output
9 methane.pdb
```

**Ejercicio 3**  Realiza las siguientes instrucciones dos veces cada una. Explora las diferencias. ¿Qué hace el operador >>?

Solución(Atenea):

```output
$ echo hola > test1.txt
```

```output
$ echo hola >> test2.txt
```

```python
El operador >> sobreescribe la salida sobre el archivo si es que existe y si no existe crea el archivo.
```

Output(primer comando) despues de ejecutar el comando `cat test1.txt`:

```output
hola
```
Output(segundo comando) despues de ejecutar el comando `cat test2.txt`:

```output
hola
hola
```


**Ejercicio 4** Considera el archivo /exercise-data/animal-counts/animals.csv. Después de aplicar los siguientes dos comandos, ¿qué hay en el archivo animals-subset.csv?

```output
$ head -n 3 animals.csv > animals-subset.csv
$ tail -n 2 animals.csv >> animals-subset.csv
```
Solución (Atenea):

Escribir resultado:


```output
2012-11-05,deer,5
2012-11-05,rabbit,22
2012-11-05,raccoon,7
2012-11-07,rabbit,16
2012-11-07,bear,1
```

### 2.3.1 Tuberías

**Ejercicio 1** De los archivos que están en la carpeta alkanes, obten los 3 archivos con la menor cantidad de líneas.

Solución(Atenea):

```python
$ wc -l *.pdb | sort | head -n 3
```

Escribir resultado

```output
9 methane.pdb
12 ethane.pdb
15 propane.pdb
```

**Ejercicio 2** Explora el archivo exercise-data/animals-counts/animals.csv. ¿Cuál será el resultado de la siguiente instrucción? 

```python
$ cat animals.csv | head -n 5 | tail -n 3 | sort -r > final.txt
```

Solución(Atenea):

```output
2012-11-06,rabbit,19
2012-11-06,deer,2
2012-11-05,raccoon,7
```

**Ejercicio 3** ¿Porqué se necesita colocar el sort antes del uniq?

Solución(Atenea):

```python
El comando uniq solo devuelve los elementos duplicados de un archivo/directorio si es que esta ordenado.
```

Escribir resultado

**Ejercicio 4** Si quisiéramos ver cuantos animales hay de cada tipo, ¿que instrucción tendríamos que usar?

Solución (Mariel)

```bash
cat animals.csv | uniq | wc -l
```

## 2.4 Ciclos

**Ejercicio 1** Crea un ciclo que muestre en pantalla (echo) todos los números del 0 al 9.

Solución(Atenea):
```python
$ for i in {0..9}; do  echo "$i"; done
```


**Ejercicio 2** Ve a la carpeta shell-lesson-data/exercise-data/alkanes y lista lo que hay. 

1) ¿Cuál es el output del siguiente código?

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
Solución(Atenea):
Explica las diferencias.

```python
Con el primer ciclo para cada archivo con extensión .pdb se esta imprimiendo los nombres de todos los archivos con esta extensión.
Mientras que para el segundo ciclo para cada archivo con extensión .pdb se imprime su nombre solo una vez.
```

Salida 1:

```output
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb
alkanes.pdb  all.pdb  cubane.pdb  ethane.pdb  methane.pdb  octane.pdb  pentane.pdb  propane.pdb

```

Salida 2:

```output
alkanes.pdb
all.pdb
cubane.pdb
ethane.pdb
methane.pdb
octane.pdb
pentane.pdb
propane.pdb
```


**Ejercicio 3**  En el directorio shell-lesson-data/exercise-data/alkanes, ¿cuál sería el output del siguiente código?

```python
$ for filename in c*
> do
>     ls $filename
> done
```
Y si en lugar de c* usamos c?

Solución(Atenea):
```python
El segundo código marca un error puesto que no existe ningún archivo con ese nombre.
```

Output del primer código:

```output
cubane.pdb

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

Solución(Atenea):

```python
El primer ciclo imprime los nombres de los archivos con extensión .pdb y además 
copia el contenido del último archivo con tal extensión en el archivo alkanes.pdb.
El segundo ciclo imprime los nombres de los archivso con extensión .pdb pero
difiere en que sobreescribe el contenido de cada uno de los archivos con tal 
extensión en alkanes.pdb
```

**Ejercicio 5**  Crea un ciclo que muestre las últimas 20 líneas de cada archivo en la carpeta creatures.

Solución(Atenea):

```python
$ for filename in *.dat; do  cat $filename | tail -n20 ; done
```


**Ejercicio 6** Crea un ciclo for que copie los dos archivos a dos nuevos archivos llamados original-basilisk.dat, original-unicorn.dat y original-minotaur.dat.

Solución(Atenea):

```python
$ for filename in *.dat; do cp $filename original-$filename; done
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

Solución(Atenea):

```python
El segundo código permite visualizar los cambios que realiza el ciclo sobre el archivo all.pdb.
```
Output código 1:
```output
cat alkanes.pdb
cat cubane.pdb
cat ethane.pdb
cat methane.pdb
cat octane.pdb
cat pentane.pdb
cat propane.pdb
```
El segundo código no altera el archivo all.pdb.
**Ejercicio 8** En la carpeta norht-pacific-gyre se encuentran dos scripts (.sh) y una lista de archivos. Esta lista de archivos tiene terminaciones A, B y en el caso de que la terminación sea Z significa que el archivo está corrupto.

**8.1**¿Cómo podrías darte cuenta que los archivos con terminación Z están corruptos?

Solución(Atenea):

```python
Una posibilidad de distinguir si un archivo esta corrupto o no, es comparar su tamaño con el de los demás, si este difiere mucho
entonces se trata de un archivo corrupto.
```

Usando el comando `ls -sh` vemos que sólo el  archivo 4NENE02018B.txt esta  corrupto.

```output
total 140K
8.0K NENE01751A.txt  8.0K NENE01729B.txt  8.0K NENE01978B.txt  8.0K NENE01843B.txt  4.0K NENE02018B.txt
8.0K NENE01751B.txt  8.0K NENE01843A.txt  8.0K NENE02043A.txt  8.0K NENE01971Z.txt  
8.0K NENE01729A.txt  8.0K NENE02043B.txt  8.0K NENE01978A.txt  8.0K NENE01736A.txt
8.0K NENE01812A.txt  8.0K NENE02040A.txt  8.0K NENE02040Z.txt  8.0K NENE02040B.txt
```
Supongamos que queremos ejecutar el script llamado goostats.sh, este script necesita recibir dos cosas, el archivo de entrada y el nombre del archivo de salida. Supongamos que queremos correr este script para todos los archivos con terminación A y B y que queremos que los archivos de salida se llamen stats-$datafile

**8.2** Crea un ciclo que te muestre en pantalla el nombre del archivo a usar como input.

Solución(Atenea):

```python
$ for datafile in {*A.txt,*B.txt}
> do  
>	echo $datafile
> done
```

**8.3** Crea un ciclo que te muestre en pantalla el nombre del archivo de salida con el formato indicado. Pero quieres asegurarte que para el archivo input sea el nombre correcto el del archivo de salida.

Solución(Atenea):

```python
$ for datafile in {*A.txt,*B.txt} 
> do  
>	echo stats-$datafile 
> done
```


**8.4** Crea un ciclo que muestre los comandos a usarse para correr el script con los archivos de entrada y de salida del paso 2 y 3. Para correr un script como se indica, se usa el comando bash nombre_archivo.sh input output.

```python
$ for datafile in {*A.txt,*B.txt}
> do  
>	bash goostats.sh $datafile  stats-$datafile
> done
```

**8.5** Agrega un echo $datafile para saber en que archivo va tu ciclo.

```python
$ for datafile in {*A.txt,*B.txt}
> do  
>	echo $datafile
>	 bash goostats.sh $datafile  stats-$datafile
> done
```
## 2.5 Scripts

**Ejercicio 1** El archivo animals.csv ya vimos que es un archivo separado por comas que indica las especies y la cantidad de cada uno. Crea un script que se pueda aplicar a cualquier cantidad de archivos con ese formato y que te diga las especies únicas de cada archivo. Crea 3 archivos similares al animals.csv (copia y modifica) y prueba tu script.

Solución(Atenea):

El contenido del script que llamaremos especies.sh  es el siguiente:
```python
for archivo in $@
do
	echo "Para " $archivo "sus especies únicas son: "
	cut -d, -f2 $archivo| sort | uniq  
done

```


```output
$ bash especies.sh animals.csv 
Para  animals.csv sus especies únicas son: 
bear
deer
fox
rabbit
raccoon
```

**Ejercicio 2** Corre el siguiente comando:
```python
$ history | tail -n 5 > recientes.sh
```

¿Qué contiene ese archivo? ¿Observa la última línea del archivo? ¿Porqué guarda esa línea?

Solución(Atenea):
El archivo contiene los ultimos 5 comandos ejecutados en bash(incluyendo el comando ejecutado 
anteriormente). Guarda este último ya que el comando history guarda todos los comandos
ejecutados.

Salida del archivo recientes.sh:

```python
 1807  cat animals.csv 
 1808  cat especies.sh 
 1809  bash especies.sh animals.csv 
 1810  $ history | tail -n 5 > recientes.sh
 1811  history | tail -n 5 > recientes.sh
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
Solución(Atenea):
¿Qué esperas obtener?

```python
Espero obtener el primer y el último renglon de cada archivo con extensión .pdb de la carpeta alkanes.
```

Por cuestiones de espacio, sólo se imprimira las primeras lineas despues de imprimir el comando anterior.

```output
==> alkanes.pdb <==
COMPND      PROPANE

==> all.pdb <==
cat alkanes.pdb

==> cubane.pdb <==
COMPND      CUBANE

```
**Ejercicio 4** Crea un script llamado longest.sh que reciba como argumentos un directorio y una extensión de archivos y que te devuelva el archivo en el directorio, que tenga esa extensión, con el mayor número de líneas.

Solución(Atenea):

El contenido de longest.sh debera ser similar a:
```python
wc -l $1/*$2| sort -r | head -n2|tail -n1
```

Si ejecutamos lo siguiente obtendremos el siguiente output:
```output
$bash longest.sh alkanes '.pdb'
  129 alkanes/alkanes.pdb

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

Solución(Atenea):

```python
El primer script imprime todos los nombres de archivos y directorios que incluyan en su nombre un punto.
El segundo script imprime el contenido de los 3 primeros archivos con extensión .pdb
Por último el tercer archivo imprime el nombre de todos los archivos con extensión .pdb
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

Solución(Atenea):

```python
$ bash -x do-errors.sh NENE*A.txt NENE*B.txt
```

## 2.6  Buscando y encontrando cosas

**Ejercicio 1**  ¿Cómo obtendrían solo lo siguiente del archivo haiku.txt?

```python
and the presence of absence.
```
```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```


**Ejercicio 2** El archivo que se encuentra en la carpeta animal-counts/animals.csv contiene una lista de animales, con su fecha de observación y cuantos animales se observaron.

```python
2012-11-05,deer,5
2012-11-05,rabbit,22
2012-11-05,raccoon,7
2012-11-06,rabbit,19
2012-11-06,deer,2
2012-11-06,fox,4
2012-11-07,rabbit,16
2012-11-07,bear,1
```
Supongamos que queremos crear un script que tome como primer argumento la especie del animal y como segundo argumento el directorio. El script nos debe regresar un archivo llamado especie.txt que contenga una lista de fechas y el número de veces que se observo esa especie. Por ejemplo, rabbit.txt tendría que contener la siguiente información:


```python
Usa las opciones de ayuda de los comandos cut y grep (puedes usar man grep o man cut también para pedir ayuda de esos comandos, la palabra man se refiere a manual.)
```    
    
```python
Respuesta
```

Escribir resultado

```output
Espacio Resultado
```


**Ejercicio 3** En la carpeta exercise-data/writing se encuentra el texto completo de Mujercitas LittleWomen.txt. Usando un for encuentra que hermana aparece más veces: Jo, Meg, Beth, Amy.

**soluciones:**
Francisco:
```python
for hermana in "^Jo" "^Meg" "^Beth" "^Amy"; do grep -w -E "$hermana" LittleWomen.txt | wc -l; done

```

```output
139
72
46
63
```

**Ejercicio 4**  ¿Cómo podrías mostrar en color lo que estás buscando? Explora la ayuda de grep

```python
grep --help
```

Ahí encontramos lo siguiente

```output
grep --color=auto "texto a buscar" archivo
```

**Ejercicio 5**   La opción -v en grep busca todo lo que no concuerde con el patrón indicado. En la carpeta creatures, ¿cómo listarías todos los archivos que terminen en .dat menos el que se llama unicorn? 

```python
find . -type f -name '*.dat' | grep -v './unicorn.dat'
```

Escribir resultado

```output
./basilisk.dat
./minotaur.dat
./original-basilisk.dat
./original-minotaur.dat
./original-unicorn.dat

```
## 2.7 if, while y for

**Ejercicio 1** Crea un case statement para adivinar tu edad. Debes pedirle al usuario que introduzca el número correspondiente a tu edad y que los casos o patrones obtengan por resultado una frase referente a si adivinaron o no su edad. Realiza lo mismo con un if.

**Soluciones**
francisco: 
    
para case:    con nano hacemos el siguiente script y lo guardamos como edad.sh;
```python

echo "Adivina mi edad:"
read edad
case $edad in
                26)
                echo "adivinaste";;
                *)
                echo "no le sabes"
esac

```
corremos
    
````python
bash edad.sh
    
24
    
````

```output
no le sabes
```

Para if:    con nano hacemos el siguiente script y lo guardamos como ifedad.sh;


```python
echo adiviname la edad
read edad
if [ $edad == 26 ]; then
        echo adivinaste
else
        echo no le sabes
fi
```
corremos

```python
bash ifedad.sh

26
```
```output
adivinaste
```

