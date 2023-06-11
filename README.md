# Crime in India: Exploratory Data Analysis

This project contains exploratory analyses of two National Crime Records Bureau
(NCRB) datasets. The notebooks use pandas, NumPy, Matplotlib, and Seaborn to
summarize crime trends, crime categories, geography, age, and sex.

## Datasets

### 1. District-wise crimes committed under IPC, 2001–2012

Source file: [`datasets/01_District_wise_crimes_committed_IPC_2001_2012.csv`](datasets/01_District_wise_crimes_committed_IPC_2001_2012.csv)

Analysis notebook: [`crimes_in_india.ipynb`](crimes_in_india.ipynb)

- 9,017 records covering 2001–2012.
- 35 states/union territories and 808 districts.
- 33 columns, including location, year, individual IPC categories, and
  `TOTAL IPC CRIMES`.

### 2. Persons arrested by age and sex in 19 metropolitan cities, 2019

Source file: [`datasets/NCRB_CII-2019_Table_19B.2.csv`](datasets/NCRB_CII-2019_Table_19B.2.csv)

Analysis notebook: [`eda.ipynb`](eda.ipynb)

- 19 city records were analyzed after removing the `TOTAL CITIES` summary row.
- The dataset describes persons arrested, not reported crimes.
- Arrests are grouped into juveniles and four adult age bands, with male,
  female, and total counts.
- The analysis includes 19 cities; it should not be interpreted as a complete
  national total.

## Findings

### IPC crime trends, 2001–2012

- The dataset contains **47,881,308 total IPC crimes**.
- Reported crime increased overall across the period. **2012** was the peak
  year with **4,774,376 cases**, while **2003** was the lowest with
  **3,432,240 cases**.
- The notebook reports an average annual growth rate of **2.80%** and only
  **two years with a year-over-year decrease**.
- **Madhya Pradesh** had the highest total crime count at **4,827,540**.
  The notebook identifies **Andhra Pradesh** as having the highest average
  crime count per district.
- The most frequent categories were:
  1. **Other IPC crimes** - 19,605,658
  2. **Theft** - 7,001,060
  3. **Hurt/grievous hurt** - 6,743,752
- The notebook’s grouped comparison found **economic crimes (15,958,792)**
  substantially higher than **violent crimes (3,316,380)**, a ratio of about
  **4.8:1**.
- Women-related crimes represented approximately **9.46%** of total crimes in
  the notebook’s analysis.
- Crime counts are strongly right-skewed (reported skewness **7.95**), meaning
  a relatively small number of district/category combinations account for a
  large share of observations.

### Arrests by age and sex, 2019

Across the 19 analyzed cities, the notebook reports **434,769 persons
arrested**:

- **Male:** 410,850
- **Female:** 23,919
- Male-to-female ratio: **17.18:1**

The adult **18–30 age group** had the largest number of arrests:

| Age group | Male | Female | Total |
|---|---:|---:|---:|
| Juveniles | 7,790 | 16 | 7,806 |
| 18–30 | 201,422 | 8,432 | 209,854 |
| 30–45 | 142,365 | 10,451 | 152,816 |
| 45–60 | 54,038 | 4,347 | 58,385 |
| 60 and above | 5,235 | 673 | 5,908 |

The highest total arrest counts were reported for:

1. **Delhi** - 99,086
2. **Chennai** - 58,508
3. **Mumbai** - 54,543
4. **Ahmedabad** - 34,952
5. **Bengaluru** - 28,358

## Interpretation notes

- Higher counts do not necessarily indicate higher underlying crime risk.
  Population size, reporting practices, police activity, city coverage, and
  changes in classification can all affect the observed values.

## Running the notebooks

From the project directory, install the notebook dependencies and launch
Jupyter:

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook
```

Run [`crimes_in_india.ipynb`](crimes_in_india.ipynb) for the 2001–2012 IPC
analysis and [`eda.ipynb`](eda.ipynb) for the 2019 arrest analysis.