# 🔍 Global Search Trends Aggregator with Google Trends Data

## 🌐 Overview
This project combines data from multiple Google Trends public tables to analyze and compare top and rising search terms across different regions and sources.  
Using SQL, I unified four different datasets into a single structure to enable consistent trend tracking and analysis over time.

## 🧰 Tools & Technologies
- BigQuery Public Datasets
- SQL (UNION, filtering, dynamic date logic)
- Google Trends Tables:
  - `international_top_terms`
  - `top_rising_terms`
  - `top_terms`

## 🎯 Business Goal
To create a reusable data foundation for comparing stable and emerging search trends across the USA, Ukraine, and globally.

## 📊 Combined Sources
| Source Type        | Description |
|--------------------|-------------|
| **Top UA Terms**        | Weekly top search terms in Ukraine |
| **Top USA Rising**      | Most rapidly increasing search terms in the USA |
| **Stable Top Terms**    | Global terms consistently ranking in the Top 10 |
| **Top Global Terms**    | General top search terms with regional breakdown (DMA level) |

## 🧪 Sample Query Structure
```sql
SELECT 'Top UA Terms' AS source_type, term, rank, score
FROM `bigquery-public-data.google_trends.international_top_terms`
WHERE country_name = 'Ukraine'
