# Chicago Automated Speed Camera Analysis
MSIS2629 Individual Project anayzing the City of Chicago's Automated Speed Camera Program
  
# Version 2
Rachel Lee  
5/5/2019  

**Tableau Public Link:** https://public.tableau.com/views/speed-camera-violations-v2/SpeedingCameraViolationsandFines?:embed=y&:display_count=yes&publish=yes  
**Documentation:** https://rlwy.github.io/chicago-automated-speed-camera-analysis/  

## Reflection
Revisiting Version 1, after Week 5 classes, I noticed some mistakes that I overlooked in preparing the visualizations. For example, the axis label for story card 2 (Collected Fines Estimate by Year) should have been _Estimated Fines to be Collected by Year_ as the chart does not represent the total collected fines by the city, but rather the estimated amounted fines from all issued violations by the automated speed camera program alone. There were also other axis/title related issue in the other charts as well. One thing I realized from preparing the final documentation and cleaning up Version 1 for Version 2, was that my visualizations do not fully support my claim of how the fines were being heavy financial burdens to residents and possibly leading them to debt. Pehaps a more substantial analysis could have been made if I had combined the dataset with another traffic fine related dataset.
  
  
## Changes from **Version 1**
Here are the changes made to the visualizations from Version 1 to 2:

1. The second chart, Estimated Fines by Year (2014 - 2018), underwent some changes from its prior version. The chart's Title and axis labels were reworded to better reflect the visualization. I also included an estimated fines collected with allowance of bad debt to the chart and a forecast for coming two years so that the reader can better estimate revenue from the program.  
2. I also switched all fines related values across all charts to use the Fines Estimate calculated field so that we can test the numbers across all charts to see its impact.
3. Displayed text in the marked labels for the map chart showing _Violations and Fines Estimated by Zipcode and Per Capita Income_ was also reworded to better reflect the figures being shown.
4. Added documentation.
  
No major changes were made to charts in Story cards 1 and 3 as I felt they were easier to understand if left in their basic charts.
  

  
# Version 1
Rachel Lee  
4/28/2019  

**Tableau Public Link:** https://public.tableau.com/views/speed-camera-violations-v1/SpeedingCameraViolationsandFines?:embed=y&:display_count=yes&publish=yes

## Background reading
Prior to beginning the project, a lot of background reading had to be done to understang the Automated Speed Camera program that was launched by the City of Chicago. Materials that were reviewed included the program's documentation on the City's website, along with articles on the program by local news outlets, such as, Chicago Tribune.
  
From our data exploratory, we have seen that the number of violations issued from the program averages to approximately 1 mil per year since its launch in 2014. Background reading and exploratory analysis on other related dataset brought to light several interesting finds:  
 
 - there is a 13% drop in average speed from 26mph in 2014 to 22.5mph in 2018. 
 - the nummber of crashes in children safety zones declined by 4% in 2015 from 2013, while elsewhere in Chicago showed a 13% increase.
 - since the launch of the program, tens of thousands of drivers were ticketed under questionable circumstances (Bordens, A., Epton, A., et al, (n.d.)).
 - there has been high ticket debt, especially in lower income neighbourhoods, with black neighborhoods having the hardest hit (Sanchez, M, and Kambhampati, S., 2018).

## Idea generation for project
From the data exploratory phase, an obvious analysis for this project would be to analyse crash data, which was readily available on the City of Chicago's website. Unfortunately, due to lack of Tableau skills, I was unable to merge the dataset and isolate out only records that were relevant to the children safety zones. After much trial and error, I decided to approach the project from fines collection perspective and did reading on the topic to see if the analysis would show any significance.

## Searching for suitable datasets
There were limited dataset on fines collection and demographic distribution to be integrated into the project. Also, latest official census dataset were dated 2010. I was hoping to find dataset that show racial/income distribution in nearhbourhoods that were within the speed cameras to see if there were any correlation between them. However, I was only able to find income dataset and none for racial.

## Data cleanup
Since there is no way to connect the violations dataset from the data exploratory phase, with the income dataset I found, I used the Speed Camera Location dataset as an intermediate dataset, connecting the locations to violations by ADDRESS columns in both datasets. Using a Excel, I capitalized the addresses in the locations dataset so that it matched that of the violations dataset. I also had to lookup the right zipcodes for each location as it was wrong in the dataset. Using Google Map, I looked up each location individually and inserted the correct zipcode. Once that was completed, I was able to join the locations dataset to the income dataset by their neigbourhood area number. There are 77 neighbourhoods in the City of Chicago. 

