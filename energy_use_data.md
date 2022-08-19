# Team Enterpernures
### Submitted by **Muhammad Waleed Anjum** & **Ahsan Shakoor**

## Exploratory Data Analysis on Energy Use Data 
## About the Dataset
- This Dataset is taken from HP by Z Unlock. In this dataset, we are going to do EDA on CO2 emissions tracking from various energy industries around the world. We have data for the last 50 years, from 1970 to 2019.

### We do EDA on 2 parts in First part we do EDA on whole data and in Second part we do EDA on Exploring Specific Region Data (Subcontinent).

## Whole Data

### Step-1: Importing Libraries

```python
# importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### Step-2: Importing Dataset

```python
df = pd.read_csv('energy_use_data_11-29-2021.csv')
df.head().T
```
> **Output :**

|                  | 0               | 1               | 2               | 3               | 4               |
|------------------|-----------------|-----------------|-----------------|-----------------|-----------------|
| Domain Code      | GN              | GN              | GN              | GN              | GN              |
| Domain           | Energy Use      | Energy Use      | Energy Use      | Energy Use      | Energy Use      |
| Area Code (ISO3) | AFG             | AFG             | AFG             | AFG             | AFG             |
| Area             | Afghanistan     | Afghanistan     | Afghanistan     | Afghanistan     | Afghanistan     |
| Element Code     | 7273            | 7273            | 7273            | 7273            | 7273            |
| Element          | Emissions (CO2) | Emissions (CO2) | Emissions (CO2) | Emissions (CO2) | Emissions (CO2) |
| Item Code        | 6801            | 6801            | 6801            | 6801            | 6801            |
| Item             | Gas-Diesel oil  | Gas-Diesel oil  | Gas-Diesel oil  | Gas-Diesel oil  | Gas-Diesel oil  |
| Year Code        | 1990            | 1991            | 1992            | 1993            | 1994            |
| Year             | 1990            | 1991            | 1992            | 1993            | 1994            |
| Unit             | kilotonnes      | kilotonnes      | kilotonnes      | kilotonnes      | kilotonnes      |
| Value            | 231.4918        | 188.5317        | 47.9904         | 38.6116         | 31.4465         |
| Flag             | F               | F               | F               | F               | F               |
| Flag Description | FAO estimate    | FAO estimate    | FAO estimate    | FAO estimate    | FAO estimate    |

```
# Clean data - exclude unnecessary data improved readability

df_clean = pd.read_csv("energy_use_data_11-29-2021.csv")
x = ["Year Code", "Domain Code", "Domain", "Element Code", "Element", "Item Code", "Flag", ]
df_clean.drop( x, inplace = True, axis =1)
df_clean.head()
```
> **Output :**


|   | Area Code (ISO3) | Area        | Item           | Year | Unit       | Value    | Flag Description |
|---|------------------|-------------|----------------|------|------------|----------|------------------|
| 0 | AFG              | Afghanistan | Gas-Diesel oil | 1990 | kilotonnes | 231.4918 | FAO estimate     |
| 1 | AFG              | Afghanistan | Gas-Diesel oil | 1991 | kilotonnes | 188.5317 | FAO estimate     |
| 2 | AFG              | Afghanistan | Gas-Diesel oil | 1992 | kilotonnes | 47.9904  | FAO estimate     |
| 3 | AFG              | Afghanistan | Gas-Diesel oil | 1993 | kilotonnes | 38.6116  | FAO estimate     |
| 4 | AFG              | Afghanistan | Gas-Diesel oil | 1994 | kilotonnes | 31.4465  | FAO estimate     |


### Step-3: Data Shape

```python
row, col=df.shape
print('Total number of observations/rows/entries:', row)
print('Total number of columns:', col)

row, col=df_clean.shape
print('\nTotal number of observations/rows/entries:', row)
print('Total number of columns:', col)
```
> **Output :**

```python
Total number of observations/rows/entries: 46131
Total number of columns: 14

