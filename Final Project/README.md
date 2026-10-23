# FINAL PROJECT - TRASH ON LOS ANGELES BEACHES

### What types and amounts of plastic debris were logged by the Heal the Bay Organization during the month of July 2026?

## The Database
I used the Marine Debris Tracker app from NOAA. https://debristracker.org/data.

This website only allows the user to sort by two parameters, organization and date. It is a worldwide database. I would love to be able to sort on Los Angeles or Lat/long values but the website does not allow that.
For my csv export, I filtered the database on 'Heal the Bay' as the local LA organization and the time period Oct 1, 2025 - October 1, 2026 (the rainy season officially starts an Oct 1 each year. This period is defined as the 2026 Water Year). 

The exported database was (7883, 18) in size. See data dictionay in the Final Project file for information.
The only change made was the dtype of column 'dt' (date) from string to datetime.

## Actions Taken
To get to know the database, I investigated all the cities with Heal The Bay trash logging events.
I looked at the number of plastics found in each city.
I looked at the material types
I selected to only view plastic materials
I looked at the itemnames under the plastic materials heading
I pulled a smaller working database from the larger import (5038,6).
I plotted Quantity of Plastics logged by month for the water year.
I plotted Quantity of Plastics logged by type in July 
I plotted Quantity of Plastics as a Percentage logged by type in July 
I ran a correspondance matrix to see if there was a correlation between 'plastic pieces' and any of the larger plastic items.


## Findings
In July of 2026, Heal the Bay logged the plastics in 13 cities, including Las Vegas, Nevada.
Heal The Bay logged plastics in every month of the 2026 water year, except November. 

![imagealt](https://github.com/acamend/cs82a-portfolio/blob/211b230e142fffe11be39eb5436c45d757332941/Final%20Project/Plastics%20per%20month.png)

The most plastic was logged in May, June and July as seen above. Warning: These data have not been adjusted for the number of events or participants, so one cannot assume that there is more trash on the beach in the summer. This is just a look at the data.



![imagealt](https://github.com/acamend/cs82a-portfolio/blob/eb3692192fdfbcce7f42f255224ebb5e3a4d3b07/Final%20Project/Plastics%20in%20July.png)

There were 5085 pieces of plastic logged by Heal the Bay in July. The largest quantity on July 19.



![imagealt](https://github.com/acamend/cs82a-portfolio/blob/e94cb89d3fc3bee9b03b21aa1160a4abf797f8d5/Final%20Project/Plastic%20Percentages.png)

A little over 50% were classified as 'plastic pieces'. 

Single use food, related plastics made up about one third; Plastic snack bags/wrappers, beverage bottles, and bottle caps/rings accounted for about 25%, and plates, cups/lids, utensils, stirrers/straws accounted for about 12%.

This is the area where I aim to make change. I would like to create policies that reduce this type of plastic. 



## Statistics 

Is there an item type which would make a good predictor for 'plastic pieces'? In general whole plastic items break into smaller and smaller plastic items over time and the smaller the plastic, the more hazarous to life. It would be good to have a predictor of a type of plastic that is more easily found and communicated through these community science events. 

![imagealt](https://github.com/acamend/cs82a-portfolio/blob/de9f749a502f691dc7798b616dd4613f363c3ee4/Final%20Project/Final_Correlation.png)

**Findings:** The correlation heat map showed no strong correlation between 'plastic pieces' and any other plastic. It does correlate well with the total, but that is not the correlation I am looking for. I am looking for larger plastics to indicate small plastic pieces.  However, it's possible that a more intensive investigation using prediction statistics and looking at each event or user's results would be more appropriate and may result in a usable correlation. 

## Limitation and what next
I would like to access all the materials logged along Ballona Creek. 
I cannot do this without extracting the entire worldwide database so I need to contact the Marine Debris folks for different access.
I would like to find out how plastic types and amounts fluctuate with rain. Need to pull rain data and join that to my database. I have already received the csv from NOAA on this.

# AI Prompt Log

## AI Prompt for initial cleaning and shrinking of my working database
Tool: Gemini Prompt: You are helping to create a smaller database and clean some data: (1)My CSV has 18 columns. I want to create a new df, named plastic_df, that includes only 6 of the 18 columns, they are: [itemname], [material], [quantity], [location], [dt], [id]. (2) The date in the dt column is a string, change dtype to datetime. (3) There are numerous "materials' values. Only pull 'plastic' material into this database. I should end up with a smaller database that has only 6 columns and only plastic materials. Explain each step in comments.

I verfied the data before and after and used the code with no changes.

## AI Prompt 2
You are helping me create plots using the plastic_df database I want to create (1) A plot to show total quantity of plastic each month. (2) Show a plot of the total quantity of each itemname in the month of July (3) plot of the quantity of each itemname in the month of July as a percent of the total items. Write Python using pandas and seaborn to: organize the data and produce the charts. Explain each step in comments.

The code worked without error. One drawback with task (1), the code is that when summarizing the plastics per month, the code is written to define each month a a period (dtype string). Therefore November, with no data, is not in the plot. I left it as is but would change that if I were to use that in a report, not just a probe of the database.

## AI Prompt #3
I asked Gemini to provide the coding for step #3 to be a pie chart instead of bar chart. The chart is too crowded so I did not include it in this report although it can be see in my notebook.


