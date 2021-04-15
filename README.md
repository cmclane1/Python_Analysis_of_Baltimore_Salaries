# Python Analysis of Baltimore Salaries
## Background
Python is a powerful tool for data analysis. It is a robust programming language that uses interpratation instead of compiling. This makes its syntax more leaniant than other compiled languages such as Java, making python more approachable. A number of libraries such as Matplotlib, Plotly, Numpy, and Pandas are useful tools for creating and manipulating arrays of data then creating visualizations.
Baltimore City as with all major cities, employs a large number of employees for various activities such as policing, teaching, and administrating. Because these jobs are all paid for by the public (taxpayer) the city makes the information about who it employs and for how much publicly available in a data set. I previously tried to work with this data set using excel on my laptop but it crashed several times and I gave up. This highlights a particular strength of python over spreadsheet software. Because Python is a programming language it can operate on the data set on a lower level, and is thus less taxing on the software, which is less taxing on your computing. 
  
## Business Question
What is the distribution of annual salaries of employees of Baltimore City?

## Analysis
It differs by quite a lot. The average income of the Baltimore is $23,000 (2nd percentile), while the average in Bristol county is $38,000 (76th percentile), 55% higher. The histogram below shows the distribution of the different income tracts. This is a surprising and significant difference, I decided to check some other metrics for other indicators and education was quite different. Looking at the same groups Baltimore has a high school graduation rate of 73% (12th percentile), and college graduation rate of 12% (19th percentile). While Bristol has a high school graduation rate of 88% (92nd percentile), and college graduation rate of 33% (96th percentile). Both metrics clearly show better outcomes for Bristol but it is interesting that both rank higher in education than in income. 

Baltimore needs to examine why the education rates are so low and try and improve them, especially for low-income students. While Bristol is doing well, it needs to focus on translating its high rate of education into a similarly high income. These places are not similar in demographics or size. They require very different solutions to improve their outcomes and Bristol is far further along than Baltimore is in having good outcomes. An interesting theory I have is that Bristol has a much higher rate of Catholics, and growing up I went to one of many Catholic elementary and high schools, it should be investegated what effect religion has on the high school graduation rate.

![alt text](https://github.com/cmclane1/Python_Analysis_of_Baltimore_Salaries/blob/main/Annual%20Salary%20of%20Baltimore%20Employees.png)

## Step by Step Walkthrough
Using google colab as a coding environment I imported the various libraries mentioned in the background section. After moving a csv of the data to github I imported that into a pandas dataframe through the raw link on github. I then practiced a form of cleaning up the data by unifing a persons name to be their full name. I ended up not using this field because I pivoted on what I wanted to analyze but I left this in because I still think it was a good exercise in dataframe manipulation. Taking this dataframe I used the pivot function to move the fiscal year from a single column to each year having its own column and associated values. This created a large data frame with a lot of empty values because each row only had one value from one year. So using a for loop I created a temporary data fram for each year, reset the index, and then joined them together for a final dataframe. I repeated this process for the gross pay and pay variance where payvariance is the difference between annual salary and gross pay. 
  
## Links to Sources
[Analysis](https://github.com/cmclane1/comparing-baltimore-bristol-county-household-income/blob/main/Baltimor-Bristol-Analysis.xlsx)

[Data](https://data.baltimorecity.gov/datasets/baltimore-employee-salaries/data)

[Baltimore City Data](https://data.baltimorecity.gov/datasets/baltimore-employee-salaries/data)
