
## Summary:
The purpose of this project and related data is to track the five main macronutrients and their related caloric values over a two-week period. The basal metabolic rate (BMR) and average calories burned were subtracted from this to find net calories each day. An initial dashboard to track macronutrients was created as well as a  secondary dashboardmallowing for individual BMI, BMR, and net calories to be calculated were created. The final visualization is hosted in Tableau:https://public.tableau.com/shared/4SSQ9GB4D?:display_count=n&:origin=viz_share_link

## Dataset:
Daily food reports were collected over a two week period using my Net Diary and exported as a csv file. Only the main five categories Calories, Fat, Carbs, Protein, and fiber were kept as fields with each row representing a day. All categories except calories were recorded in grams

Movement data was collected using the StepsApp and exported as a csv file. Data consisted of  date, steps, duration, distance, calories, and floors. Duration, calories, and floors were measured in seconds, meters, kcals, and 3 meter increments respectively.

Water intake data was recorded using the Water Reminder app and transferred into an excel file for processing. Fields consisted of date and water intake measured in ounces with each row representing a day.

## Introduction:
In order to upkeep basic bodily functions such as breathing and body temperature, the human body burns calories. This varies between individuals and is known as the basal metabolic rate (BMR). This can be calculated once age, weight, and height are accounted for. This, in addition to the daily calories burned through exercise, accounts for the calories burned each day. In order to maintain homeostasis, an equivalent amount of calories must be consumed on a daily basis.

## Methodology:
The MyNetDiary app was used in order to track the amount of calories consumed and the related macronutrient breakdown. The water reminder app was used to track water intake. Lastly, the StepsApp app was used to track the number of steps, elevation, and duration of movement over the period. Data was exported as CSV files from the respective apps and uploaded to Google BigQuery as individual tables named Food, Steps, and Water for querying and exploratory data analysis using SQL. columns in the food table were aliased for clarity to indicate grams. Duration and distance were converted to minutes and miles, respectively, in the steps table for clarity, and a steps goal column was added. Columns in the water table were aliased to indicate ounces, and a water goal column was added. All tables were then joined and exported to Tableau for visualization.

Gauges were created based on a goal of 55% of calories coming from carbohydrates, 35% of calories coming from protein, and 20% of calories coming from fat. An independent fiber gauge was created with a goal of 38 grams of fiber a day. Step, calorie, and water metrics were broken down and measured against goals. Basal metabolic rate for men was calculated using the formula 88.362 + (13.397 x weight in kg) + (4.799 x height in cm) - (5.677 x age in years). This was added to active calories burned, which was calculated using the formula kcal = time [minutes] × ((MET × 3.5) × weight [kg] ÷ 200) to estimate the calories burned in a day. Weight change over the period was documented by converting the net calories each day to pounds and adding it to the starting weight for the day. Height was recorded and multiplied by a factor of .415 to find approximate stride length. A second dashboard was created to calculate BMR, BMI, active calories burned, and caloric needs for an individual based on their height,weight,sex, and minutes spent walking.


## Results:
The primary dashboard allowed for better understanding and tracking of daily consumption goals for the five main micronutrients: carbohydrates, protein, fat, water, and fiber. In addition to this, a baseline activity level could be observed.This aided in the creation of a plan for long-term weight gain and sustained activity. The secondary dashboard allows for a snapshot of net calories on a given day based on the individual.
