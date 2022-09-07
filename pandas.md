# Pandas

To start it all:
import pandas as pd

### Main Datatypes creation

#### Series (1-dim)

```
series = pd.Series(["BMW", "Toyota", "Honda"])
colours = pd.Series(["Red", "Blue", "white"])
```

#### DataFrames (2-dim)

    car_data = pd.DataFrame({"Car make": series, "Colours": colours})

### Importing and Exporting data

    car_sales = pd.read_csv("car-sales.csv")
    car_sales.to_csv("exported-car-sales.csv", index=False)

`index = False` so it uses the same indexes.

### Describing data

    df.dtypes
