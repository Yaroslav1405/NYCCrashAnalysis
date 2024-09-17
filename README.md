# Introduction
New York City, one of the busiest urban environments in the world, is home to millions of vehicles, cyclists, and pedestrians sharing its streets daily. With such a high concentration of traffic, the city experiences a significant number of vehicle collisions each year. It is very crucial to analyze crash data from NYC to identify possible patterns, understand contributing factors, and improve overall road safety. 

Did you know that the _second_ biggest collision location in NYC is off_street? (parking lots, sidewalks, etc.)
Or that the most collisions happen in Brooklyn? Well, you could guess it, but do you think Brooklyn also has the biggest and the most fatal collisions? 
This, and much more we will explore in our analysis today.

Our dataframe contains these columns (does not include some feature-engineered columns):

- _crash_date_ - date when collision occurred;
- _borough_ - district where collision occurred;
- _zip_ - zip-code of the district where the collision occurred;
- _location_ - latitude and longitude where the collision occurred;
- _on_street_name_ - the name of the street where the collision occurred;
- _cross_street_name_ - name of the cross street of collision(if intersection);
- _off_street_name_ - name of the street where collision occurred(if sidewalk, parking, etc.);
- _persons_injured_ - total number of people injured in the collision(includes all next categories);
- _persons_killed_ - total number of people killed in the collision(includes all next categories);
- _pedestrians_injured_ - number of pedestrians injured;
- _pedestrians_killed_ - number of pedestrians killed;
- _cyclist_injured_ - number of people on bicycle injured;
- _cyclist_killed_ - number of people on a bicycle killed;
- _motorist_injured_ - number of people on motor vehicle injured;
- _motorist_killed_ - number of people on a motor vehicle killed;
- _contributing_factor_vehicle_1/2/3/4/5_ - factor that caused vehicle _num_ to collide; 
- _collision_id_ - id number of collision;
- _vehicle_1_type_ - vehicle type of the first car in a collision (same applies to other categories for vehicle_type);
- _crash_hour_ - time when the collision occurred rounded to the closest hour;
- _crash_date_year_month_ - year and month when the collision occurred.

### **Note:**

This project includes two versions of data analysis:

  - A version with regular static graphs to access straight from github;
  - A version with interactive graphs that can be explored in more detail.
    
To view interactive graphs, you can use NBViewer (https://nbviewer.org/) by pasting the following link(link to notebook file from github): https://github.com/Yaroslav1405/NYCCrashAnalysis/blob/main/nyc_crash_analysis.ipynb

# Main Stages 
This project was utilized using Python frameworks such as Pandas, Numpy, and Plotly. The data was sourced from the **Motor Vehicle Collisions - Crashes** dataset, available on the U.S. government’s open data platform _data.gov_, which provides over 10 years of vehicle collision data across the city.

1. Data Preprocessing
Before any analysis, the data had to be preprocessed, so this was our first step after loading it. The data had a lot of NaN values, so we had to deal with them. Also, there were some unnecessary columns that we dropped, and some other data points were empty so we had to find and fix them. Another data preprocessing that we've done was fixing the vehicle type naming. Since every police official have their own writing style (someone use title, someone use all capital letters or vice versa), the vehicle type column contained around 1700 unique names. We have not fixed all of them, but found top 5 and performed quick fixes.

2. Exploratory Data Analysis
Initially, we generated and analyzed some basic summary statistics, visualized the distribution of key variables, and identified some trends. This helped us to set our focus later to more specific analysis, such as borough investigation, contributing factors, road user categories, and much more. 

3. Data Transformation
We applied some transformations to the data to enhance the quality of the analysis. Date formats were standardized, new variables such as day of the week, hour of the crash were created to provide additional insights. 

4. Visualizations
Throughout the analysis, various visualizations were used to represent the data, such as:
    - Distribution charts for fatalities by month, collision locations using pie charts;
    - Distribution of different types of collisions, vehicle types, contributing factors, etc. using bar charts;
    - Geographical distribution of collisions and their intensity using maps;
    - Line charts to track the trends of collisions over time;
    - Radar chart to track total collisions by day.

# Conclusion
Throughout the analysis, we discovered a lot of interesting insights. Brooklyn has the most collisions overall, but the Bronx and Manhattan are the first in high-impact collisions involving pedestrians and cyclists. Notably, motorists are injured at a rate four times higher than pedestrians, yet pedestrian fatalities exceed motorist fatalities in four out of the five boroughs. These findings represent only a portion of the insights uncovered in the full analysis. They highlight the complexity of traffic dynamics across the city. Some findings were unexpected or appeared controversial, while others were more straightforward. However, all these results emphasize the need for further investigation into road safety and traffic regulations in order to mitigate future injuries and fatalities.

# Future Work
To improve our analysis, the first thing should be to limit records to only a particular time period (e.g., the last 5 years) and this would present the most accurate results, and the insights drawn will still be up to date. Fixing all vehicle types, to provide full analysis for all distinct categories. Also, a good thing is to inspect the top 10 places of collisions or high-impact collisions with a street view tool using external methods. It can be very useful to understand what could be a potential reason for these collisions, and what could be done to prevent it. 
Generally, there are a lot of improvement areas and additions that can be done in the future. Exploring such datasets can be useful to prevent collisions in the future. 
