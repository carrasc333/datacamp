## Creating and Visualizing DataFrames

Creating and Visualizing DataFrames

### Which avocado size is most popular? (Bar Graph)

```
# Import matplotlib.pyplot with alias plt
import matplotlib.pyplot as plt

# Look at the first few rows of data
print(avocados.head())

# Get the total number of avocados sold of each size
nb_sold_by_size = avocados.groupby('size')['nb_sold'].sum()

# Create a bar plot of the number of avocados sold by size
nb_sold_by_size.hist()

# Show the plot
nb_sold_by_size.plot(kind="bar")
plt.show()

```

### Changes in sales over time (Line Plot)

```
# Import matplotlib.pyplot with alias plt
import matplotlib.pyplot as plt

# Get the total number of avocados sold on each date
nb_sold_by_date = avocados['date'].sum(axis="index")

# Create a line plot of the number of avocados sold by date
nb_sold_by_date = avocados.groupby("date")["nb_sold"].sum()

# Show the plot
nb_sold_by_date.plot(kind="line")
plt.show()

```

### Avocado supply and demand (scatter plot)

```
# Scatter plot of avg_price vs. nb_sold with title
avocados.plot(kind='scatter', x='nb_sold', y='avg_price', title="Number of avocados sold vs. average price")

# Show the plot
plt.show()

```

### Price of conventional vs. organic avocados (multiple plots)

```
# Modify bins to 20
avocados[avocados["type"] == "conventional"]["avg_price"].hist(alpha=0.5, bins=20)

# Modify bins to 20
avocados[avocados["type"] == "organic"]["avg_price"].hist(alpha=0.5, bins=20)

# Add a legend
plt.legend(["conventional", "organic"])

# Show the plot
plt.show()

```

### Finding missing values (Missing Values)

```
# Import matplotlib.pyplot with alias plt
import matplotlib.pyplot as plt

# Check individual values for missing values
print(avocados_2016.isna())

# Check each column for missing values
print(avocados_2016.isna().any())

# Bar plot of missing values by variable
avocados_2016.isna().sum().plot(kind='bar')

# Show plot
plt.show()

```
### Removing missing values (remove rows with missing values)

```
# Remove rows with missing values
avocados_complete = avocados_2016.dropna()

# Check if any columns contain missing values
print(avocados_complete.isna().any())

```

### Replacing missing values (with 0)

```
# List the columns with missing values
cols_with_missing = ["small_sold", "large_sold", "xl_sold"]

# Create histograms showing the distributions cols_with_missing
avocados_2016[cols_with_missing].plot(kind='hist')

plt.show()

# Fill in missing values with 0
avocados_filled = avocados_2016.fillna(0)

# Create histograms of the filled columns
avocados_filled[cols_with_missing].hist()

# Show the plot
plt.show()

```
