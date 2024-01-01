# kafka-elastic-spark

Ce projet permet la visualisation en temps réel du statut des stations de vélos, avec le nombre de vélos disponibles. Cela permet aux utilisateurs de sélectionner des stations pour la prise ou le dépôt de vélos, tout en fournissant des informations utiles pour les gestionnaires de stations.

## Technologies Utilisées

- Apache Kafka: 3.6.0
- Apache Spark: 3.2.4
- Elasticsearch: 8.8.2
- kibana : 8.8.2
- Scala: 2.12.15
- hive: 3.1.3

## Project Architecture

![Project Architecture](images/image.png)

Description of the project architecture:

- **Kafka**: Utilisé pour le streaming en temps réel des données des stations de vélos à partir d'une API disponible.
- **Spark**: Traite et analyse les données en streaming provenant de Kafka pour des informations en temps réel.
- **Elasticsearch**: Stocke les données traitées pour des requêtes et une visualisation efficaces.
- **hive**: Stocke les données traitées dans une base de données.
   



# Running the consumer 
1. Démarrez Kafka et Zookeeper :

    ```sh
    sudo systemctl start kafka
    sudo systemctl start zookeeper
    ```

2. Démarrez Elasticsearch:

    ```sh
    elasticsearch
    ```

3. Exécutez le script Python pour indexer les données dans Elasticsearch :

    ```sh
    python3 index.py
    ```

4. Lancez le producteur Kafka :

    ```sh
    python3 kafka.py
    ```

  
Stockage des Données Historiques dans une Table Hive

Cette section démontre l'intégration de PySpark avec Hive pour le traitement et le stockage des données historiques. Les dépendances suivantes ont été utilisées :


## Exécution du Consommateur

1. Assurez-vous que le cluster Hadoop est en cours d'exécution :

    ```sh
    ./sbin/start-all.sh
    ```

2. Assurez-vous que le service metastore de Hive est en cours d'exécution :

    ```sh
    hive --service metastore
    ```

Now you are ready to run the consumer and store historical data in the Hive table.
