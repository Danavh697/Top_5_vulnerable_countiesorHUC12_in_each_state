# Top 5 vulnerable countiesorHUC12 in each state
## Purpose of Project
 This dataset consists of a spatial join between HUC12 data of Flooding and Nitrate Pollution (prepared by Jerry Mount of the University of Iowa) and data variables indicating vulnerable communities within chosen states in the Mississippi River Basin.
## Data Utilized
### [Baseline Resilience Indicators for Communities (BRIC)] (https://www.sc.edu/study/colleges_schools/artsandsciences/centers_and_institutes/hvri/data_and_resources/bric/index.php)
The BRIC index considers six categories of community disaster resilience: Social, economic, community capital, institutional, infrastructural, and environmental at the county level. The input variables used to measure these categories are then scaled from 0 to 1 with 1 meaning increasing resilience. Once constructed, the sub-index scores are summed to create the overall BRIC score, which ranges from 0-6 for each county. This is at the county level.
### [Life Expectancy] (https://www.arcgis.com/home/item.html?id=c514eddc6d584e85bc2f90be25305fc8)
Life Expectancy was utilized in this analysis as it is a useful proxy to [vulnerability] (https://data.oecd.org/healthstat/life-expectancy-at-birth.htm). As life expectancy displays a community's vulnerability to health risks that could be a result of environmental or systemic issues, it is useful to measure as a health metric. This is at the county level.
### [Debt-to-Asset Ratio (DAR)] (https://www.bea.gov/data)
The Debt-to-Asset Ratio of farms and agricultural companies was utilized as a proxy for rural financial risk and vulnerability. Each county has an average DAR. This data was gathered by Mandy Liesch from the Bureau of Economic Analysis. This is at the county level.
### Nitrate and Flooding Data
The Nitrate and Flooding Data utilized was created by Jerry Mount at the University of Iowa, and was derived from SWAT+ surface runoff data. This is at the HUC12 level.  
##Methodology
In order to complete this analysis, a spatial join was conducted between the Social Vulnerability variables (BRIC, DAR, and Life Expectancy), which were at a county level, and the Nitrogen and Flood risk data, which was at the HUC12 level. Flood Risk Data and Nitrogen Pollution data were analyzed seperately so that overlap between the two could be analyzed at a later date. The spatial join was conducted twice, once so that the data would be at the county level (in which only the HUC12 with the highest Flood risk or Nitrogen risk was apparent) and once so that the data would be at the HUC12 level. This way 
