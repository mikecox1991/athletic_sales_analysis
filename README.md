# athletic_sales_analysis
Module 5 
Combine and Clean the Data
----------------------------------------------------------------------------------------------------------------
This module was difficult for me at first but we got through this! The beginning of the code
we import the CSV files in and start with read_csv. After we see the data for sales_2020_df 
and sales_2021_df we see what we are looking at as far as the table data. 
Here we are looking at the types of data we are using for both tables with .dtypes, we see invoice_date
is an object and not a 'datetime' data type. 
We are combining our dataframes together, using concat to combine both sales_2020_df and sales_2021_df
into one table. We ignore the index and then reset_index to look at our new index column. I looked at .head(20)
to look at the first 20 rows of data for myself. We check if there are any null columns in the combined tables,
which I did not see anything. The next three steps are verify invoice_date data type 'object', change the data 
type to datetime using pd.to_datetime. Then confirm the data type took and we see invoice_date 'datetime64[ns]'
which is correct for us.

Determine Which Region Sold the Most Products
----------------------------------------------------------------------------------------------------------------
This was a good exercise for these next couple sections because its repetitive using the .pivot_table and 
.groupby functions and reinforcing our knowledge of how to use these corrctly. For this section we are 
using the .groupby function, group the columns by region, city, and state, and finding the sum of all three
in one column of total sales. Then we rename 'units_sold' to 'Total_Products_Sold'. After we sort the values
in descending order and print top 5 results. We do the same exact sequence but with pd.pivot_table and set the
table up using index to region, state, city. Values to units_sold and aggfunc to sum. We rename units sold and 
then sort_values by descending order and print. 

Determine Which Region had the Most Sales
----------------------------------------------------------------------------------------------------------------
This is the same sequence as previous, we start the section by using .groupby using the index of region, state,
city; .agg to find the sum of total sales. we .rename total_sales to Total_Sales, sort_values using total_sales
and print the top five results. The same thing happens with the pivot table, use the dataframe, index using
region, city, state and aggfunc as sum. we rename the column and then sort_values of Total_Sales then 
descending order and print top 5 results.

Determin Which Region had the Most Sales
----------------------------------------------------------------------------------------------------------------
Here we do the samething determine which retailer has the most sales. We add retailer into the index with region, 
state, city then we find the sum of all the values with the agg function. Rename the columns of total sales to 
Total_Sales, sort values by Total_Sales then print the first five in the dataframe. We create the samething scenerio 
with the pivot_table and print out the first five items. 

Determine which Retailer Sold the Most Women's Athletic Footwear
----------------------------------------------------------------------------------------------------------------
We want to filter the data to see only Women's Athletic Footwear, for this I used .loc of the product column 
then found every row == "Women's Athletic Footwear". After we print the results and the table is showing womens 
footwear only as the product. After this we runt he same sequence for the pivot_table, but using the groupby 
function we gorup by retailer, region, state, and city then use agg to find the sum of all units_sold.
Rename the units sold to "Womens_Footwear_Units_Sold" and then sort values in descending order. 

Determine the Day with the MOst Women's Athletic Footwear Sales
----------------------------------------------------------------------------------------------------------------
Here we are using the womens_shoe_df, creating a new pivot_table and saving the new table under womens_day_units.
We create pivot_table using the index as invoice_date and values as total_sales then aggfunc as sum. We rename the 
column as Total_Sales and print the results. From there we resmaple the table using 'D' for days and sorting by the 
descending order to find the top 5 values. After that we resample again using 'W' for weeks find the sum for each 
week of sales then sorting the values in descneding order to find the top values. 









