# FINAL PROJECT - TRASH ON LOS ANGELES BEACHES

### What types and amounts of plastic debris were logged by the Heal the Bay Organization during the month of July 2026?

## The Database
I used the Marina Debris Tracker app from NOAA. https://debristracker.org/data.

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
In July of 2026, Heal the Bay logged the plastics in 13 cities, including Las Vegas Nevada.
Heal The Bay logged plastics in every month of the 2026 water year, except November. 

![imagealt](https://github.com/acamend/cs82a-portfolio/blob/211b230e142fffe11be39eb5436c45d757332941/Final%20Project/Plastics%20per%20month.png)

The most plastic was logged in July.
There were 5085 pieces of plastic logged by Heal the Bay in July. 

![imagealt](https://github.com/acamend/cs82a-portfolio/blob/eb3692192fdfbcce7f42f255224ebb5e3a4d3b07/Final%20Project/Plastics%20in%20July.png)

A little over 50% were classified as 'plastic pieces'. 
Plastic snack bags/wrappers, beverage bottles, and bottle caps/rings accounted for about 25%, and 
plates, cups/lids, utensils, stirrers/straws accounted for about 12%.

![imagealt](

The correlation heat map showed no strong correlation between 'plastic pieces' and any other plastic. 
However, a more intensive investigation using prediction statistics and looking at each event or user's results would be more appropriate and may result in a usable correlation.

## Limitation and what next
I would like to access all the materials logged along Ballona Creek. 
I cannot do this without extracting the entire worldwide database so I need to contact the Marine Debris folks for different access.
I would like to find out how plastic types and amounts fluctuate with rain. Need to pull rain data and join that to my database.
