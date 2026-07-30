# DAX Measures for Dashboard KPIs

## Customer KPIs

### Total Customers
```DAX
Total Customers =
DISTINCTCOUNT('cohort_index_dataset'[Customer ID])
```

### Total Orders
```DAX
Total Orders =
DISTINCTCOUNT('cohort_index_dataset'[Invoice])
```

---

## Revenue KPIs

### Total Revenue
```DAX
Total Revenue =
SUM('cohort_index_dataset'[Revenue])
```

### Average Order Value (AOV)
```DAX
Average Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)
```

---

## Retention KPIs

### Cohort Size
```DAX
Cohort Size =
CALCULATE(
    DISTINCTCOUNT('cohort_index_dataset'[Customer ID]),
    'cohort_index_dataset'[Cohort_Index] = 1
)
```

### Retained Customers
```DAX
Retained Customers =
DISTINCTCOUNT('cohort_index_dataset'[Customer ID])
```

### Retention Rate (%)
```DAX
Retention Rate (%) =
DIVIDE([Retained Customers], [Cohort Size], 0)
```

---

## CLTV KPIs

### Purchase Frequency
```DAX
Purchase Frequency =
DIVIDE([Total Orders], [Total Customers], 0)
```

### Average Customer Lifespan
```DAX
Average Customer Lifespan =
AVERAGE('cohort_index_dataset'[Cohort_Index])
```

### Customer Lifetime Value (CLTV)
```DAX
CLTV =
[Average Order Value] *
[Purchase Frequency] *
[Average Customer Lifespan]
```
