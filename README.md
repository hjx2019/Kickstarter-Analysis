
# Kickstarting with Excel

## Overview of Project

### Purpose

In this project, the data of over 4000 crowdfunding projects is analyzed and visualized. Using Pivot table and charts, we can find the count of projects with different outcomes in various categories, date, and country. By visualizing the result, comparison accross categories and trends in any country are very obvious.

Also, in this project, I start to manage my project in GitHub, and try to complete a data analysis project from aquiring request to writing the closing report. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

1. **Convert Date:**
According to a brief overview of the data, to find the Outcomes Based on Launch Date, the first step is to convert the date from a special version (UNIX timestamp) to a date format. Forumula used in CELL(T2) is _=(((J2/60)/60/24)+DATE(1970,1,1))_ , then extend to the whole column and format to DATE.

2. **Find the MONTH:**
Since the requirement in output of date are grouped by months and are cross years, which means YEAR and DAY cannot be seen.(And a YEAR column is already built up using YEAR()). I came up with two solutions:
   - same value, different format: Cell(V2) = T2, extend to the whole column; Then format the column in 'Customed format', using "mmm" which means 3-letter month format;
   - convert the value: Cell(V2) = TEXT(T2,"mmm").
> Comparing the two, the first formula keeps the "year and day" info, and the second formula returns a text, discarding the "year and day" info. I chose the first one here. 

3. **Generate Pivot table:**
Insert a pivot table using default settings. Named the Sheet as Theater Outcomes by Launch Date. Drag fields into filters/columns/rows/values. That's easy by following the instruction. 

4. **Modify the display of MONTH:**
When dragging the new generated column "months" into rows, it has drill-down rows of Year and Quarter. By removing these two fields, I got the correct result. 

![Year and Quarter Info](/resources/Yearquartermonth.png)

>Here's the point: when the years and quarters are needed by chance after this set up, it's easier to show them than using text-format month.(the 2nd solution in step 2)

5. **Editing the Visualization - Line Chart:**
Use the icon beside the colomn labels, I chose "sort Z to A" as a descending order. Then chose the whole table to insert a chart. Double click the chart, and all the settings are shown on the right side. 
To edit the elements of the chart, there's a green plus sign outside the right up corner of the chart, through which the chart elements can be selected or deselected by a click.

![Add chart title here](/resources/Chart_elements.png)

6. **Result of deliverable 1:**
After all the editing, the chart is saved below:

![Theater Outcomes vs Launch Date](/resources/Theater_Outcomes_vs_Launch.png)

---
### Analysis of Outcomes Based on Goals

1. **Aquiring the titles:**
Copy the column titles into Excel, paste(_value only_) in any cell; keep the cells selected and copy again, then paste(_Transpose_) in Cell(A1). Since the row names are shown in a picture, type in the row names in Column A. 

2. **Dive into COUNTIFS():**
Starting from Cell(B2) _=COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F,"successful")_ and auto fill the whole column, then change the formula one by one. When the whole column is modified, drag and extend to the second and Third Column. Modify the criteria of Outcomes. To check it using _Formulas - show formulas_. 

![Check Formula](/resources/showformulas.png)

3. **Input from Office hour:** I know that I missed the subcategory of "plays", and I could use find/replace. 

![finde and replace](/resources/replace.png)

4. **Calculate the Total Count and Ratio:** Using the sum() formula to get the total count of projects. Then use count of each outcomes devided by the total to get the ratio. Then Format the ratio by click the "%" sign.

![sum and ratio](/resources/sumratio.png)

5. **Insert Line-Chart:** Select all data and insert the line-chart. Click the Design->Select data. 

![Outcomes Based on Goals](/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered

* In deliverable 2, double check the formula needs extra time. But the "show formulas" really helps. 
* Also in this one, the line chart didn't come automatically, because the numbers of the first 4 columns are integers and the last 3 columns are ratios which are less than 1. In this case, I need to modify the rows and columns manually. I also tested two other ways that works well: 1 hide colomn B:D; 2 hold Ctrl and select columns. They don't need extra data editing.


## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

  * According to the chart, the projects realated to theater are more launched in every Feburary, April, May, June, July, August, and October. Which means that other months are low season of project launching.
  * Within these 7 months, there are more successful projects launched in May, June, and July, which indicates that more porjects are successfully funded in these months. 

- What can you conclude about the Outcomes based on Goals?

  * Projects with goals lower than $10000 and between $35000 and $45000 are more likely to be successful.

- What are some limitations of this dataset?

  * the dataset needs update, since deadlines are out of date.
  * the data range is too big

- What are some other possible tables and/or graphs that we could create?

  * Everage Donation by categories or sub categories. To see what categories are tend to get big donations.
  * Fulfil ration of failed and canceled projects by categories. To find out how far they are from success.
