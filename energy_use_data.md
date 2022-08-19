# Team Enterpernures
### Submitted by **Muhammad Waleed Anjum** & **Ahsan Shakoor**

## Exploratory Data Analysis on Energy Use Data 
## About the Dataset
- This Dataset is taken from HP by Z Unlock. In this dataset, we are going to do EDA on CO2 emissions tracking from various energy industries around the world. We have data for the last 50 years, from 1970 to 2019.

### We do EDA on 2 parts in First part we do EDA on whole data and in Second part we do EDA on Exploring Specific Region Data (Subcontinent).

## Whole Data

### Step-1: Importing Libraries

```
# importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
### Step-2: Importing Dataset

```
df = pd.read_csv('energy_use_data_11-29-2021.csv')
df.head()
```

```
| Column1 | Domain Code | Domain     | Area Code (ISO3) | Area        | Element Code | Element         | Item Code | Item           | Year Code | Year | Unit       | Value    | Flag | Flag Description |
|---------|-------------|------------|------------------|-------------|--------------|-----------------|-----------|----------------|-----------|------|------------|----------|------|------------------|
| 0       | GN          | Energy Use | AFG              | Afghanistan | 7273         | Emissions (CO2) | 6801      | Gas-Diesel oil | 1990      | 1990 | kilotonnes | 231.4918 | F    | FAO estimate     |

| 1       | GN          | Energy Use | AFG              | Afghanistan | 7273         | Emissions (CO2) | 6801      | Gas-Diesel oil | 1991      | 1991 | kilotonnes | 188.5317 | F    | FAO estimate     |

| 2       | GN          | Energy Use | AFG              | Afghanistan | 7273         | Emissions (CO2) | 6801      | Gas-Diesel oil | 1992      | 1992 | kilotonnes | 47.9904  | F    | FAO estimate     |

| 3       | GN          | Energy Use | AFG              | Afghanistan | 7273         | Emissions (CO2) | 6801      | Gas-Diesel oil | 1993      | 1993 | kilotonnes | 38.6116  | F    | FAO estimate     |

| 4       | GN          | Energy Use | AFG              | Afghanistan | 7273         | Emissions (CO2) | 6801      | Gas-Diesel oil | 1994      | 1994 | kilotonnes | 31.4465  | F    | FAO estimate     |
```