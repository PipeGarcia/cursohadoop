# hadoop-storage HBASE
## Universidad EAFIT
## Profesor: Edwin Montoya Munera - emontoya@eafit.edu.co

# HBASE

## HBASE DESDE EL cli

1. Conectarse al cluster Hadoop (192.168.10.75)

entrar al cluster:

```
$ ssh username@192.168.10.75
username@192.168.10.75's password: ******
[username@hdplabmaster ~]$
```

2. Comandos interactivos

```
      $ hbase shell

      hbase(main):001:0> help

      hbase(main):002:0> create ‘test’, ‘cf’

      hbase(main):003:0> list ‘test’

      // listar todas las TABLAS
      hbase(main):01x:0> list

      hbase(main):004:0>put 'test', 'row1', 'cf:a', 'val1'

      hbase(main):005:0> scan ‘test’

      hbase(main):006:0> get ‘test’, ‘row1’

      hbase(main):007:0>put 'test', 'row2', 'cf:b', 'val2'
      hbase(main):008:0>put 'test', 'row3', 'cf:a', 'val3'
      hbase(main):009:0>put 'test', 'row4', 'cf:b', 'val4'
      hbase(main):010:0>put 'test', 'row5', 'cf:a', 'val4'

      //listar todos los valores de una columna en una CF:

      hbase(main):011:0>scan ‘test', {COLUMNS => 'cf:a’}
```
3. Acceso a HBASE desde la API Java

ejemplo1: agregar datos a una tabla y leerlos.

[HBaseClient.java](src/hbase/HBaseClient.java)

compilar:

      $ cd 04-hbase/src
      $ javac -cp `hadoop classpath`:`hbase classpath` hbase/HBaseClient.java

Ejecutar:

      $ java -cp `hadoop classpath`:`hbase classpath` hbase.HBaseClient      

ejemplo2: crear una tabla

[HBaseCreateTable.java](src/hbase/HBaseCreateTable.java)

compilar:

      $ cd 04-hbase/src
      $ javac -cp `hadoop classpath`:`hbase classpath` hbase/HBaseCreateTable.java

Ejecutar:

      $ java -cp `hadoop classpath`:`hbase classpath` hbase.HBaseCreateTable <table_name>

# TAREA:
