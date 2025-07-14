# Best-Value-for-Money-Product-Analytics-on-Amazon

This project analyzes the relationship between product ratings, review sentiment, and price to assess **value-for-money (VFM)** for Amazon products=. Using large-scale product metadata and customer reviews, we built custom scoring metrics and NLP pipelines to identify patterns in consumer perception and product worth.

---

## Overview

In the era of online shopping, understanding which products offer true value-for-money is key to smarter purchasing and better business strategies. By combining customer satisfaction, product popularity, and pricing data, this project uncovers high-VFM products and evaluates the alignment between high ratings and real value.

---

## Research Questions

- **RQ1:** How do Electronics products compare in terms of value-for-money?
- **RQ2:** What % of high-rated products (≥ 4.5 stars) are *actually* good value?
- **RQ3:** What aspects (e.g., price, quality) mentioned in high-rated reviews most influence value perception?
- **RQ4:** How do *CD & Vinyl* products compare to *Electronics* in value-for-money?

---

## Dataset

We used publicly available **Amazon Product Metadata** and **Review datasets** which include:
- **Metadata fields:** `asin`, `title`, `price`, `salesRank`, `related`, etc.
- **Review fields:** `reviewerID`, `reviewText`, `overall`, `helpful`, `reviewTime`, etc.

Each product was linked via `asin` for consistent analysis between metadata and reviews.

---

## Methodology

### Value-for-Money Scoring

We designed a **Weighted VFM metric**:
VFM = (Average Rating × log(Number of Reviews + 1)) / Price


This balances:
- Customer satisfaction (ratings)
- Popularity (review count, log-transformed)
- Affordability (inverse price)

### Preprocessing & Integration

- Cleaned and filtered reviews (missing values, zero prices)
- Grouped reviews by product and computed average rating & review count
- Merged with product metadata

### Review Analysis

- Tokenized and cleaned review text
- Extracted common aspects: **price**, **quality**, **features**, **design**, **value**, **durability**, etc.
- Compared frequencies in positive (≥4 stars) vs. negative reviews
- Analyzed keywords by VFM-ranked products (top 50% only)

---

## Results Snapshot

- Only ~40% of highly rated products (≥4.5) offer top-tier VFM
- Electronics** outperform CD & Vinyl in average VFM
- High-value product types: accessories (cases, chargers), affordable gadgets
- Key influencing review aspects: price, quality, and performance

---

## Technologies Used

- **PySpark** & **Spark SQL**: Distributed data processing
- **Python**: Data cleaning & transformation
- **NLP**: Text processing & keyword frequency analysis
- **Matplotlib**: Visualization

---

## Files in This Repo

- `RQ1_and_RQ4.py` – VFM scoring & category comparison
- `RQ2.py` – Percentage of high-rated products with high VFM
- `RQ3_cdvinyl.py` – Aspect frequency analysis for CD & Vinyl reviews
- `RQ3_electronics.py` – Aspect frequency analysis for Electronics

---

## Report

Refer to the full report for more detailed explanation: [`Best Value-for-Money Product Analytics on Amazon.pdf`](./Best%20Value-for-Money%20Product%20Analytics%20on%20Amazon.pdf)

---

## Project Contributors

- Gabriela Todorova  
- Miglena Pavlova  
- Manojkumar Muthukumaran  
- Raja Ravi Varma Ramesh Babu  
- Akhila

