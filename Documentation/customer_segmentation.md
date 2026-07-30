# Customer Segmentation (DAX)

## Description
This calculated column categorizes customers into High, Medium, and Low Value segments based on their Customer Lifetime Value (CLTV).

## DAX Formula

```DAX
Customer Segment =
SWITCH(
    TRUE(),
    [CLTV] >= 30000, "High Value",
    [CLTV] >= 15000, "Medium Value",
    "Low Value"
)
```

## Segments
- High Value: CLTV ≥ 30,000
- Medium Value: CLTV ≥ 15,000 and < 30,000
- Low Value: CLTV < 15,000

## Purpose
This segmentation helps identify the most valuable customers for targeted marketing, retention strategies, and business decision-making.