Total number of observations/rows/entries: 46131
Total number of columns: 7
```

### Step-4: Data Structure

```python
df_clean.info()
```
> **Output :**

```python
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 46131 entries, 0 to 46130
Data columns (total 7 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   Area Code (ISO3)  46131 non-null  object 
 1   Area              46131 non-null  object 
 2   Item              46131 non-null  object 
 3   Year              46131 non-null  int64  
 4   Unit              46131 non-null  object 
 5   Value             46131 non-null  float64
 6   Flag Description  46131 non-null  object 
dtypes: float64(1), int64(1), object(5)
memory usage: 2.5+ MB
```

```python
# Clean data - exclude unnecessary data improved readability

df_clean = pd.read_csv("energy_use_data_11-29-2021.csv")
x = ["Year Code", "Domain Code", "Domain", "Element Code", "Element", "Item Code", "Flag", ]
df_clean.drop( x, inplace = True, axis =1)
df_clean.head()
```
> **Output :**

|   | Area Code (ISO3) | Area        | Item           | Year | Unit       | Value    | Flag Description |
|---|------------------|-------------|----------------|------|------------|----------|------------------|
| 0 | AFG              | Afghanistan | Gas-Diesel oil | 1990 | kilotonnes | 231.4918 | FAO estimate     |
| 1 | AFG              | Afghanistan | Gas-Diesel oil | 1991 | kilotonnes | 188.5317 | FAO estimate     |
| 2 | AFG              | Afghanistan | Gas-Diesel oil | 1992 | kilotonnes | 47.9904  | FAO estimate     |
| 3 | AFG              | Afghanistan | Gas-Diesel oil | 1993 | kilotonnes | 38.6116  | FAO estimate     |
| 4 | AFG              | Afghanistan | Gas-Diesel oil | 1994 | kilotonnes | 31.4465  | FAO estimate     |


###```python: Data Shape

```python
row, col=df.shape
print('Total number of observations/rows/entries:', row)
print('Total number of columns:', col)

row, col=df_clean.shape
print('\nTotal number of observations/rows/entries:', row)
print('Total number of columns:', col)
```
> **Output :**

```python
Total number of observations/rows/entries: 46131
Total number of columns: 14

Total number of observations/rows/entries: 46131
Total number of columns: 7
```
### Step-4: Data Structure

```python
df_clean.info()
```
> **Output :**

```python
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 46131 entries, 0 to 46130
Data columns (total 7 columns):
 #   Column            Non-Null Count  Dtype  
---  ------            --------------  -----  
 0   Area Code (ISO3)  46131 non-null  object 
 1   Area              46131 non-null  object 
 2   Item              46131 non-null  object 
 3   Year              46131 non-null  int64  
 4   Unit              46131 non-null  object 
 5   Value             46131 non-null  float64
 6   Flag Description  46131 non-null  object 
dtypes: float64(1), int64(1), object(5)
memory usage: 2.5+ MB
```python

### Step-5: Finding Missing Values

```python
df_clean.isnull().sum()
```
> **Output :**
```python
Area Code (ISO3)    0
Area                0
Item                0
Year                0
Unit                0
Value               0
Flag Description    0
dtype: int64
```
### Step-6: Summary Statistics

```python
df_clean.describe()
```
> **Output :**

|       | Year        |  Value      |
|-------|-------------|-------------|
| count | 46131       | 46131       |
| mean  | 1998.988814 | 863.132722  |
| std   | 13.111035   | 5274.730687 |
| min   | 1970        | 0           |
| 25%   | 1990        | 3.37075     |
| 50%   | 2000        | 21.4899     |
| 75%   | 2010        | 165.7289    |
| max   | 2019        | 197674.5593 |


### Step-7: Value Counts

```python
df_clean.Item.value_counts()
```
> **Output :**

```python
Motor Gasoline                       8756
Gas-Diesel oil                       8160
Liquefied petroleum gas (LPG)        7431
Fuel oil                             6418
Electricity                          6061
Coal                                 4304
Natural gas (including LNG)          3787
Gas-diesel oils used in fisheries     747
Fuel oil used in fisheries            467
Name: Item, dtype: int

```python
# unique values in each column
df_clean.nunique
> **Output :**

```python
Area Code (ISO3)      229
Area                  229
Item                    9
Year                   50
Unit                    1
Value               34024
Flag Description        3
dtype: int64
```
### Step-8: Check the Normality of Data

```python
df_clean['Item'].unique()
```
> **Output :**

```python
array(['Gas-Diesel oil', 'Motor Gasoline', 'Natural gas (including LNG)',
       'Coal', 'Electricity', 'Liquefied petroleum gas (LPG)', 'Fuel oil',
       'Gas-diesel oils used in fisheries', 'Fuel oil used in fisheries'],
      dtype=object)
```

```python
# groupby specific item and sum the values
df_clean.groupby(['Item','Value']).head()
```
> **Output :**

```python
1	AFG	Afghanistan	Gas-Diesel oil	1991	kilotonnes	188.5317	FAO estimate
2	AFG	Afghanistan	Gas-Diesel oil	1992	kilotonnes	47.9904	FAO estimate
3	AFG	Afghanistan	Gas-Diesel oil	1993	kilotonnes	38.6116	FAO estimate
4	AFG	Afghanistan	Gas-Diesel oil	1994	kilotonnes	31.4465	FAO estimate
...	...	...	...	...	...	...	...
46126	ZWE	Zimbabwe	Electricity	2015	kilotonnes	424.3909	International reliable sources
46127	ZWE	Zimbabwe	Electricity	2016	kilotonnes	213.9419	International reliable sources
46128	ZWE	Zimbabwe	Electricity	2017	kilotonnes	187.7450	International reliable sources
46129	ZWE	Zimbabwe	Electricity	2018	kilotonnes	218.3081	International reliable sources
46130	ZWE	Zimbabwe	Electricity	2019	kilotonnes	201.9786	FAO estimate
40787 rows × 7 columns
```

### Step-9: Plotting

```python
# Grouping the data by Item and Area and then calculating the mean and plotting the graph by top 10 countries
plt.figure(figsize = (15,10))
df_clean.groupby(['Item', 'Area']).mean()['Value'].sort_values(ascending = False).head(10).plot(kind = 'bar', color = 'grey')
plt.xlabel("Energy, Country", fontsize=14)
plt.ylabel("CO2 emissions - absolute number in kilotones ", fontsize=14)
plt.title("Top Ten Countries by Energy Type", fontsize = 18, loc='left', y=1.01  )
plt.xticks(rotation=45)
plt.show()
```


```python
df_clean.head()
```
> **Output :**

|   | Area Code (ISO3) | Area        | Item           | Year | Unit       | Value    | Flag Description |
|---|------------------|-------------|----------------|------|------------|----------|------------------|
| 0 | AFG              | Afghanistan | Gas-Diesel oil | 1990 | kilotonnes | 231.4918 | FAO estimate     |
| 1 | AFG              | Afghanistan | Gas-Diesel oil | 1991 | kilotonnes | 188.5317 | FAO estimate     |
| 2 | AFG              | Afghanistan | Gas-Diesel oil | 1992 | kilotonnes | 47.9904  | FAO estimate     |
| 3 | AFG              | Afghanistan | Gas-Diesel oil | 1993 | kilotonnes | 38.6116  | FAO estimate     |
| 4 | AFG              | Afghanistan | Gas-Diesel oil | 1994 | kilotonnes | 31.4465  | FAO estimate     |

```python
plt.figure(figsize = (20,10))
sns.barplot(x='Item', y='Value', data=df)
plt.show()
```
> **Output :**


```python
plt.figure(figsize = (20,10))
sns.boxplot(y='Value', data=df)
plt.show()
```
> **Output :**


```python
#Construct visualisation 
plt.figure(figsize = (20,10))
sns.countplot(x = "Item", data = df)

#customisation
plt.xlabel("Energy", fontsize=14)
plt.annotate('Source: https://www.fao.org/faostat/en/#data/GN', (0,-.3), xycoords ='axes fraction')
plt.title("Distribution Energy type", fontsize = 18, loc='left', y=1.01  )
plt.xticks(rotation=45)
plt.show()
```
> **Output :**



# Exploring Specific Region Data (Subcontinent)
In this section the data specifically for the subcontinent countries will be examined. the list of countries are as follows:

* Bangladesh,
* India,
* Pakistan


```
df_sub = df_clean[df_clean["Area"].isin(["India", "Pakistan", 'Bangladesh'])]
df_sub.head()
```
> **Output :**

```python
df_sub.shape
```
> **Output :**

```python
(1019, 7)
```

```python
PK_avg = df_sub[df_sub["Area"]=="Pakistan"]["Value"] 
IN_avg = df_sub[df_sub["Area"]=="India"]["Value"]
Bang_avg = df_sub[df_sub["Area"]=="Bangladesh"]["Value"]
```

```python
df_sub.describe()
```
> **Output :**

|       | Year        | Value       |
|-------|-------------|-------------|
| count | 1019        | 1019        |
| mean  | 1995.056919 | 5089.548264 |
| std   | 14.077065   | 19611.97113 |
| min   | 1970        | 0.0528      |
| 25%   | 1983        | 7.7898      |
| 50%   | 1995        | 185.0348    |
| 75%   | 2007        | 817.5375    |
| max   | 2019        | 197674.5593 |

```python
plt.figure(figsize = (15,10))
sns.barplot(x='Area', y='Value', data=df_sub)
plt.show()
```
> **Output :**


```python
df_sub = df_clean[df_clean["Area"].isin(["India", "Pakistan", 'Bangladesh'])]
df_sub.head()
```
> **Output :**

|      | Area Code (ISO3) | Area       | Item           | Year | Unit       | Value    | Flag Description               |
|------|------------------|------------|----------------|------|------------|----------|--------------------------------|
| 2915 | BGD              | Bangladesh | Gas-Diesel oil | 1972 | kilotonnes | 31.863   | International reliable sources |
| 2916 | BGD              | Bangladesh | Gas-Diesel oil | 1973 | kilotonnes | 38.2356  | International reliable sources |
| 2917 | BGD              | Bangladesh | Gas-Diesel oil | 1974 | kilotonnes | 149.7561 | International reliable sources |
| 2918 | BGD              | Bangladesh | Gas-Diesel oil | 1975 | kilotonnes | 168.8739 | International reliable sources |
| 2919 | BGD              | Bangladesh | Gas-Diesel oil | 1976 | kilotonnes | 178.4328 | International reliable sources |

```python
# Groupby Bangladesh and Item and plot the mean in horizontal bar chart
df_sub[df_sub["Area"]=="Bangladesh"].groupby("Item")["Value"].mean().plot(kind="barh", figsize=(15,8))
```
> **Output :**


```python
# Groupby India and Item and plot the mean
df_sub[df_sub["Area"]=="India"].groupby("Item")["Value"].mean().plot(kind="barh", figsize=(15,8))
```
> **Output :**


```python
# Groupby Pakistan and Item and plot the mean
df_sub[df_sub["Area"]=="Pakistan"].groupby("Item")["Value"].mean().plot(kind="barh", figsize=(15,8))
```
> **Output :**


```python
df_sub.groupby(['Area', 'Item'])['Value'].mean().unstack().plot(kind='barh', figsize=(15, 10))
```
> **Output :**


```python
plt.figure(figsize = (26,8))
sns.lineplot(x = "Year", y = "Value", data = df_sub)

#customisation
#plt.ylim(10,)
#sns.despine(top = True, right = True, left = False, bottom = False)
plt.title("Average energy usage for Subcontinent Countries", fontsize = 18, loc='left', y=1.01 )
plt.xlabel("Year", fontsize=14)
plt.ylabel("CO2 emissions - absolute number in kilotones ", fontsize=14)

plt.show()
```
> **Output :**




```python
# Contruct visualisation for india's energy usage increase over the years
plt.figure(figsize = (20,10))
sns.lineplot(x = "Year", y = "Value", data = df_sub[df_sub["Area"]=="India"])
plt.show()
```

