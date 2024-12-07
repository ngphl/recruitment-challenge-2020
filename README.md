# Synengco Recruitment Challenge

Recruitment challenge based on AEMO electricity demand 

# Note

This challenge was fairly simple in theory, focusing on data visualization with a straightforward dataset.
The data format and quality were also convenient for the user to use, without any errors or formatting issues, probably because it was fetched from a government website.

Considering the year the challenge was created and the nature of the provided dataset, 2015-2019, I will only consider 2020 as a recent time.

## Tool
Choice Python vs R:
I chose Python because initially, I thought about predicting 2020 using a machine learning algorithm, but alas it's not required and currently, I'm more comfortable using Python for visualization.

## Tackling

Given the Year, Month, Day and Intervals column, it was straightforward to map energy demand in a single day by flattening the intervals column.

For visualizing Year/Monthly/Daily - I found the average energy demand in a single day and month to map into a graph, simply by taking the mean.

Predicting 2020, per instruction, to average actual electricity demand over the past 5 years. So I simply use group by Month/Day and use mean to find the average for every day/interval electricity demand.

## Challenges

The difficult part about this challenge is how to integrate the actual April 2020 data download from AEMO. A lot of trials and errors, google and ChatGPT were required because the format was tricky to adapt to other datasets for visualization.

Note that a day also starts and ends at 4 am in the challenge, while the downloaded dataset has days starting/ending at 12 instead, so some adaptions had to be made.

## Result/Observation

![alt text](https://github.com/ngphl/recruitment-challenge-2020/blob/master/deliverables/Actual%20April%202020%20vs%20Others.png)

This shows the resulting estimated 2020 electricity demand against 2015-2019, we can see a pattern emerging, with high consumption during the first 2 months, and shows a steep decrease toward the middle of the year, probably due to weather changes (Summer->Winter), at lowest demand point of September, but increase from October toward December (increase AC usage maybe).

![alt_text](https://github.com/ngphl/recruitment-challenge-2020/blob/master/deliverables/Anzac%20Day%202020%20Predicted.png)

Another pattern, this time within Anzac Day in 2020 Predicted. Throughout the day the electricity demanded is relatively low, because people are likely to be going out, and increase significantly from 18:30 onward, as people are returning home and resting (indicated by a downward slope)

![alt_text](https://github.com/ngphl/recruitment-challenge-2020/blob/master/deliverables/Actual%20April%202020%20vs%20Others.png)

This visualizes the actual data trend in April 2020, against April in historical data and predicted 2020. While there are signs of a common pattern between Actual vs Predicted April 2020, it's worth noting that Covid was a huge factor this year and had changed people's lives/behaviors drastically. An example could be a lockdown period, where people had to stay home for a long time, increasing electricity usage in daily household.

## Helper Function

For visualising electricity demanded in a single day
```python
day_viz(day,month,year,df)
```

For visualising electricity demanded in a single month
```python
daily_viz(month,year)
```

For visualising electricity demanded in a single year
```python
monthly_viz(year)
```

For visualising electricity demanded between years
```python
monthly_viz_years(df, title)
```

# Do differently and suggestion

While I think the line graph is best fit already for these dataset, different types of graphs and modification could probably be tested to find further insight or communicate the data better, such as bar graphs or boxplots.

Additionally, in terms of predicting electricity demand for 2020, taking the average of previous years is a decent approach, but given the technologies, we could try to use an AI algorithm to predict it.

I would suggest incorporating the latest data post-Covid-19 with more comprehensive detail/factors that influence the electricity demand, along with experimental AI prediction challenge for the next couple of years.
