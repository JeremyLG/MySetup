# Spark on Windows

## Again Windows ?? OMEGALUL (yeah if you have no choice again...)

[Follow this StackOverflow answer](https://stackoverflow.com/a/38735202/6434448)

- Put Java, Spark, Scala and SBT in **C:/**, not a sub directory especially with a **SPACE** in it. Otherwise it won't work.
- Don't forget to setup **environnment variables**
- If you have an error linked to **/tmp/hive** check this [solution](https://stackoverflow.com/a/42290821/6434448)

## Scala Spark Jupyter Kernel : Spylon-kernel

It's really a nice kernel, I love it.

[link of the github](https://github.com/Valassis-Digital-Media/spylon-kernel)

## Setup Pyspark with Jupyter on Windows

Developping in Windows LULXD, please avoid, but if you don't have the choice here you go. Environnement variables to set :
- **PYTHON_HOME** => path to your python home
- **PYSPARK_DRIVER_OPTS** => notebook
- **PYSPARK_DRIVER_PYTHON** => %PYTHON_HOME%\Scripts\jupyter.exe
- **PYSPARK_PYTHON** => %PYTHON_HOME%\python.exe
