# Battery Low: An Analysis of Washington State’s Electric Vehicle (EV) Charger Distribution

## I. Group Members
This project is a two-person group project. The contributors are Clara Bates and Kaylah Tan.

## II. Colab Worksheet
The link to my Colab workbook can be found [here](https://colab.research.google.com/drive/16EMIzERPqem2CVYGsDjUBzvYeUO5rlab#scrollTo=bOSot0bqrTXf).

## III. Report
This report provides an overview of our project.

Introduction
<br>
For this project, we will be using two main datasets. The first dataset is an Electric Vehicle Population Dataset, which contains information about all EVs registered in Washington State. Sourced from data.gov, this dataset provides detailed location data for analyzing population density. Our second dataset, an EV Charging Station dataset, is from the U.S. Department of Energy’s Alternative Fuels Data Center. This data set stores the locations of all publicly available charging stations in Washington. 
	For our central research question, we want to explore how well-distributed EV chargers are across Washington State compared to the distribution of registered EVs. Are there areas of the state that need more charging stations? Where are EV owners more likely to find a station? To answer these questions, we will compare the population of EVs to the population of EV charging stations by county. 

Methods and Results
<br>
We began by loading the CSV files into pandas dataframes, selecting the columns that were relevant to our research questions. Since we planned on analyzing the data by county, we were initially concerned that the EV population dataset didn’t have a county column. We were able to solve this issue by merging the EV population dataframe with the EV charging station dataframe on the ZIP code column. Our next step was to count the number of EV charging stations in each county, adding a station count column to the counties dataframe. This exact process was repeated for counting the number of EVs in each county. Once we had station and EV counts, we calculated the ratio of EVs to charging stations for each county. This gave us a more meaningful metric with which to compare charging station availability across the state. 
	To analyze the data, we created two different visualizations. The first was a Mapbox scatterplot of EV charging stations by county. The size of the dot represents the number of EV charging stations, and the color of the dot represents the number of EVs per charging station.
 
 
![ev_stations (2)](https://github.com/user-attachments/assets/8d2b3349-d6f8-4e27-a015-d7815b7bb59f)
<div style="text-align: center;">
<p><strong>Figure 1:</strong> Electric Vehicle charging stations by county</p>
<a href="https://drive.google.com/file/d/1_hrRyvFF0_IM-UaEidRgYCYerKU_tWmE/view?usp=drive_link" title="https://drive.google.com/file/d/1_hrRyvFF0_IM-UaEidRgYCYerKU_tWmE/view?usp=drive_link">
	Click here to view the interactive map with hover effects
</a>
</div>

Based on the map, King County has the most EV charging stations, and roughly 35 EVs per charging station. Counties with fewer EV charging stations also appear to have fewer EVs per charging station.

The second visualization was a box plot of EV population by county. Similar to the other plot, the color indicates the ratio of EVs to charging stations in a county. 

![ev_count (3)](https://github.com/user-attachments/assets/4493b798-b6c8-4cfa-a05a-fb0c49c9ea0b)
<div style="text-align: center;">
<p><strong>Figure 2:</strong> Electric Vehicle Counts by County</p>
<a href="https://drive.google.com/file/d/1DQJ8uEFV646eM5jk_KbYblHqvynOTq2z/view?usp=drive_link" title="https://drive.google.com/file/d/1DQJ8uEFV646eM5jk_KbYblHqvynOTq2z/view?usp=drive_link">
	Click here to view the interactive map with hover effects
</a>
</div>
As expected, King County has the highest number of EVs, followed by Snohomish and Pierce County. This visualization also supports the claim that counties with more EVs have proportionally fewer charging stations.

Conclusion
<br>
Based on the varying ratios by county, it appears that EV charging stations are not very well distributed across Washington State. Some counties, such as Island, Snohomish and Clark County, had more than 40 EVs for each charging station. On the other hand, Skamania,  Columbia, and Lincoln County had fewer than 10 EVs for each charging station. This data analysis suggests that although counties with high EV populations have a lot of EV charging stations, the ratio is typically larger than counties with low EV populations.
	One reservation about this analysis is that it doesn’t take into account hybrid vehicles. The dataset of EVs includes hybrid vehicles, which have a lower demand for charging stations. Another limitation is that the EV location data is only specific as a Zip Code, which makes it impossible to calculate exact distances between a registered EV and nearby charging stations. It would be interesting to perform a more in depth analysis based on the average number of charging stations within a certain distance of an EV.
Another potential area of further study would be to analyze EV charging density with median income by county. Do counties with a higher median income also have a higher ratio of charging stations to electric vehicles? We could also compare gas station availability to EV charging station availability. Is it easier for owners of gas-powered vehicles to find a gas station than it is for EV owners to find a charging station?

References

U.S. Department of Energy. "Electricity Infrastructure Trends." Alternative Fuels Data Center,
https://afdc.energy.gov/fuels/electricity-infrastructure-trends. Accessed 28 June 2024.

U.S. Government Open Data. "Electric Vehicle Population Data." Data.gov,
https://catalog.data.gov/dataset/electric-vehicle-population-data. Accessed 28 June 2024.

