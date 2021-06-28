
# Kickstarting with Excel

## Overview of Project

### Purpose

In this project, the data of over 4000 crowdfunding projects is analyzed and visualized. Using Pivot table and charts, we can find the count of projects with different outcomes in various categories, date, and country. By visualizing the result, comparison accross categories and trends in any country are very obvious.

Also, in this project, I start to manage my project in GitHub, and try to complete a data analysis project from aquiring request to writing the closing report. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

According to a brief overview of the data, to find the Outcomes Based on Launch Date, the first step is to convert the date from a special version (UNIX timestamp) to a date format. Forumula used in CELL(T2) is =(((J2/60)/60/24)+DATE(1970,1,1)) , then extend to the whole column and format to DATE.

Since the date are grouped in months and are cross years, which means YEAR and DAY should be hidden.(And a YEAR column is already built up using YEAR()). I came up with two solutions:
1. colone a column: Cell(V2) = T2, extend to the whole column. Then format the column in 'Customed format', using "mmm" which means 3-letter month format;
2. an alternative way: Cell(V2) = TEXT(T2,"mmm").
Comparing the two, the first formula is a integer, having "year and day" info, and the second formula returns a text, discarding the "year and day" info. I chose the first one here. 

Insert a pivot table using default settings. Named the Sheet as Theater Outcomes by Launch Date. Drag fields into filters/columns/rows/values. That's easy by following the instruction. When dragging the new generated column "months" into rows, it has drill-down rows of Year and Quarter. 
![Year and Quarter Info](/resources/Yearquartermonth.png)
I could just remove these two, and get the correct result. Here's the point: when the years and quarters are needed by chance after this set up, it's easier to show them than using text-format month.(the solution 2 above)

Use the icon beside the colomn labels, I chose "sort Z to A" as a descending order. Then chose the whole table to insert a chart. Double click the chart, and all the settings are shown on the right side. There's also a green plus sign outside the right up corner of the chart, through which the chart elements can be selected or deselected by a click.
![Add chart title here](/resources/Chart_elements.png)

After all the editing, the chart is saved below:

![Theater Outcomes vs Launch Date](/resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

![Outcomes Based on Goals](/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered



## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

* According to the chart, the projects realated to theater are more launched in every Feburary, April, May, June, July, August, and October. 
* Within these 7 months, there are more successful projects launched in May, June, and July. 

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
