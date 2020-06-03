# Introducción a Spark

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Luxillo/Spark/blob/master/Colab%20y%20PySpark%20-%20Inicio.ipynb)
 
## Jugando con Colab & Spark (Python)

De forma bastante practico queremos brindar un notebook para que pueda utilizar pyspark en Colab de la forma mas sencilla, seria ejecutar algunos de los siguientes comandos en una celda en Colab:

Haremos lo siguiente :

- Instalacion Rapida Java y Spark
- Configuracion Veloz de Java y Spark
- Ejemplos utilizando PySpark

## instalar Java

__Java__ 
Podemos instalar y hacer rapidamente que nuestro entorno de ejecucion implemente Java

```shell
!apt-get install openjdk-8-jdk-headless -qq > /dev/null
import os # libreria de manejo del sistema operativo
os.system("wget -q https://www-us.apache.org/dist/spark/spark-2.4.5/spark-2.4.5-bin-hadoop2.7.tgz")
os.system("tar -xzvf spark-2.4.5-bin-hadoop2.7.tgz")
!ls ##listamos los archivos
```

__Pyspark__
Ahora instalamos Pyspark

```
!pip install -q pyspark

```

## Configuramos las Variables
__JAVA_HOME__  define la ubicación de instalación de java y permite instanciarlo desde cualquier lugar en el sistema.

__SPARK_HOME__  define la ubicación de la instalación de Spark y permite instanciarlo desde cualquier lugar del sistema.

```shell
# Variables de Entorno
os.environ["JAVA_HOME"] = "/usr/lib/jvm/java-8-openjdk-amd64"
os.environ["SPARK_HOME"] = f"/content/spark-2.4.5-bin-hadoop2.7"
```

### Iniciamos y utilizamo PySpark

Iniciamos con la importacion de librerias necesarias y la creación de una sesión de Spark.

```shell
# Cargar Pyspark
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("Test_spark").master("local[*]").getOrCreate()
```

Imprimimos los valores de la sesion

  * In code this looks as follows:

```scala
spark
```

**SparkSession - in-memory**

**SparkContext**

[Spark UI](http://ff9f989de030:4040/)

- Version

  `v2.4.5`

- Master

  `local[*]`

- AppName

  `Test_spark`

## Mas Codigo

Puedes Descargar el notebook con todas las instrucciones :

 * [Notebook: Iniciando en Spark con Colab](https://github.com/Luxillo/Spark/blob/master/Colab%20y%20PySpark%20-%20Inicio.ipynb)

## License

This library is licensed under the Apache 2.0 License.
