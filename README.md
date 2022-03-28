# Top 5 vulnerable countiesorHUC12 in each state
## Purpose of Project
 This dataset consists of a spatial join between HUC12 data of Flooding and Nitrate Pollution (prepared by Jerry Mount of the University of Iowa) and data variables indicating vulnerable communities within chosen states in the Mississippi River Basin.
 To support EDF’s One River project scoping, we performed a distributional environmental justice GIS analysis. We used indicators and proxies from existing datasets such as baseline resilience indicators for communities, life expectancy, and debt-to-asset ratios. While there are many EJ tools and analyses already existing, we wanted to focus on the Mississippi River mainstem states and farmers instead of more urbanized areas. Using these indicators and proxies, we were able to first identify marginalized populations and then we combined those with areas likely to face the highest risks from nitrate pollution and flooding. From this analysis, we identified the top 5 counties in each state that were most vulnerable. This included historically marginalized populations, nitrogen pollution, and flooding throughout the basin. The compiled data will be useful for various EDF strategy processes and for EDF partners.
## Data Utilized
### [Baseline Resilience Indicators for Communities (BRIC)](https://www.sc.edu/study/colleges_schools/artsandsciences/centers_and_institutes/hvri/data_and_resources/bric/index.php)
The BRIC index considers six categories of community disaster resilience: Social, economic, community capital, institutional, infrastructural, and environmental at the county level. The input variables used to measure these categories are then scaled from 0 to 1 with 1 meaning increasing resilience. Once constructed, the sub-index scores are summed to create the overall BRIC score, which ranges from 0-6 for each county. This is at the county level. This data can be found under 'TOT RESIL2015' in the dataset.
### [Life Expectancy](https://www.arcgis.com/home/item.html?id=c514eddc6d584e85bc2f90be25305fc8)
Life Expectancy was utilized in this analysis as it is a useful proxy to [overall health of a community](https://data.oecd.org/healthstat/life-expectancy-at-birth.htm). As life expectancy displays a community's vulnerability to [health risks that could be a result of environmental or systemic issues](https://research.umn.edu/inquiry/post/better-environment-not-slower-aging-increases-life-expectancy), it is useful to measure as a health metric. Environmental degradation is one of the critical determinants of life expectancy, [but it is still under-researched](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0262802). This is at the county level. This data can be found under 'LIFE_EX' in the dataset.
### [Debt-to-Asset Ratio (DAR)](https://www.bea.gov/data)
The Debt-to-Asset Ratio of farms and agricultural companies was utilized as a proxy for rural financial risk and vulnerability. Each county has an average DAR. This data was gathered from the Bureau of Economic Analysis by [Mandy Liesch](https://github.com/agrichick45/EDF/blob/main/ReadMe.md#farm-income-and-debt-to-asset-ratio). This is at the county level. This data can be found under 'Debtall' in the dataset.
### Nitrate and Flooding Data
The Nitrate and Flooding Data utilized was created by Jerry Mount at the University of Iowa, and was derived from SWAT+ surface runoff data. This is at the HUC12 level. Within data files, Flooding = MEAN_surq_ProxyforFlooding and Nitrate = sumno3_Nitrate.  

## Maps
![All States Flood Risk Map](https://github.com/Danavh697/Top-5-vulnerable-countiesorHUC12-in-each-state/blob/143f78327078710bd8298cf0d831852125079338/Maps/All_Flooding.png)

![All States Nitrate Risk Map](https://github.com/Danavh697/Top-5-vulnerable-countiesorHUC12-in-each-state/blob/cee4e73481e929677bd57f6963701929615a60b6/Maps/All_Nitrate.png)

## Methodology
In order to complete this analysis, a spatial join was conducted between the Social Vulnerability variables (BRIC, DAR, and Life Expectancy), which were at a county level, and the Nitrogen and Flood vulnerability data, which was at the HUC12 level. The averages for each Social Vulnerability variables were found for each state, and each state's individual averages were used in order to find socially vulnerable counties. The maps in this analysis display the basin-wide averages for the socially vulnerable variables. The 5 counties that were at the highest vulnerability and intersected with the highest flooding or nitrate pollution were selected and put into a list with all of the highest risk counties in the basin. A similar action was conducted in order to find the most vulnerable HUC12s in each state. All counties with social vulnerability for each state can be found within the individual state's data file.

Flood Risk Data and Nitrogen Pollution data were analyzed seperately so that overlap between the two could be analyzed at a later date. The spatial join was conducted twice, once so that the data would be at the county level (in which only the HUC12 with the highest Flood risk or Nitrogen risk was apparent) and once so that the data would be at the HUC12 level. This way, specific HUC12s at risk could be seen inside the at-risk counties. The only flood risk and nitrate that will appear is the risk inside counties that have already been deemed socially vulnerable. For example, in Iowa, there are 9 counties that are considered socially vulnerable due to their BRIC, DAR, and Life Expectancy statistics. Only at-risk HUC-12 watersheds from those 9 counties will appear in this analysis.

## Files in this github
### Top5risk_Flooding
[Top5risk_Flooding](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/dfa1f4ac7f6f816f224dcc7bbf62ff21df70f289/Top5risk_Flooding.xlsx) is a list of the 5 counties or HUC12s in each analyzed state that are at the highest risk of social vulnerability and flood risk. Each state is measured on a state-wide metric for social risk, taking the median BRIC, DAR, and Life Expectancy in said state to measure vulnerability. The list of counties or HUC12s that are found to have higher than average DAR and lower than average BRIC and Life Expectancy is then ranked in terms of flood risk in order to find the highest overlapped risk.

### Top5risk_Nitrate
[Top5risk_Nitrate](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/dfa1f4ac7f6f816f224dcc7bbf62ff21df70f289/Top5risk_Nitrate.xlsx) is a list of the top 5 counties or HUC12s in each analyzed state that are at the highest risk of social vulnerability and nitrate pollution. Each state is measured on a state-wide metric for social risk, taking the median BRIC, DAR, and Life Expectancy in said state to measure vulnerability. The list of counties or HUC12s that are found to have higher than average DAR and lower than average BRIC and Life Expectancy is then ranked in terms of nitrate pollution in order to find the highest overlapped risk.

### AllCountiesandHUC12
[AllCountiesandHUC12](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/dfa1f4ac7f6f816f224dcc7bbf62ff21df70f289/AllCountiesandHUC12.xlsx) is a list of all of the data collected for the counties and HUC12s in the states analyzed. This consists of 850 counties, and 23,802 HUC12s. Any counties or HUC12s displayed in this file are part of the MRB, meaning that there are counties/HUC12s missing from states that are not entirely in the MRB.

### Individual State files
Files found in folders for individual states contain all of the counties/HUC12s that met parameters for social vulnerability and flooding or nitrate pollution. For example, in the [IllinoisRisk_Flooding](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/dfa1f4ac7f6f816f224dcc7bbf62ff21df70f289/Illinois/IllinoisRisk_Flooding.xlsx) file, one can see that 23 counties met the metrics for social vulnerability. The Readme.md files for these folders will contain the parameters of social vulnerability for the individual state, and will have the 5 counties and HUC12 which had the highest flood risk or nitrogen pollution and social vulnerability metrics listed.

## Findings regarding Flooding and Nitrate pollution
Flooding tended to be more severe towards the bottom of the watershed, namely in Mississippi, Louisiana, Arkansas, southern Missouri and Illinois, and western Tennessee. Nitrate pollution was more severe in the the Upper Mississippi River Basin, namely Iowa, Missouri, Illinois, Minnesota and Wisconsin. The areas where these two variables were combined most often are in Iowa, Missouri, and Illinois. Issues regarding flooding and nitrate have been well documented in the American Bottom Region, an [image](https://www.researchgate.net/figure/The-American-Bottom-locality-shaded-area_fig6_285523981) of which can be found at the end of this section. In the past, most notably the [Centreville](https://floodedandforgotten.com/summary-of-the-centreville-sewage-crisis/) crisis, in which one of the most socially vulnerable communities in Illinois has continually suffered from enviromental justice and public health issues for decades.

![American Bottom Region](https://www.researchgate.net/profile/Thomas-Emerson-3/publication/285523981/figure/fig6/AS:668871702888463@1536482849809/The-American-Bottom-locality-shaded-area.ppm)

In the map below, the area where this overlap occurs can be seen in bright pink. Areas with high flood risk can be seen in green, and areas with high nitrate pollution can be see in light pink.
![Flooding and Nitrate](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/0554eab9f3805a6b7cfffa730f76c429535e8d0f/Maps/NitrateandFlooding.png)

### Maps displaying Flooding and Nitrate pollution findings

#### This map displays where flooding is most prominant in the basin.
![Flooding](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/2158d481117346e38eafe7884458a1a9f9491dcc/Maps/Floodingonly.png)

#### This map displays the 50 HUC12s that are most vulnerable to flooding in the basin.
![Top 50](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/2158d481117346e38eafe7884458a1a9f9491dcc/Maps/Top50HUC12Flooding.png)

#### This map displays where nitrate pollution is most prominant in the basin.
![Nitrate](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/2158d481117346e38eafe7884458a1a9f9491dcc/Maps/Nitrateonly.png)

#### This map displays the 50 HUC12s that are most vulnerable to nitrate pollution in the basin.
![Top 50](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/2158d481117346e38eafe7884458a1a9f9491dcc/Maps/Top50HUC12Nitrate.png)

#### This map displays the overlap between counties determined as at-risk as described [here](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state#methodology) and the 50 counties with the highest overall flood risk in the basin.
![HRCvsTotalflooding](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/d65658a99240e7b339673568e924145fd35d7183/Maps/FloodingcountiesHRCvsall.png)

#### This map displays the overlap between counties determined as at-risk as described [here](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state#methodology) and the 50 counties with the highest overall nitrate pollution risk in the basin. 
![HRCvsTotalnitrate](https://github.com/Danavh697/Top_5_vulnerable_countiesorHUC12_in_each_state/blob/d65658a99240e7b339673568e924145fd35d7183/Maps/NitratecountiesHRCvsall.png)
