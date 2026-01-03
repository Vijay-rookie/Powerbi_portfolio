# Zomato Analysis using power BI 

## Project Overview 
<br>
This project analyses zomato data using <b>Power BI</b> to identify trends in restaurant performance, customer rating and location based insights. The dashboard is also made which help stakeholder to understand business trends and pattern to make data-driven decision. It helps in analysing Zomato presence and its market shre around the world by uncovering insights related to restaurants, cities, regions, customer rating, cuisine choice,etc. 

## Data set
-**Fact Table.xlsx** - Contains data related to Average cost, Average rating, price range, online delivery status,etc.
- **Africe.xlsx** - Regional Resturant data of Africa.
- **Asia.xlsx** - Regional Resturant data of Asia.
- **Europe.xlsx** - Regional Resturant data of Europe.
- **NAM.xlsx** - Regional Resturant data of North America.
- **SAM.xlsx** - Regional Resturant data of South America.
- **Oceania.xlsx** - Regional Resturant data of Australia and New Zealand.
- **Country-code.xlsx** - Countries name and their respective codes.

## Data Cleaning and preparation
- The first step is to open the excel files one by one in <b>power query editor</b> and then rename some countries, take care of null cloumns and rows.
- After that, In all files except country-code and fact table, a new column is created by the name of <b>Region</b>.
- In my 3rd step, I <b>Append</b> all continent files through Append Query as new and named it "Business Countries".
- Then a craeted two new table, one is "Cuisine table" and other is "KPIs table".

## Key KPIs
- Number of Restaurants globally.
- Average ratings.
- Top Restaurants.
- Average cost.
- Cuisine Count.
  
## Tools and Skills Used 
- Power BI
- Power Query editor (Data cleaning and transformation)
- Interactive dashboard and KPIs
- DAX
- Data Modeling

## Key Calculations

Cuisine Table = SELECTCOLUMNS('Business Countries', "Restaurant ID", 'Business Countries'[Restaurant ID], "Cuisines", 'Business Countries'[Cuisines])
<br>
Rating Color = SWITCH( TRUE(), KPIs[Aggregate rating]>4.5, "Dark Green",KPIs[Aggregate rating]>=4, "Green", KPIs[Aggregate rating]>2 , "Red", "Black")
<br>
Cuisine Count = COUNT('Business Countries'[Cuisines])
<br>
Restaurant Count = COUNT('Business Countries'[Restaurant ID])
<br>
Average Rating = AVERAGE(KPIs[Aggregate rating])

## Dashboard Preview

### Report overview

![Report overview](Screenshot_2026-01-03_203508.png)

### Visualization

![Visualization](Screenshot_2026-01-04_010427.png)

## Live Dashboard

<iframe title="Zomato" width="600" height="373.5" src="https://app.fabric.microsoft.com/view?r=eyJrIjoiYmY2MTA2ZDktOTEwNS00NzJkLTg0NzYtMDAyNjNhYWQwYTgyIiwidCI6ImE0MmRjZTc5LTI2ZTktNDNiZC05MjFjLTY0OGUwZTYxYjAyMCJ9" frameborder="0" allowFullScreen="true"></iframe>

