# Dataset reference

**Dataset:** Amazon Sales Dataset  
**Creator:** Karkavelrajaj  
**Source:** https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

Download the original CSV from Kaggle and retain its provided format when using it in QuickSuite. The raw file is not redistributed in this repository.

The analyzed file contains 1,465 rows, 16 columns and 1,351 distinct product IDs. The USB Cables filter is:

```text
Computers&Accessories|Accessories&Peripherals|Cables&Accessories|Cables|USBCables
```

That subset has 233 rows and 161 distinct products. Baseline calculations retain the first occurrence of each product_id in original file order. Currency symbols, thousands separators and percent signs need numeric parsing; preserve invalid/missing values as missing and report valid denominators.

**SHA-256 of the analyzed original file:**

```text
4ba126c4ba8edd35e62e94ce1c853073d832de380184ab4f5f97d1e314882c77
```

The file was uploaded in this conversation as `amazon(1).csv`, while the QuickSuite Space used `amazon.csv`. A future Kaggle download may differ; the hash identifies the particular file analyzed here.

## Limits

- This is a product-listing sample, not transaction data.
- Marketplace links and INR prices support an Amazon India listing context, not buyer or manufacturing location.
- Collection date is unconfirmed; URL parameters are not proof of temporal validity.
- Rating counts do not establish sales or market share.
- Embedded reviewer fields are not a reliably normalized review dataset.
- Product names alone do not establish a validated brand or connector classification.
