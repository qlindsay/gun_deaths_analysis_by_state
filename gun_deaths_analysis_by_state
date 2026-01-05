# Import Packages 

import pandas as pd 
import numpy as np 
import matplotlib.pyplot as plt
import pandasql as sql

# Import Dataset 
df = pd.read_csv('../input/us-gun-deaths-by-county-19992019/gun_deaths_us_1999_2019.csv', index_col = 0)

# Remove all NaN (not a number) values and replace them with 0
df = df.fillna(0)

# Show dataframe 
df.head()

# Question 1: What is the population by state?

# Using SQL to pull in the population of each state 

df_pop_state = sql.sqldf("""SELECT DISTINCT(State_Name), Population
FROM df
GROUP BY State_Name
ORDER BY Population ASC""")

# Show dataframe
df_pop_state.head()

# Show the population by state in a bar chart
df_pop_state.plot.bar(x = "State_Name", y = "Population", title = "Population by State", 
                      xlabel = "State Name", ylabel = "Population", figsize = (20, 5))

# Question 2: What is the number of deaths by state?

# Using SQL to pull the number of deaths in each state

df_death_state = sql.sqldf("""SELECT DISTINCT(State_Name), Deaths
FROM df
GROUP BY State_Name
ORDER BY Deaths ASC""")

# Show Dataframe
df_death_state.head()

# Show the deaths by state in a bar chart
df_death_state.plot.bar(x = "State_Name", y = "Deaths", title = "Deaths by State",
                       xlabel = "State Name", ylabel = "Total Deaths", color= "red", figsize = (20, 5))
                       
# Question 3: Based on the two datasets (Population by State and Deaths by State) above, do you see a positive or 
negative correlation between population and deaths? Show the correlation between the two columns.

# Import Packages 

import pandas as pd 
import numpy as np 
import matplotlib.pyplot as plt
import pandasql as sql

# Import Dataset 
df = pd.read_csv('../input/us-gun-deaths-by-county-19992019/gun_deaths_us_1999_2019.csv', index_col = 0)

# Remove all NaN (not a number) values and replace them with 0
df = df.fillna(0)

# Show the pairwise correlation of all columns in df
df.corr()

# Show the correlation between Deaths and Population
df.Deaths.corr(df.Population).round(2)

# Conclusion: Based on my analysis, there is in fact a strong positive correlation between Deaths and Population, showing a value of 0.89 or 89%.
Therefore, as the population within a state increases, you can expect the number of deaths to increase as well. This can be due to various reasons which are 
outside the scope of this dataset.
