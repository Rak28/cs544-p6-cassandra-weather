# CS544 P6: Cassandra, Weather Data

**Course:** CS544 — Big Data Systems, UW-Madison (Fall 2025)

## Overview

A **gRPC server** that receives weather data (simulating NOAA weather stations) and inserts it into a **Cassandra** table. Explores Cassandra's read/write availability tradeoffs and consistency levels.

## Learning Objectives

- Design and query Cassandra tables with appropriate partition keys
- Implement gRPC services for real-time data ingestion
- Understand CAP theorem tradeoffs in distributed databases
- Configure Cassandra consistency levels (ONE, QUORUM, ALL)

## Architecture

```
Weather Stations (gRPC clients)
        │
        ▼ gRPC
Weather gRPC Server
        │
        ▼
Cassandra Cluster (3 nodes)
```

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Cassandra](https://img.shields.io/badge/Cassandra-1287B1?style=flat&logo=apachecassandra&logoColor=white)
![gRPC](https://img.shields.io/badge/gRPC-244c5a?style=flat&logo=google&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)

## Project Structure

```
p6/
├── docker-compose.yml  # Cassandra cluster + gRPC server
├── server.py           # gRPC server: ingest + query weather data
├── weather.proto       # Protobuf service definition
├── p6.ipynb            # Analysis: availability tradeoffs
└── README.md
```

## Key Experiments

- Measured read/write availability under different consistency levels
- Tested behavior when Cassandra nodes go offline
- Compared throughput at consistency levels ONE vs QUORUM vs ALL

## Author

**Rakshith Sriraman Krishnaraj** · MS CS @ UW-Madison · [LinkedIn](https://www.linkedin.com/in/rakshith-s-k-95b550151/)