## Dabbling with Tableau
In Tableau, 
1. The bar charts for violations by year was straightforward to create by dragging `Violation Date` to column and setting it to be by `YEAR` and `SUM(Violations)` to rows, filtering out records for 2019.
2. To calculate the fines for each year, I set up a parameter called `Violation Fines` with the list of values being 35, 100 and 67.5 (average). I then create the measure `Collected Fines` and `Collected Fines 50/50` that counts the sum of fines for violations issued in each year. After deliberating, I decided to only plot the Collect Fines 50/50 line graph so that we could get an estimate on how much the violations incurred in fines, since there is no indication in the violations if the tickets were of the $35 or $100 ticket types.
3. I then plot a graph to show the average violation and fines paid per adult in the City of Chicago between the age of 18 - 64 for each year. To plot the graph, I created a `Population` parameter with the minimum value of 2,695,598 (according to 2010 census data) and a maximum of 2,750,598. The max value is set by using the population growth rate of 0.425% yearly in census data, which equals to 10,000 increase in population each year.
4. I made sure to standardise the colours used to represent violations and fines in all three charts.
5. A map chart was used to plot the _violations vs per capita income_ by zipcode. Using the crosstab data, I determined the top 3 zipcodes with highest violations and fines and selected them to display their labels and tooltip.
6. Several other charts were created as well and were compared to see which could give the best result for the final story.
7. Lastly, the story was assembled and text included to explain each chart and their insight.

# Data Exploratory
Rachel Lee  
4/21/2019  

**Tableau Public Link**: https://public.tableau.com/views/speed-camera-violations/Story1?:embed=y&:display_count=yes  

# Dataset Sources
**Per Capita Income**  
URL: https://data.cityofchicago.org/Health-Human-Services/Per-Capita-Income/r6ad-wvtk  
Docs: https://data.cityofchicago.org/api/assets/8D10B9D1-CCA3-4E7E-92C7-5125E9AB46E9  

**Speed Camera Locations**   
URL: https://data.cityofchicago.org/Transportation/Speed-Camera-Locations/4i42-qv3h
  
**Speed Camera Violations**  
URL: https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/hhkd-xvj4
  
Crashes  
**Traffic Crashes - Crashes**  
URL: https://data.cityofchicago.org/Transportation/Traffic-Crashes-Crashes/85ca-t3if


# References
Bordens, A., Epton, A., Hing G., Kidwell D., (n.d.). _Speeding tickets questioned_. Chicago Tribune. Accessed at: http://apps.chicagotribune.com/news/local/chicago-speed-camera-tickets/. Access on: April 24, 2019.
  
Brockway, M., (2015). _$1.5 Billion in Unpaid Tickets Could Be Huge Cash Cow for Chicago_. Chicago Tribune. Accessed at: https://www.dnainfo.com/chicago/20150331/downtown/15-billion-unpaid-tickets-could-be-huge-cash-cow-for-chicago/. Accessed on: April 25, 2019.
  
Brockway, M., (2016). _City Rakes in $5.7 Million in Unpaid Tickets and Fines During Amnesty_. Chicago Tribune. Accessed at: https://www.dnainfo.com/chicago/20160108/downtown/city-rakes-57-million-unpaid-tickets-fines-during-amnesty/. Accessed on: April 25, 2019
  
_Chicago Automated Speed Enforcement Camera Before and After Safety Impact Analysis_. Accessed at: https://www.chicago.gov/content/dam/city/depts/cdot/CSZ/ASE_CrashAnalysisWriteUp_10_10_18.pdf
  
_Chicago Children’s Safety ZonesCrash Data from 2009-2012_. Accessed at: https://www.chicago.gov/content/dam/city/depts/cdot/CSZ/ChildrensSafetyZoneList.pdf
  
_Chicago, Illinois Demographic_. Accessed at: https://www.biggestuscities.com/demographics/il/chicago-city
  
Chicago Tribune (2002). _Chicago Communities_. Accessed at: https://www.chicagotribune.com/chi-community-areas-htmlstory.html. Access on: April 25, 2019.

_City of Chicago Budget 2018_. Accessed at: https://www.chicago.gov/content/dam/city/depts/obm/supp_info/2018Budget/2018_Budget_Overview.pdf. Accessed on: 5/2/2019
  
_List of Activated Speed Cameras and Enforcement Schedule_. Accessed at: https://www.chicago.gov/content/dam/city/depts/cdot/Red%20Light%20Cameras/2018/Chicago_Active_Camera_Schedule_090518.pdf
  
Payment Plan Options (Parking, Red Light Camera and Automated Speed Camera). Accessed at: https://www.chicago.gov/city/en/depts/fin/supp_info/revenue/parking_and_red-lightticketpaymentplans.html. Accessed on: April 27, 2019.
  
_QuickFacts - Chicago city, Illinois_. Accessed at: https://www.census.gov/quickfacts/fact/table/chicagocityillinois

Sanchez, M, and Kambhampati, S., 2018. _How Does Chicago Make $200 Million A Year On Parking Tickets? By Bankrupting Thousands of Drivers_. Accessed at: https://www.motherjones.com/crime-justice/2018/02/how-does-chicago-make-200-million-a-year-on-parking-tickets-by-bankrupting-thousands-of-drivers/. Accessed on: April 24, 2019.
  
