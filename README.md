# Module 2 Homework – Workflow Orchestration (Kestra)
Data Engineering Zoomcamp 2026  
Author: Hamza Ayaz

---

## 📌 Overview

This repository contains my solution for Module 2 of the Data Engineering Zoomcamp.

In this module, I implemented workflow orchestration using Kestra to process NYC Taxi data.  
The pipelines include ingestion into PostgreSQL and Google Cloud (GCS + BigQuery), including scheduled executions.

All flows were successfully executed and verified through Kestra logs.

---

## 🛠️ Technologies Used

- Kestra
- Docker
- PostgreSQL
- Google Cloud Storage (GCS)
- BigQuery
- NYC Taxi Dataset

---

## 📂 Repository Structure

 Flows Description

### 1️⃣ 02_postgres_taxi.yaml
Flow responsible for:
- Downloading NYC Taxi data
- Processing CSV files
- Loading data into PostgreSQL

---

### 2️⃣ postgres_taxi_scheduled.yaml
Scheduled version of the Postgres ingestion flow using a Schedule trigger.

---

### 3️⃣ gcp_taxi.yaml
Flow responsible for:
- Downloading taxi data
- Uploading files to Google Cloud Storage
- Loading data into BigQuery

---

### 4️⃣ gcp_taxi_scheduled.yaml
Scheduled version of the GCP ingestion pipeline.

---

## 📊 Homework Answers

### Question 1  
Uncompressed file size for Yellow Taxi 2020-12:

**128.3 MiB**

---

### Question 2  
Rendered value of variable `file`:

**green_tripdata_2020-04.csv**

---

### Question 3  
Total rows for Yellow Taxi data (2020):

**24,648,499**

---

### Question 4  
Total rows for Green Taxi data (2020):

**1,734,051**

---

### Question 5  
Rows for Yellow Taxi data (March 2021):

**1,925,152**

---

### Question 6  
Timezone configuration for New York:

Add the following property inside the Schedule trigger:

timezone: America/New_York

Example:

```yaml
triggers:
  - id: schedule
    type: io.kestra.plugin.core.trigger.Schedule
    cron: "0 9 * * *"
    timezone: America/New_York
