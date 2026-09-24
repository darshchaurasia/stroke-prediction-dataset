---
type: Dataset
title: Stroke Prediction Dataset
description: CSV dataset reference for notebook analysis, including observed columns, categories, and missing values.
resource: https://github.com/darshchaurasia/stroke-prediction-dataset
tags:
- dataset
- csv
- notebooks
sources:
- resource: https://github.com/darshchaurasia/stroke-prediction-dataset/blob/50524fd7f8861c2415782d5df93b7fe507147f0f/healthcare-dataset-stroke-data.csv
  title: healthcare-dataset-stroke-data.csv
---

# Stroke Prediction Dataset

This repository hosts [healthcare-dataset-stroke-data.csv](healthcare-dataset-stroke-data.csv) for use in analysis notebooks. The checked-in snapshot contains **5,110 data rows and 12 columns**. It does not contain a training notebook or a model.

## Schema

The table below describes the observed CSV representation. Field meanings beyond their names, including measurement units and label definitions, require an upstream data dictionary.

| Column | Observed representation |
| --- | --- |
| `id` | Integer identifier. |
| `gender` | `Female`, `Male`, `Other`. |
| `age` | Numeric value, including fractional values. |
| `hypertension` | `0` or `1`. |
| `heart_disease` | `0` or `1`. |
| `ever_married` | `No` or `Yes`. |
| `work_type` | `Govt_job`, `Never_worked`, `Private`, `Self-employed`, `children`. |
| `Residence_type` | `Rural` or `Urban`; preserve the capital `R`. |
| `avg_glucose_level` | Numeric value. |
| `bmi` | Numeric value or `N/A`; 201 rows contain `N/A`. |
| `smoking_status` | `Unknown`, `formerly smoked`, `never smoked`, `smokes`. |
| `stroke` | `0` or `1`. |

## Examples

Read the downloaded file with the Python standard library:

```python
import csv

with open('healthcare-dataset-stroke-data.csv', newline='', encoding='utf-8') as file:
    rows = list(csv.DictReader(file))

print(len(rows))  # 5110 for the documented snapshot
print(rows[0].keys())
```

`csv.DictReader` returns strings. Convert numeric columns explicitly and handle `N/A` before numerical analysis. Treat `Unknown` as an observed category unless the analysis specifies another policy.

For a notebook, download the file through GitHub or load its raw URL. Use a commit-pinned URL when the analysis needs a reproducible snapshot; the exact source revision is recorded in this document's frontmatter.

## Provenance and reuse

The repository currently contains no upstream attribution, original data dictionary, collection methodology, or license file. The filename alone does not establish those facts. Add the original source and applicable reuse terms when they are known; this guide does not invent an upstream attribution or grant a dataset license.

Counts and category values above were computed from the checked-in CSV during this documentation update.
