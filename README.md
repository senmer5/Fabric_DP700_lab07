# 📊  Real-Time Intelligence with Microsoft Fabric – Stock Market Example

## 🎯 Objective

The purpose of this lab exercise was to learn how to ingest, analyze, and visualize real-time data streams using the Microsoft Fabric platform.  
Stock market data was used as the real-time data source.  
The steps involved included creating a data stream, storing data into a table, querying, visualizing, and setting up an alert mechanism.

---

## 🔧 Steps Performed

### 1. Creating a Workspace

- Logged into Microsoft Fabric.
- Created a new workspace and enabled Fabric capacity.

---

### 2. Creating an Eventstream

**What is Eventstream?**  
An Eventstream is used to capture data from real-time sources and feed it into the system in a structured format.  
With this stream, continuously changing data can be monitored and made available for further analysis.

> In this example, data streaming from the stock market was ingested using an Eventstream named `stock-data`.

- Selected the "Stock market" sample data from the Real-Time Hub.
- Created an Eventstream named `stock-data`.

---

### 3. Creating an Eventhouse

**What is Eventhouse?**  
An Eventhouse is a data warehouse used to store, query, and analyze real-time data.  
It includes a KQL (Kusto Query Language) database that enables fast and scalable queries on incoming data.

> In this example, incoming stock data from the Eventstream was stored in a table for querying and visualization.

- Created a new Eventhouse.
- Added a table named `stock` inside the KQL database.
- Linked the Eventstream to stream real-time data into the `stock` table.

---

### 4. Data Analysis with KQL (Kusto Query Language)

Performed queries on the `stock` table using KQL:

- Displayed the first 100 records.
- Calculated the average price of each stock over the last 5 minutes using the following query:

```kusto
stock
| where ["time"] > ago(5m)
| summarize avgPrice = avg(todecimal(bidPrice)) by symbol
| project symbol, avgPrice

```
---

### 5. Creating a Real-Time Dashboard

- Added the average price query result to a dashboard.
- Set the visualization format to **Column Chart**.
- Saved the dashboard as **Stock Dashboard**.

---

### 6. Defining an Alert System

- Using the **Activator** feature, configured an alert to send an email when the average price of a stock increased by 100 units.

---

### 7. Cleaning Up Resources

- After completing the lab, deleted the workspace to clean up the resources.

---

## 📌 What Did I Learn?

- Gained hands-on experience with Microsoft Fabric’s Real-Time Intelligence features.
- Understood the connection between **Eventstream** and **Eventhouse**.
- Practiced querying real-time data using **KQL (Kusto Query Language)**.
- Developed skills in creating dashboards for real-time data visualization.
- Learned how to set up automatic alert systems based on real-time data changes.

## Screenshots

<img width="1495" alt="1" src="https://github.com/user-attachments/assets/e4229f49-6bd3-406e-9217-83f2721ef4ab" />

<img width="1472" alt="2" src="https://github.com/user-attachments/assets/a7746eb4-09f2-4ed0-8773-31e1fd6b13bc" />

<img width="1406" alt="3" src="https://github.com/user-attachments/assets/f3ebe790-b9ea-4768-8acd-311ca07406de" />

<img width="1464" alt="4" src="https://github.com/user-attachments/assets/a4ac3231-d7e0-45ae-9ed9-9c184b079d49" />

<img width="1479" alt="5" src="https://github.com/user-attachments/assets/95e1c419-c260-4059-8189-d2b7f7840344" />

<img width="1466" alt="6" src="https://github.com/user-attachments/assets/2e980def-7173-4c30-a45a-5f87661ec8a2" />

<img width="1288" alt="7" src="https://github.com/user-attachments/assets/fd8907d8-a52c-4b28-b344-406890d73831" />

<img width="1484" alt="8" src="https://github.com/user-attachments/assets/8fa7d432-d344-449d-9224-c8a8995a7c7a" />

<img width="1430" alt="9" src="https://github.com/user-attachments/assets/1c557555-cdd9-4a77-9d6e-10bf36dcbc42" />

<img width="1441" alt="10" src="https://github.com/user-attachments/assets/de6ce1cb-aee7-4978-92a5-e61aaab6682a" />

<img width="1448" alt="11" src="https://github.com/user-attachments/assets/a0d357d8-cf20-4bf3-90b3-d88a4b7d6364" />

<img width="1420" alt="12" src="https://github.com/user-attachments/assets/42b03eb1-aaec-40ab-b6ef-ef68ef6cdb34" />



