---
title: Database
date: 26.08.2023 10:00
categories: [Generelt]
tags: [nolek,database,datamatiker,softwareudvikling]
---
## Relational Database

- **Eksempler:**
  - Oracle
  - Microsoft SQL Server
  - MySQL
  - PostgreSQL

- **Beskrivelse:**
  - I relationelle databaser oprettes forskellige tabeller afhængigt af de data, de skal indeholde. For eksempel, i en butikdatabase kan der være tabeller for kunder, produkter og ordrer. Hver tabel tildeles et unikt ID, som bruges til at oprette relationer mellem tabellerne. Når en kunde foretager en ordre, oprettes relationer ved hjælp af disse ID'er.

## Non-Relational Database

### Key-Value Database

- **Eksempler:**
  - Redis
  - Memcached
  - etcd

- **Beskrivelse:**
  - I en key-value database tildeles en unik nøgle til en gruppe data, hvilket gør det nemt at hente data ved hjælp af nøglen. Denne type database bruges normalt som en cache for at reducere data-latens og kan supplere en eksisterende database.

### Document Database

- **Eksempler:**
  - MongoDB
  - CouchDB
  - Firestore
  - DynamoDB

- **Beskrivelse:**
  - Dokumentdatabaser er velegnede, når datastrukturen ikke er fast eller forudsigelig. Data lagres normalt i strukturer som JSON og kan variere i format. Dette gør dem gode til apps, spil og IoT-applikationer.

### Graph Database

- **Eksempler:**
  - Neo4j
  - Dgraph

- **Beskrivelse:**
  - Graph-databaser bruger grafstrukturer til at repræsentere data med noder, egenskaber og relationer. Dette gør dem velegnede til at håndtere komplekse relationer.

<div style="text-align: center">
  <img src="/assets/images/GraphDB.jpg" alt="Something went wrong loading the image." width="200" height="400"/>
</div>

### Wide Column Database

- **Eksempler:**
  - Apache Cassandra
  - HBase

- **Beskrivelse:**
  - En wide column-database ligner en key-value database, men data opbevares i kolonner. Den kan skaleres horisontalt og bruges ofte til store mængder tidsseriedata eller historiske poster.

### Search Engine Database

- **Eksempler:**
  - Solr
  - Elasticsearch
  - Algolia
  - MeiliSearch

- **Beskrivelse:**
  - Search Engine-databaser bruges primært til søgemaskiner og indekserer data for at muliggøre hurtig søgning og filtrering. De kan være dyre at skala op.

### Time Series Database
- **Eksempler:**
  - InfluxDB
  - OpenTSDB
  - TimescaleDB

- **Beskrivelse:**
  - Time Series-databaser er specialiserede i at håndtere data, der ændrer sig over tid, som sensorlæsninger, logfiler og tidsstemplede begivenheder.
