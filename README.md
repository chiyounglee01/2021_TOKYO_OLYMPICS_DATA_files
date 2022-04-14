# 2021_tokyo_olympics

**This exploration attempts to answer the following questions.**

* **Which countries won the most medals?**
* **Which countries had the most Athlete Count?**
* **Is there a correlation between Athlete Count and the number of Medals a country wins?**
* **Amongst the top 30 medal winning countries, is there a correlation between Per Capita GDP and the number of Medals a country wins?**

For this exploration I used the 2021 Tokyo Olympics Dataset found in Kaggle.

https://www.kaggle.com/arjunprasadsarkhel/2021-olympics-in-tokyo

I use the Medals.xlsx and 'Athletes.xlsx' files in the dataset to explore the correlation of the number of athletes a country sends and the number of medals a country wins.

For the top 30 total medal winning countries, I also explore the correlation between Per Capita GDP and total medals won. I use the World Bank's GDP PER CAPITA Data for 2020.
I also supplement some missing data from the CIA World Factbook page.

https://data.worldbank.org/indicator/NY.GDP.PCAP.CD

https://www.cia.gov/the-world-factbook/field/real-gdp-per-capita/country-comparison

## DATA WRANGLING

First, in the Olympic Medal dataset, there were many countries that didn't win any medals. There were a lot of null values. I had to replace
all null values with 0 using the replace() function. 

The biggest challenge to this analysis was joining the Olympic data from Kaggle to the GDP data from the
World Bank. The country names were different in these two sources. For example, in the Kaggle Olympic dataset the
country "Bahamas" was called "The Bahamas" in the World Bank data. I had to make a dictionary and use the rename()
function to change the country names of the World Bank data to the version in the Olympic Data. I then joined the two
datasets.

After I joined the datasets, I realized the GDP value for "Chinese Taipei", "Cuba" and "Japan" did not exist for
in the world bank dataset for the year 2020. I used the CIA Factbook data to get the GDP data for Japan's 2019,
Chinese Taipei's 2018 and Cuba's 2020 GDP. I made a dictionary for those values and used the fillna() function to
enter GDP data for those countries.



## CONCLUSION

* **United States of America, People's Republic of China and ROC(Russia) won the most Medals in Tokyo 2021.**
* **United States of America, Japan and Australia sent the most Athletes to Tokyo 2021.**
* **There is a strong correlation between Athlete Count and the Total Medals a Country wins. Pearson R = 0.87**
* **There is a low correlation between GDP Per Capita and the Total Medals a Country wins.
Pearson R = 0.21. 
This makes sense as People's Republic of China and ROC(Russia) are amongst top 3 medal winners but have relatively low GDP per capita.**

