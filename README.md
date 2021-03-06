# Kickstarter-Analysis
## Overview of Project
### The purpose of this project was to gain familiarity with using Microsoft Excel to analyze large sets of data.  It was done as part of my Week 1 project for my DU coding bootcamp.  My work with the data set included:
* filtering data, conditional formatting, and freezing panes - to more easily see and group the data;
* finding averages and using UNIX timestamps;
* pivot tables and splitting data into multiple columns;
* Vlookup functions
* statistics: 
  - central tendancy - mean, mode, median;
  - measureing spread - standard deviation, IQR, outliers
  - data visualization - box plots, line graphs, etc
* and COUNTIF functions
## Analysis and Challenges
### Analysis
For the first deliverable, "Theather Outcomes by Launch Date", I added a new column and used the Year function to extract the year from the "Date Created Conversion" column, which was generated from the UNIX codes. 

![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Year%20Function.png)

I then created a pivot table from the updated worksheet, and set up the table as below.  The table has been set up to show all years, filtering "theater", showing only "successful, Canceled, and Failed" projects, and sorted to display the outcomes in the table in reverse alphabetical order. I also added a table with percents of outcomes.

![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Theater_Outcomes_vs_Launch%20averages.png)

For the second deliverable, "Outcomes based on Goals", I created a table with the funding ranges in the fist column and then used the COUNTIF function linked to the main data set sheet to populate out the table.  The table included outcome criteria: successful, failed, and canceled; monitary goal ranges, and filtered for plays only.  An example of the COUNTIF code is below.

=COUNTIFS('Kickstarter (modified)'!$F:$F, "failed", 'Kickstarter (modified)'!$D:$D, ">=1000", 'Kickstarter (modified)'!$D:$D, "<=4999", 'Kickstarter (modified)'!$S:$S, "plays")

I generated corresponding percentages, and then used those percentages to create a line graph.  I also generated a bar graph for all the funding ranges and all 3 outcomes.

![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Outcomes%20of%20Plays%20by%20Funding%20Goals%20screen.png)

### Challenges
For me, keeping track of what I was actually doing, or what a graph was actually telling me, was difficult.  For example, a graph could be generated from data in a sheet, but that data was copied from a different sheet after applying filters.  Or the graph might be generated using data or formulas that auto-update the graph as data changes.  Since we would make graphs, then go and clear filters, reset the data set, or change other minor things, sometimes, those changes would result in changed graphs, and updated trends.  This is a huge problem, per say, but something that needs to be remembered.  Saving graphs with clear titles, labels, or even descriptions, would be helpful.
Also, buidling complex formulas that reference cells, columns, or tables in other sheets, can be tricky.  This was definately the case for me with the COUNTIF functions, when multiple creiterias were being asked for.
## Results
### What are two conclusions you can draw about the Theater Outcomes by Launch Date? 
At first glance, it seems that theater kickstarters launched in the summer are the substantially more successful in comparison to the rest of the year.  The graph indicates that May is the most successful, followed by June, then July, with success rates of 66.9%, 65.4%, and 63.0%, respectively.  If one lookes at the graph alone, they might conclude that kickstarters launched between May-July, are exceedingly more successful.  However, if you calculate out the percent success (successful campaigns divided by total campaigns), it becomes obvious, that most months are similarly successful.  

The average percent success is 60.6% with a standard deviation of 4.2%, yielding 56.4%-64.8% success rate +/- 1 standard deviation.  December is the only month that falls outside this range, with a rate of 49.3% success, which is in the -3 standard deviation range.  In reality, May and June are the only two months that are higher than the 1 standard deviation range mentioned above, but this is barely the case, espcecially for June. 

![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Theater_Outcomes_vs_Launch.png)
![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Theater_Outcomes_vs_Launch%20table.png)

So yes, if Louise can arrange to launch her kickstarter in May, followed by June, she will be more likely to succeed than any other month; but in reality, her chance of success is pretty even through out the year, excluding December.

### What can you conclude about the Outcomes based on Goals?
If we look at the line graph generated by the percentage data, "Outcomes Based on Goal", we see that plays with goals between $0-999, and $1,000-4,999 were aproximately %70 successful, %75.8 and %72.7 respectively. 
If we generate a bar chart of the outcomes based on goal, we confirm out initial findings.  Looking at the table with the calculated data, we can see 2 immediate things:
1. Most of the kickstarters that were playes, regardless of outcomes, had funding goals under $15,000.  To be more precise, 91.8% of all plays had funding goals of less than or equal to $14,999; and 84.9% of all plays had goals of less than or equal to $9,999.  If we use a bar graph to view this data, we see that the data is skewed right, with the majority of plays having low funding goals.  This is not clearly evident in the line graph, but it makes sense since fewer people are going to try to fund expensive projects, and few projects requiring large expense, will be more likely to fail.
2. Plays with funding goals less than $5,000 had a success rate of 73.5%, with play funding goals between $1,000-$4,999 having the most projects, and being 72.7% successful.

![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Outcomes%20of%20Plays%20by%20Funding%20Goals.png)
![This is an image](https://github.com/bartblack13/ExcelChallenge-bblack/blob/main/Outcomes_vs_Goals.png)

### What are some limitations of this dataset?
There are a lot of variables that might be worth investigating, that are not represented in the data set.  For example grouping plays according to genres, like comedy or romance, etc.  These things could shed light on other trends that might give Luise more insight on how successful she may be.  The other limitaion of this data set is the numbers of kickstarters per group, for example by country.  Some groupings resulting from the sorting had very low numbers.  If Louise was looking at launching a kickstarter in a different country, she might not have enough data points to make an informed decision.

### What are some other possible tables and/or graphs that we could create?
I created a secondary table for the outcomes by launch date, which calculated out percentages of successful, failed, and canceled campaigns, along with average success and standard deviation.  This was useful to see what the line graph hides.  The pitfall with the line graph alone is that total campaign numbers increase during the summer months, when we see the "spike" in success, creating an illusion that their is almost double the success in comparison to March, for example.  But in rality, using a table to calculate out the percents of success shows the flaw in the graph.  

The table was informative, but had a lot of numbers to read, especially if the data was going to be presented in a presentation where time might be limited.  Having a visual representation of the data would be advantageous.  At minimum, updating the line graph to show percents for each outcome would be beneficial, as would a box plot fot the Theater Outcomes by date.  

Normalization of data is an important thing in data analysis, as it sets the perspective of the conclusions made through the results.

A bar graph, although not required, was useful for Outcomes Based on Goals data and seeing what funding bracket had the majority of plays.

**Summary Conclusion:** If Luise launches her kickstarter campaign in May (66.9% success) and does not exceed the goal of $4999 (74.3% success), then she should have a combined probability of success of 49.1% (0.734 x 0.669 = 0.491)

    

