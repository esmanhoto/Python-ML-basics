# Pandas

To start it all:
import pandas as pd

### 1. Main Datatypes creation

#### \* Series (1-dim)

    series = pd.Series(["BMW", "Toyota", "Honda"])
    colours = pd.Series(["Red", "Blue", "white"])

#### \* DataFrames (2-dim)

    car_data = pd.DataFrame({"Car make": series, "Colours": colours})

### 2. Importing and Exporting data

    car_sales = pd.read_csv("car-sales.csv")
    car_sales.to_csv("exported-car-sales.csv", index=False)
    #index = False -> so it uses the same indexes.

`index = False` -> so it uses the same indexes.

### 3. Describing data

- df.dtypes => columns and types of each column

```
car_sales.dtypes
Make object
Colour object
Odometer (KM) int64
Doors int64
Price object
dtype: object
```

- df.columns => columns names

```
car_sales.columns
Index(['Make', 'Colour', 'Odometer (KM)', 'Doors', 'Price'], dtype='object')
```

- df.describe() => count, mean, std, min and quartiles for numerical columns

```
car_sales.describe()
	    Odometer (KM)	Doors
count	10.000000	    10.000000
mean	78601.400000	4.000000
std	    61983.471735	0.471405
min	    11179.000000	3.000000
25%	    35836.250000	4.000000
50%	    57369.000000	4.000000
75%	    96384.500000	4.000000
max	    213095.000000	5.000000
```

- df.info() => columns, types, indexes and memory usage

```
car_sales.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 10 entries, 0 to 9
Data columns (total 5 columns):
 #   Column         Non-Null Count  Dtype
---  ------         --------------  -----
 0   Make           10 non-null     object
 1   Colour         10 non-null     object
 2   Odometer (KM)  10 non-null     int64
 3   Doors          10 non-null     int64
 4   Price          10 non-null     object
dtypes: int64(2), object(3)
memory usage: 528.0+ bytes
```

- df.mean() => mean of numeric columns
- df.sum() => sum/concatenation column values
- len(df) => length of the dataFrame

### 4. Viewing and Selecting Data

#### Viewing

- df.head(n) => first 'n' rows of the dataFrame, default is 5
- df.tail(n) => last 'n' rows of the dataFrame, default is 5
- df.loc[i] => displays rows with index 'i'
- df.iloc[i] => display 'i-th' row

#### Selecting

- df["column_name"] | df.column_name (works best with names with no empty spaces)

#### Filtering columns

- df[df.column == condition]
