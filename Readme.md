# USA Immigration in 2016
### Udacity Data Engineering Capstone Project


### Overview of this project  
This project is used to build a ETL pipeline with Spark for combining all data related to the immigration of USA in 2016. It builds an ETL pipeline to exact data from different files, and process the data with Apache Spark and build a star schema with a fact table and 3 dimension tables.

### The processes for the project
* Step 1: Scope the Project and Gather Data
* Step 2: Explore and Assess the Data
* Step 3: Define the Data Model
* Step 4: Run ETL to Model the Data
* Step 5: Check the data quality  

### Datasets
All the data files are stored in the data folder in the main directory.

1. **I94 Immigration Data**: This data comes from the US National Tourism and Trade Office. The source of this data is from [link](https://travel.trade.gov/research/reports/i94/historical/2016.html). The table include the immagration information.   
2. **World Temperature Data**: This dataset came from Kaggle. You can read more about it [link](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data). This table include the temperature of different cities in different countries.  
3. **U.S. City Demographic Data**: This data comes from OpenSoft. You can read more about it [link](https://public.opendatasoft.com/explore/dataset/us-cities-demographics/export/). This table includes poulation information for each city.  
4. **Airport Code Table**: This is a simple table of airport codes and corresponding cities. It comes from [here](https://datahub.io/core/airport-codes#data).  
5. **Countries code and airport 3 letters code**: The two tables are from name library file of immigration I94_SAS_Labels_Descriptions.SAS.    

### Fact table

- **Fact table -- fact_immigration**

| Column Name   | Description                                            |
| :------------ | -----------------------------------------------------: |
| cicd          | Record ID                                              |
| i94yr         | 4 digit year                                           |
| i94mon        | Numeric month                                          |
| i94cit        | Contry of citizenship                                  |
| i94res        | Country of residence                                   |
| i94port       | Three letter airport code                              |
| arrdate       | Arrival date in the USA                                |
| i94mode       | Mode of transportation                                 |
| i94addr       | State code                                             |
| depdate       | Departure date in the USA                              |
| i94bir        | Age of Respondent in Years                             |
| i94visa       | Visa codes (1 = Business, 2 = Pleasure, 3 = Student)   |
| entdepa       | Arrival Flag                                           |
| biryear       | 4 digit year of birth                                  |
| gender        | Non-immigrant sex                                      |
| airline       | Airline used to arrive in U.S.                         |
| fltno         | Flight number of Airline used to arrive in U.S.        |
| visatype      | Class of admission legally admitting the non-immigrant |

### Dimension table

- **Dimension table -- dim_countries**  
| Column Name                   | Description                          |
| :---------------------------- | -----------------------------------: |
| code                          | 4 digit code for country             |
| Country                       | Country Name                         |
| AverageTemperature            | Average Temperature for country      |
| AverageTemperatureUncertainty | Uncertaintay of Average Temperature  |

- **Dimension table -- dim_demographics**  

| Column Name                 | Description                                            |
| :-------------------------- | -----------------------------------------------------: |
| City                        | City                                                   |
| State                       | State                                                  |
| Median                      | Meadian age                                            |
| Age                         | Age                                                    |
| Female_Population           | number of female                                       |
| Male_Population             | number of male                                         |
| Total_Population            | number of citizen                                      |
| Number_Veterans             | number of Veterans                                     |
| Foreign_born                | number of citizen born outside of US                   |
| AverageHouseholdSize        | Average of household size                              |
| State_Code                  | Two letter state code                                  |
| AmericanIndian_AlaskaNative | Race                                                   |
| Black_AfricanAmerican       | Race                                                   |
| Hispanic_Latino             | Race                                                   |
| Asian                       | Race                                                   |
| White                       | Race        |   


- **Dimension table -- dim_airports**  

| Column Name  | Description                                                             |
| :------------| ----------------------------------------------------------------------: |
| ident        | Identity ID                                                             |
| type         | Type of airport                                                         |
| name         | Name of airport                                                         |
| elevation_ft | Elevation above the sea level in feet                                   |
| continent    | Continent code                                                          |
| iso_country  | ISO Country Code                                                        |
| iso_region   | ISO Region Code                                                         |
| municipality | municipality                                                            |
| gps_code     | GPS Code                                                                |
| iata_code    | Code of the airport assigned by International Air Transport Association |
| local_code   | Local Code                                                              |
| coordinates  | Coordinates                                                             |  



### How to run  

Please install Juputer **Notebook** and **Spark** before running this script.  

Follw the steps in the file: **Capstone Project Template.ipynb**
 
