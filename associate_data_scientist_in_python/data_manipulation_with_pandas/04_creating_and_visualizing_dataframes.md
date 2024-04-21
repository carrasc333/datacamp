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