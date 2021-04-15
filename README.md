# Python Analysis of Baltimore Salaries
## Background
Python is a powerful tool for data analysis. It is a robust programming language that uses interpratation instead of compiling. This makes its syntax more leaniant than other compiled languages such as Java, making python more approachable. A number of libraries such as Matplotlib, Plotly, Numpy, and Pandas are useful tools for creating and manipulating arrays of data then creating visualizations.
Baltimore City as with all major cities, employs a large number of employees for various activities such as policing, teaching, and administrating. Because these jobs are all paid for by the public (taxpayer) the city makes the information about who it employs and for how much publicly available in a data set. I previously tried to work with this data set using excel on my laptop but it crashed several times and I gave up. This highlights a particular strength of python over spreadsheet software. Because Python is a programming language it can operate on the data set on a lower level, and is thus less taxing on the software, which is less taxing on your computing. 
  
## Business Question
What is the distribution of annual salaries of employees of Baltimore City, by fiscal year?

## Analysis
Using the statistics table we can see a lot of interesting results. The average salary has decreased notably a few times. In FY2013 and FY2014 the average salary is substantially lower. However this is likely because a lot of low salaried employees were hired specifically for this year. You can see in the graph further down that there is a large part of these two years around $11k where it is a flat line, and it is these people that offset those two years further to the right (more employees). A better way to examine this mean is to only compare employees who were hired for the same job for multiple years, which is an order of magnitude harder analysis but would lead to mor significant results

![alt text](https://github.com/cmclane1/Python_Analysis_of_Baltimore_Salaries/blob/main/Stats_table_Bmore_salaries.png)

The shape of the graph below is really interesting and reveals a disparity that exists in the city's employees. The first part of the line, until about $80k, is quite linear. Meaning that there are a similar amount of people making every salary. However at the end the graph shoots upward quite aggressively, showing that there a small select number of employees who are making many times what others are. A numerical example of this is that the 75 percentile is around $70k for each year, while the highest paid person is making $240k more than three times that. While the mean is around $45k showing that pay sharply increases as employees reach the top. Lastly the right or leftness of each curve shows how many people were employed that year.

![alt text](https://github.com/cmclane1/Python_Analysis_of_Baltimore_Salaries/blob/main/Annual%20Salary%20of%20Baltimore%20Employees.png)

## Step by Step Walkthrough
Using google colab as a coding environment I imported the various libraries mentioned in the background section. After moving a csv of the data to github I imported that into a pandas dataframe through the raw link on github. I then practiced a form of cleaning up the data by unifing a persons name to be their full name. I ended up not using this field because I pivoted on what I wanted to analyze but I left this in because I still think it was a good exercise in dataframe manipulation. Taking this dataframe I used the pivot function to move the fiscal year from a single column to each year having its own column and associated values. This created a large data frame with a lot of empty values because each row only had one value from one year. So using a for loop I created a temporary data fram for each year, reset the index, and then joined them together for a final dataframe. I repeated this process for the gross pay and pay variance where payvariance is the difference between annual salary and gross pay. 
  
## Conclusions
Pay in Baltimore city is heavily skewed towards the top percentages of employees. Pay does not vary that much from year to year (given the shape and magnitude of the curves are similar) but the raw number of employees does vary by a lot (given by the position of the curve on the x-axis).
  
## Links to Sources
[Analysis](https://github.com/cmclane1/comparing-baltimore-bristol-county-household-income/blob/main/Baltimor-Bristol-Analysis.xlsx)

[Data](https://github.com/cmclane1/Python_Analysis_of_Baltimore_Salaries/blob/main/Baltimore_Employee_Salaries%20(1).csv)

[Baltimore City Data](https://data.baltimorecity.gov/datasets/baltimore-employee-salaries/data)
