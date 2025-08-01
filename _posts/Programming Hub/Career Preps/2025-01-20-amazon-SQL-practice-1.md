---
layout: post
title: Amazon SQL Practice Questions
date: 2025-01-20 13:30 -0800
description: Practice Amazon SQL technical questions
author: khoa_pham
categories: [Programming Hub, Career Preps]
pin: false
math: true
mermaid: true
toc: true
comments: true
---

> Link to [Amazon DS Description Requirements](https://d2tw286t6volch.cloudfront.net/index.html#/lessons/2RUdJIA_cHNU6D7wWnQi4SmW_5ulKVAj)


## Aggregate Functions
### Q1: Number of Shipments per Month - Easy
Write a query that will calculate the number of shipments per month. The unique key for one shipment is a combination of `shipment_id` and `sub_id`. Output the year_month in format `YYYY-MM` and the number of shipments in that month.

Table: `amazon_shipments`
```sql
CREATE TABLE amazon_shipments (
    shipment_date DATE,
    shipment_id bigint,
    sub_id bigint,
    weight float,
);
```

#### Solutions

```sql
SELECT to_char(shipment_date, 'YYYY-MM') AS year_month,                -- Extract Year-Month
        count(distinct (shipment_id, sub_id)) AS shipment_count        -- Count unique shipments
        -- COUNT(DISTINCT shipment_id || '-' || sub_id) AS num_shipments
FROM amazon_shipments
GROUP BY year_month
ORDER BY year_month
```

```python
import pandas as pd
# Convert shipment_date to 'YYYY-MM' format
amazon_shipment['year_month'] = pd.to_datetime(amazon_shipment['shipment_date']).dt.to_period('M')
# Create a unique identifier for each shipment
amazon_shipment['unique_key'] = amazon_shipment['shipment_id'].astype(str) + '_' + amazon_shipment['sub_id'].astype(str)
# Group by month and count unique shipments
result = amazon_shipment.groupby('year_month')['unique_key'].nunique().to_frame('count').reset_index()
# Sort by year_month
result = result.sort_values(by='year_month')
```

### Q2: Latest