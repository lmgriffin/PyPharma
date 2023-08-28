# PyPharma

CODE PULLED FROM CLASS EXAMPLES

Module 5 (Day 3, Activity 2)
quartiles = temperatures.quantile([.25,.5,.75])
lowerq = quartiles[0.25]
upperq = quartiles[0.75]
iqr = upperq-lowerq

print(f"The lower quartile of temperatures is: {lowerq}")
print(f"The upper quartile of temperatures is: {upperq}")
print(f"The interquartile range of temperatures is: {iqr}")
print(f"The the median of temperatures is: {quartiles[0.5]} ")

lower_bound = lowerq - (1.5*iqr)
upper_bound = upperq + (1.5*iqr)
print(f"Values below {lower_bound} could be outliers.")
print(f"Values above {upper_bound} could be outliers.")


# The second example again looks at the LAX temperature data set and computes quantiles
temperature_df = pd.read_csv('../Resources/lax_temperature.csv')
temperatures = temperature_df['HourlyDryBulbTemperature']

fig1, ax1 = plt.subplots()
ax1.set_title('Temperatures at LAX')
ax1.set_ylabel('Temperature (°F)')
ax1.boxplot(temperatures)
plt.show()

---------------------------------------------------------------------
Module 5 (Day 2, Activity 4)
# Create a bar chart based off of the group series from before
count_chart = count_road_types.plot(kind='bar', figsize=(6,8))

# Set the xlabel and ylabel using class methods
count_chart.set_xlabel("Road Type")
count_chart.set_ylabel("Number of Accidents")

plt.show()
plt.tight_layout()

----------------------------------------------------------------------
Module 5 (Day 2, Activity 2)
# Set x axis and tick locations
x_axis = np.arange(len(rain_df))
tick_locations = [value for value in x_axis]

# Create a list indicating where to write x labels and set figure size to adjust for space
plt.figure(figsize=(20,4))
plt.bar(x_axis, rain_df["Inches"], color='r', alpha=0.5, align="center")
plt.xticks(tick_locations, rain_df["State"], rotation="vertical")
plt.show()







Prepare the Data
Run the provided package dependency and data imports, and then merge the mouse_metadata and study_results DataFrames into a single DataFrame.

Display the number of unique mice IDs in the data, and then check for any mouse ID with duplicate time points. Display the data associated with that mouse ID, and then create a new DataFrame where this data is removed. Use this cleaned DataFrame for the remaining steps.

Display the updated number of unique mice IDs.

Generate Summary Statistics
Create a DataFrame of summary statistics. Remember, there is more than one method to produce the results you're after, so the method you use is less important than the result.

Your summary statistics should include:

A row for each drug regimen. These regimen names should be contained in the index column.

A column for each of the following statistics: mean, median, variance, standard deviation, and SEM of the tumor volume.

Create Bar Charts and Pie Charts
Generate two bar charts. Both charts should be identical and show the total total number of rows (Mouse ID/Timepoints) for each drug regimen throughout the study.

Create the first bar chart with the Pandas DataFrame.plot() method.

Create the second bar chart with Matplotlib's pyplot methods.

Generate two pie charts. Both charts should be identical and show the distribution of female versus male mice in the study.

Create the first pie chart with the Pandas DataFrame.plot() method.

Create the second pie chart with Matplotlib's pyplot methods.

Calculate Quartiles, Find Outliers, and Create a Box Plot
Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Then, calculate the quartiles and IQR, and determine if there are any potential outliers across all four treatment regimens. Use the following substeps:

Create a grouped DataFrame that shows the last (greatest) time point for each mouse. Merge this grouped DataFrame with the original cleaned DataFrame.

Create a list that holds the treatment names as well as a second, empty list to hold the tumor volume data.

Loop through each drug in the treatment list, locating the rows in the merged DataFrame that correspond to each treatment. Append the resulting final tumor volumes for each drug to the empty list.

Determine outliers by using the upper and lower bounds, and then print the results.

Using Matplotlib, generate a box plot that shows the distribution of the final tumor volume for all the mice in each treatment group. Highlight any potential outliers in the plot by changing their color and style.

hint: All four box plots should be within the same figure. Use this Matplotlib documentation pageLinks to an external site. for help with changing the style of the outliers.

Create a Line Plot and a Scatter Plot
Select a single mouse that was treated with Capomulin, and generate a line plot of tumor volume versus time point for that mouse.

Generate a scatter plot of mouse weight versus average observed tumor volume for the entire Capomulin treatment regimen.

Calculate Correlation and Regression
Calculate the correlation coefficient and linear regression model between mouse weight and average observed tumor volume for the entire Capomulin treatment regimen.

Plot the linear regression model on top of the previous scatter plot.

Requirements
Prepare the Data (20 points)
The datasets are merged into a single DataFrame. (6 points)
The number of mice are shown from the merged DataFrame. (2 points)
Each duplicate mice is found based on the Mouse ID and Timepoint. (6 points)
A clean DataFrame is created with the dropped duplicate mice. (4 points)
The number of mice are shown from the clean DataFrame. (2 points)
Generate Summary Statistics (15 points)
The mean of the tumor volume for each regimen is calculated using groupby. (2 points)
The media of the tumor volume for each regimen is calculated using groupby. (2 points)
The variance of the tumor volume for each regimen is calculated using groupby. (2 points)
The standard deviation of the tumor volume for each regimen is calculated using groupby. (2 points)
The SEM of the tumor volume for each regimen is calculated using groupby. (2 points)
A new DataFrame is created with using the summary statistics. (5 points)
Create Bar Charts and Pie Charts (15 points)
A bar plot showing the total number of timepoints for all mice tested for each drug regimen using Pandas is generated. (4.5 points)
A bar plot showing the total number of timepoints for all mice tested for each drug regimen using pyplot is generated. (4.5 points)
A pie plot showing the distribution of female versus male mice using Pandas is generated. (3 points)
A pie plot showing the distribution of female versus male mice using pyplot is generated. (3 points)
Calculate Quartiles, Find Outliers, and Create a Box Plot (30 points)
A DatFrame that has the last timepoint for each mouse ID is created using groupby. (5 points)
The index of the DataFrame is reset. (2 points)
Retrieve the maximum timepoint for each mouse. (2 points)
The four treatment groups, Capomulin, Ramicane, Infubinol, and Ceftamin, are put in a list. (3 points)
An empty list is created to fill with tumor volume data. (3 points)
A for loop is used to display the interquartile range (IQR) and the outliers for each treatment group (10 points)
A box plot is generated that shows the distribution of the final tumor volume for all the mice in each treatment group. (5 points)
Create a Line Plot and a Scatter Plot (10 points)
A line plot is generated that shows the tumor volume vs. time point for one mouse treated with Capomulin. (5 points)
A scatter plot is generated that shows average tumor volume vs. mouse weight for the Capomulin regimen. (5 points)
Calculate Correlation and Regression (10 points)
The correlation coefficient and linear regression model are calculated for mouse weight and average tumor volume for the Capomulin regimen. (10 points)
