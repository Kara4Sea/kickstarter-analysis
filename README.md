# An Analysis of Kickstarter Campaigns
Analysis on Kickstarter data to determine goal success rates
## Overview of Project
### Purpose
The purpose of this analysis is to determine how to contribute to more success in a Kickstarter project. Both launch date and funding goals are reviewed to find variables that contribute to the success of reaching fundraising goals. 
## Analysis and Challenges
### Analysis of Outcomes Based on Launch Date
I performed analysis by creating a pivot table to examine the success of theater campaigns depending on their launch date. To ensure that the pivot table could be filtered by years, I used `YEARS(S1)` to pull over the year of each launch date into its own column, I then copied this to the below rows. I then created a pivot table using the filters of “Parent Category” and “Years”, assigned the columns of “Outcomes”, rows of “Date Created Conversion”, and values of “Counts of Outcomes”. I filtered column labels to only reflect “successful”, “failed’, and “canceled”. I filtered the parent category for “theater”. Then I created a line chart based off the pivot table.
### Analysis of Outcomes Based on Goals
I created a new sheet and typed in column and row headings as instructed. To determine “Number Successful”, “Number Failed” and “Number Canceled”, I inserted a `=COUNTIF` function. For the first line I used ` =COUNTIFS(Kickstarter!$D:$D, "<1000", Kickstarter!$F:$F, "Successful", Kickstarter!R:R, "plays")` to determine all successful with a goal of “less than 1000”. For all other rows, I expanded to include less than or equal to values. For example, ` =COUNTIFS(Kickstarter!$D:$D, ">=1000", Kickstarter!$F:$F, "Successful",Kickstarter!R:R, "plays", Kickstarter!$D:$D,"<=4999")`. For other columns, I made sure to change “Successful” to “Failed” or “Canceled” as appropriate. I used the `=SUM` function to find the total projects. Then I calculated the percentage successful, failed and canceled. To create the line chart, I highlighted columns “Goal”, “Percentage Successful”, “Percentage Failed” and “Percentage Canceled”. Then I selected line chart from the insert tab.

### Challenges and Difficulties Encountered
With the Analysis of Outcomes Based on Launch Date, the challenge I encountered was determining what elements to include in filters, columns, rows and values. I analyzed the example to find the best fit and played around with the formatting until it matched the example given.

With the Analysis of Outcomes Based on Goal, I came across several challenges. I experienced an issue where some on my `=COUNTIFS` functions were pulling an inaccurate result at zero. In problem-solving, I learned I had to go back and insert a dollar sign in front of the row and column indicated for each cell that used a numeric value. When I first created my line chart, I highlighted the full table. The result did not look like the example given. I tried a pivot table chart, and quickly saw that all I had to do was go back to the original table and highlight the “Goal”, “Percentage Successful”, “Percentage Failed” and “Percentage Canceled” columns before prompting to create the chart.
## Results
### Theater Outcomes by Launch Date Conclusions
Success rates were highest when theater productions launched in late Spring, especially May and June. Success rates level off in August. Success rates are lowest in December. Though Failure rates follow a similar trend to success rates, their overall percentage is lower, making success more likely. The one month where this is not the case is in December, when success and failure are equally as likely to occur. 0% of theater productions throughout the year were canceled, so this variable does not impact analysis, except to say that chances of cancelation are extremely low, regardless of launch.

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/110419577/189217280-4a6b6f9e-2e4b-438b-bb4e-811d4a9893f1.png)
### Outcomes base on Goals Conclusions
Success rates based on goals were highest in the “Less than 1000” and “1000 to 4999” ranges, followed by another peak of success in the “35000 to 39999” and “40000 to 44999” ranges. Failure rates are inverted from success rates, meaning that the goals that are most likely to succeed are also the goals most unlikely to fail. There is a sharp decline in successful goals at the “45000 to 49999” range. 0% of plays throughout the year were canceled, so this variable does not impact analysis, except to say that chances of cancelation are extremely low, regardless of goal.

![Outcome_vs_Goals](https://user-images.githubusercontent.com/110419577/189217411-96467fed-dd2c-4505-b12b-bada460276fd.png)
### Dataset Limitations
* For Outcomes based on goal, some information is needed to reflect outliers. The total of plays between first most successful ranges (Less than 1000 to 9999) is 889. While the second most successful range per chart (35000 to 44999) has a total amount of 9 plays. Differences in sample sizes make it difficult to predict if the chart is representative of success with goals ranging 35000 to 44999.
* For Outcomes Based on Launch Date, October is registering with a blank rather than a zero, causing a gap on the line chart. This could benefit from data cleaning to replace blank value with zero.
* Drawing comparisons betweeen Outcomes Based on Goal and Outcomes Based on Launch is difficult as these are not measuring apples to apples. Goals inspects subcategory of plays, while launch date inspects category of theater. 
### Additional Tables and Graphs
## Below are charts that reflect both category of theater and subcategory of plays, across outcomes based on launch date and goals.
![Play Outcomes Vs Launch Date](https://user-images.githubusercontent.com/110419577/189542690-cd570943-4c3d-49ad-a83c-e50b3e7009d6.png)

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/110419577/189542696-55d90fae-7860-40b4-927e-d7df5f97170d.png)

![Play Outcomes Vs Goals](https://user-images.githubusercontent.com/110419577/189542760-b7fc0226-d05b-4c1d-a83e-dc9cd781dd83.png)

![Theater Outcomes Vs  Goals](https://user-images.githubusercontent.com/110419577/189542780-623b7ad8-9731-42f1-baa3-72f46216def2.png)

## Below is a box and whisker plot to display Goal vs Pledge and the number of outliers present
![Play Goal Vs Pledge](https://user-images.githubusercontent.com/110419577/189542823-7b001365-0892-475a-9522-ee5aeec86640.png)
