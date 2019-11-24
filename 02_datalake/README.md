Sont décrits ici toutes les étapes pour créer le __datalake__ de notre projet. 
- Celui ci est composé des données brutes / rentrées dans hdfs à froid __la dataRAW__. Le stockage est fait dans le format *.parquet qui présente un bon taux de compression (meme si inférieur au format *.avro) et lisible par impala (contrairement à avro)
- de __dataTABLES__ qui seront crées à l'aide de Spark et un connecteur CASSANDRA. Cassandra a été préféré à MongoDB pour des questions de compromis de vitesse d'écriture et de lecture, et de disponibilité/rapidité/cohérence.
- une __dataVIZ__ a été réalisé avec IMPALA. Impala permet d'effectuer des requetes dans un language d'abstraction proche de SQL sans avoir a passer par des jobs MapReduce. En effet impala va directement "taper" dans HDFS et demeure donc plus rapide.