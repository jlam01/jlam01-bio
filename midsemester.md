**Coding Language:** Python using Jupyter

## Question: Are there any correlations between COVID cases within colleges and within counties? Are the mask regulations for both counties and colleges involved with the number of cases?

### Conceptually, how do you propose to go about addressing this question?

In order to approach the question I have, I would need to obtain the number of COVID cases within the colleges in the US as well as the number of COVID cases within each county in the US. I would also need to obtain the population numbers within the colleges and counties in order to compare the two by ratio. Lastly, I would need to obtain mask regulation data for both.

### What datasets did you use to answer these questions? Where did you get these from?

College and county cases were both found from the new york times. I was able to find a dataset from kaggle containing info from the census bureau on county population. Lastly, I had a lot of trouble finding a dataset on college population, mask regulation in counties, and mask regulation in colleges, so for each, I went and did my own research by going to each college site or county to figure out which places have a mask regulation in place as well as the college population info.
- **College cases:** Describes the number of college cases and describes it by the college, state, county and city. [New York Times College Cases csv](https://raw.githubusercontent.com/nytimes/covid-19-data/master/colleges/colleges.csv)
- **County cases:** Describes the number of cases per county in the US and also lists the deaths, confirmed cases, confirmed deaths, probable cases, and probable deaths. [New York Times US County Cases csv](https://raw.githubusercontent.com/nytimes/covid-19-data/master/live/us-counties.csv)
- **Population by county (2017):** Describes the total population of adults (18+) of each county but also includes other data such as population by sex, race, income, employment, and method of commute. [Kaggle US Census 2017 Dataset](https://www.kaggle.com/muonneutrino/us-census-demographic-data?select=acs2017_county_data.csv)
- **College Enrollment Headcount (2017):** Describes the total population of students in each college/university in the US. This data was collected directly from the college sites for 2017 in order to match with the population dataset that was found, which is for 2017. [College Enrollment Headcount Dataset]()
- **State-by-State Face Mask Requirements:** Describes whether or not for each state if mask usage is required. Since the info found was not in csv format nor in a dataframe, the csv file was personally made by me. [Original data source](https://www.aarp.org/health/healthy-living/info-2020/states-mask-mandates-coronavirus.html), [csv file created from data source]()
- **College Face Mask Requirements:** Describes whether or not for each college if mask usage is required. This data was collected directly from each college website on their responses to COVID-19. If no response could be found on the site, the college will be labeled to have no face mask requirement. [College Face Mask Dataset]()

### What types of analyses did you conduct?
I conducted a *linear regression* on the college and county cases by population to see if the number of cases is correlated with the population. I also conducted a *correlation analysis* between the ratios of cases by population between county and college. Lasty, I conducted several *t-tests*: college cases and population, county cases and population, and college case ratio and county case ratio (which is case divided by population).

### What did you find? Present results.
![collegecountycases](https://user-images.githubusercontent.com/67992204/97264093-a5736c80-17fa-11eb-9357-33ce63800bce.png)
**Figure 1. College and County Cases by Population.** The number of cases (y-axis) per population (x-axis) for college and county was plotted on a linear regression graph (R^2=0.304,0.794) and t-tests were performed (p=2.213e<sup>-85</sup>,1.566e<sup>-40</sup>).
![ratiocollegecountycases](https://user-images.githubusercontent.com/67992204/97264096-a7d5c680-17fa-11eb-88a7-6c9f43503a53.png)
**Figure 2. Ratio of cases in Colleges vs. Counties.** The number of cases for colleges and counties were divided by the population size of each, respectively, and plotted on a graph. The correlation was calculated (corr=0.395) and a t-test was performed (p=0.098).

### What are the implications of these results?
Through the linear regression graphs done in Figure 1, the cases and populations in the county are presented to be more correlated in comparison to the cases and population in the colleges due to the higher R^2 by 0.49. As shown through the t-tests performed for the graphs in Figure 1, it can be concluded that the cases and population correlations are not due to pure chance as the p-values are both greater than 0.5 and the null hypothesis can be rejected. Meanwhile, through the correlation analysis of the ratio of cases in the counties and colleges in Figure 2, although the correlation analysis presented that there is a medium correlation between the ratios, the null hypothesis cannot be rejected as the p-value is greater than 0.5.

### Afterword
Further analysis may have to be performed in order to see if there may be any correlation between the college and county cases. Since the population data was collected for 2017, since the COVID-19 pandemic did not occur until 2019, a more accurate analysis could be done if the population data for both counties and colleges were collected on 2019 or 2020, especially since the number of cases stretches into 2020.
