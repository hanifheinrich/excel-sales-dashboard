# Superstore Sales Dashboard

Explanatory Superstore Sales Dashoard using Microsoft Excel

- Dataset
- Data Manipulation
- Analysis
- Dashboard

  
## Dataset
- Retail dataset of a global superstore for 4 years.
- Dataset link: https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting/data

## Data Manipulation
Untuk melatih kemampuan excel saya dalam menganalisa data, saya harus memanipulasi data ke dalam pemodelan dimensi dengan python. Dengan model data tersebut, saya dapat menggunakan vlookup untuk membuat tabel master.
```python
import pandas as pd

df = pd.read_csv("Superstore Sales Dataset.csv")
df_fact = df[['Order Date', 'Ship Date', 'Ship Mode', 'Customer ID', 'Postal Code', 'Product ID', 'Sales']]

df_fact['Order Date'] = pd.to_datetime(df_fact['Order Date'], dayfirst=True)
df_fact['Ship Date'] = pd.to_datetime(df_fact['Ship Date'], dayfirst=True)

df_fact.to_csv("fact_table.csv", index=False)
df_fact
```
ETL ini menghasilkan empat tabel yaitu fakta penjualan, dimensi product, dimensi postal, dan dimensi customer.

## Analysis
- Menghitung total customer = `=SUMPRODUCT(1/COUNTIF(Table1[Customer ID],Table1[Customer ID] ))`
- Mencari nilai nama customer = `=VLOOKUP(E9768,dim_customer!$A$1:$D$794,2,)`
- Menghitung lama pengiriman = `=DATEDIF(A9768, B9768, "d")`

![image](https://github.com/user-attachments/assets/0e6a1be5-b33e-4f32-b850-62e2fad7d276)

## Dashboard
![image](https://github.com/user-attachments/assets/29a0be71-4a36-47e2-ad3c-f5b022d6384d)


