# CMPUT-191-Assignment-3 - Flour Pricing Index

# Task
Our task was to create a purchasing power parity index for a good of our choice. You can read about purchasing power parity here: https://en.wikipedia.org/wiki/Purchasing_power_parity. We chose to create an index for flour pricing. We have decided that flour pricing is important to analyze because it is a basic, yet essential good that we can use to compare any country of our choosing. 

# These are the steps that we took in order to create our wheat pricing index!

## 1. Importing pricing data on the flour product into a table from 'https://www.globalproductprices.com/rankings/flour_prices/'
Here we scraped out data from the source using beautiful soup and then cleaned the data into a table containing the countries and their prices per 1kg of flour. Here is a look at the table we have created: 
![image](https://user-images.githubusercontent.com/115324925/205714291-55218f0b-ff33-4d93-b6f5-45fe81fa5d73.png)

## 2. Next, we had to factor in the local tax rates to our calculations!
In this step, we found a csv file from https://www.kaggle.com/datasets/mathurinache/list-of-countries-by-tax-rates of local tax rates for which we will apply to the flour pricing to obtain the after-tax pricing for flour in each country. We then joined the table from step 1. Here is what the table looks like: ![image](https://user-images.githubusercontent.com/115324925/205717700-252e9920-e8c6-4fab-a82c-6d6b0fd5f7aa.png)

## 3. We then had to find the exchange rates (by currency code) for each country in our analysis.
We were able to find and scrape from an API to obtain a table of the exchange rates for each country and the currency codes used to define each currency. This is the API we used:https://api.exchangerate.host/latest. Because the exchange rates were in USD, we had to do some simple data manipulations to obtain a column converted into CAD. We then found scraped this table https://www.iban.com/currency-codes and after doing some cleaning, we joined the tables into one singular table containing country code, country, exchange rate in CAD and exchange rate in USD. Here is what that table looks like: ![image](https://user-images.githubusercontent.com/115324925/205718729-e83b5b20-e98c-40a7-83cd-b0e5c5d043ad.png)

## 4. Next, we imported the data on the external factors which we believe may have an impact on the price discrepancies between the different countries.
The two external factors that we chose to examine are temperature, and wheat production. In order to do our analysis, we scraped a table from https://listfist.com/list-of-countries-by-average-temperature which shows the average temperatures (in celcius) of each country between 1991 and 2020. We also did the same for our second external factor (wheat production) which came from https://en.wikipedia.org/wiki/International_wheat_production_statistics. We then joined all of our tables at this point which you can see here:
![image](https://user-images.githubusercontent.com/115324925/205745316-529356ae-1620-42f2-b99d-6fb0e20e16fc.png)

