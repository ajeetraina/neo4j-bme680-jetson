# Sensor Analytics using Neo4j Graph database, BME680 and Python


## Pre-requisite:

- Create a Neo4j hosted instance
- Jetson Nano with BME680 sensor


<img width="1506" alt="image" src="https://user-images.githubusercontent.com/313480/222403946-b3680e55-bc6c-47f2-9c0f-6c5534634e77.png">

```
NEO4J_URI=neo4j+s://c9fafc6e.databases.neo4j.io
NEO4J_USERNAME=neo4j
NEO4J_PASSWORD=OgIOXXXXXXXXXXXXXXY
AURA_INSTANCENAME=Instance01
```

## Importing neo4j

```
pip install neo4j
```

## A Sample Python Script for Sensors

This creates a new node with the label "SensorReading" and the specified properties. You can then query the database to retrieve sensor data and perform analysis or visualization.




```
from neo4j import GraphDatabase
  
driver = GraphDatabase.driver("neo4j+s://c9fafc6e.databases.neo4j.io", auth=("neo4j", "OgIO99y7E6vqoWW2j_S64DLz4wtkdQQ6JV90zHrJsTY"))

with driver.session() as session:
    session.run("CREATE (:SensorReading {sensor_id: 'sensor1', timestamp: datetime(), value: 23.4})")
```

## Running the Script

For this demonstration, I shall be using all the sensor values.
This script generates random values for temperature, humidity, pressure, and gas using the random library, and then inserts these values into Neo4j along with a timestamp. You can modify the ranges for the random values by changing the arguments to random.uniform() as needed.

```
python3 script.py
```

## Installing and Connecting neo4j Docker Extension to hosted neo4j Auro

```
git clone https://github.com/collabnix/neo4j-docker-extension
cd neo4j-docker-extension
make install
```

## Connecting to the remote neo4j instance





<img width="1508" alt="image" src="https://user-images.githubusercontent.com/313480/222407314-1c895e4c-8c27-452f-8ff9-02cc0455c0ab.png">

