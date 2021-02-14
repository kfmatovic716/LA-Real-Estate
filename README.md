## Los Angeles Rental Market Real Estate

### PROJECT DESCRIPTION AND RESEARCH QUESTION

Our client, a major international commercial real estate private investor is looking to add additional rental properties to their portfolio. As part of their preliminary analysis, they have asked to find out: What are the top 10 rental neighbourhoods in Los Angeles and how do they differ for Airbnb vs Regular monthly rental properties?

### Data Overview
We extracted over 3,300 rows of data from the Mashvisor api (documentation here: (https://www.mashvisor.com/api-doc/#introduction), comprising approximately 1,500 rows each for Airbnb and regular rental properties and spanning over 80 neighborhoods. Data download consisted of fields detailing geographic locations of properties e.g. address, city, lat/lng coord, and property specific data including # beds/bths, review counts, occupancy rates (Airbnb), and simple financial data e.g. rental rates by day, week, month etc. We note that Airbnb data was more granular than Regular rental properties, and allowed us to filter on additional data points such as user reviews, occupancy levels etc.

### Data Scrubbing Methodology
We downloaded rental property data from the api for Airbnb and Regular rentals separately, saved them to csv files and then removed extraneous columns (e.g. room type capacity, amenities etc) and renamed the columns of both datasets so they could be stacked together. Once this was completed, we mapped the existing property type names to a smaller set in order to simplfy our analysis and then ordered/grouped the properties by neighborhood starting with the highest price. We also added a column comparing monthly prices across Airbnb vs regular rental properties by multiplying nightly rental rates of Airbnb properties by the approximate number of days they would be rented over a month (18 days in a month, computed by observing annual occupancy rate percentages). Finally we removed "Other" as a property category owing to a lack of information about the properties.

### Python Libraries
Pandas, Matplotlib, Seaborn, gmap, csv gmaps was used to plot geographic locations of properties/neighborhoods across LA. Pandas used for data manipulation. Graphs generated in Matplotlib and Seaborn.

### Research Questions/rationale
We investigated the following questions as a way of exploratory analysis of the data: Where are the properties located on a map of Los Angeles? Are there differences between Airbnb rentals vs Regular? How are the properties grouped by type e.g. house, apartment etc?

### Analysis

1. Data is heavily skewed to the right for both AirBnb and Regular Rentals in terms of monthly rental price. Regular renters were paying a monthly average of $2,800 compared to $3,400 for AirBnb renters. As the histograms illustrate, the majority of the Regular renters were paying less than $5,000 per month, compared to the majority of AirBnb renters who were paying less than $6,000 per month, 20% higher than what Regular renters pay. 

2. Based on the boxplot and pie chart illustrations, there were 25 AirBnb rental outliers who were paying greater than or equal to the monthly rental price of $6,275. Pacific Palisades dominates the AirBnb outiler population by 32%. This neighborhood seem very appealing to invest in due to its elevated monthly rent. However, as observed in the AirBnb histogram, the amount of renters drop at approximately $6,000. This implies that occupancy can be low, which directly affects profitability.

3. The comparison of average monthly rent by neighborhood bar graph shows that Venice & Studio City were among the neighborhoods with reasonable average monthly rent from a low $3,342 to a high $4,588. This average monthly rent range is much more affordable by the majority of the population of AirBnb renters and can provide the investor stability in income due to higher probability in occupancy. In addition, since the variation of average monthly price for each rental option for these neighborhoods are low and insignificant (i.e. approximately 4% in Venice), an investor can have the flexibility to rent the property for AirBnb or Regular rental option.

### Conclusions

1. There is greater potential in earning a better income when investing in AirBnb rentals because a landlord or an investor can charge higher monthly rent.
2. AirBnb rentals in Pacific Palisades will not have a better outcome in terms of earnings due to the high monthly rent and low occupancy rate.
3. The average monthly rental price of Venice and Studio City are desirable because they provide more stable income, higher occupancy rates and flexibility in rental options.


