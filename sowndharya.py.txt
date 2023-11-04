
QUES 1:
Revenue=127804.31
cogs=96321.56
gm=((Revenue-cogs)/Revenue)
print("Their overall gross margin for their business",gm)

QUES 2:
vendor=max(1555.59,1296.98,6370.67,6903.31,1616.14,1217.95,4961.95,253.74,4266.74,3040.62)
print( "the vendor who is the most profitable is vendor 4",vendor)

QUES 3:
CUSTOMER=max(5310.57,844.83,736.55,1528.8,1273.27,1735.22,875.45,5791.64,1337.88,2713.96)
print( "the customer who is the least profitable is customer 8",CUSTOMER)

QUES 4:
data = [
    {"date": "21/08/23", "vendor": "Vendor6", "customer": "Customer7", "revenue": 4029.52, "cogs": 3172.84},
    # ... (all other data entries)
    {"date": "27/08/23", "vendor": "", "customer": "", "revenue": 5173.93, "cogs": 96321.56}
]

from datetime import datetime

day_profits = {}
for entry in data:
    date_string = entry["date"]
    date_object = datetime.strptime(date_string, "%d/%m/%y")
    day_of_week = date_object.strftime("%A")
    profit = entry["revenue"] - entry["cogs"]
    day_profits[day_of_week] = day_profits.get(day_of_week, 0) + profit

most_profitable_day = max(day_profits, key=day_profits.get)
least_profitable_day = min(day_profits, key=day_profits.get)
print("Most profitable day of the week: {}".format(most_profitable_day))

QUES 5:
data = [
    {"date": "21/08/23", "vendor": "Vendor6", "customer": "Customer7", "revenue": 4029.52, "cogs": 3172.84},
    # ... (all other data entries)
    {"date": "27/08/23", "vendor": "", "customer": "", "revenue": 5173.93, "cogs": 96321.56}
]

from datetime import datetime

day_profits = {}
for entry in data:
    date_string = entry["date"]
    date_object = datetime.strptime(date_string, "%d/%m/%y")
    day_of_week = date_object.strftime("%A")
    profit = entry["revenue"] - entry["cogs"]
    day_profits[day_of_week] = day_profits.get(day_of_week, 0) + profit

most_profitable_day = max(day_profits, key=day_profits.get)
least_profitable_day = min(day_profits, key=day_profits.get)
print("Least profitable day of the week: {}".format(least_profitable_day))

QUES 6:
Calculate 3-day average of daily gross profit
import pandas as pd

# Load the data from the CSV file
data = pd.read_csv("sales_data_2.csv")

# Convert the 'Date' column to datetime type
data['Date'] = pd.to_datetime(data['Date'])

# Calculate daily gross profit
data['Gross Profit'] = (data['Selling price'] - data['Buying price']) * data['Quantity sold']

# Calculate 3-day rolling average of daily gross profit
data['3-day Average Gross Profit'] = data.groupby('Date')['Gross Profit'].rolling(window=3, min_periods=1).mean().reset_index(0, drop=True)

# Print 3-day average of daily gross profit
print(data[['Date', '3-day Average Gross Profit']])

QUES 7:
Analyze the 3-day trend changes over the time period
# Calculate total profit per vendor and customer
vendor_profit = data.groupby('Firm bought from')['Gross Profit'].sum()
customer_profit = data.groupby('Customer')['Gross Profit'].sum()

# Identify vendors and customers with low profitability
low_profit_vendors = vendor_profit[vendor_profit < vendor_profit.median()]
low_profit_customers = customer_profit[customer_profit < customer_profit.median()
print("Low Profit Vendors:")
print(low_profit_vendors)
print("\nLow Profit Customers:")
print(low_profit_customers)


QUES 8: 
Calculate percentiles for buying and selling prices
# Calculate percentiles for buying and selling prices
buying_price_percentiles = data['Buying price'].describe(percentiles=[0.25, 0.50, 0.75])
selling_price_percentiles = data['Selling price'].describe(percentiles=[0.25, 0.50, 0.75])

print("Buying Price Percentiles:")
print(buying_price_percentiles[['25%', '50%', '75%']])
print("\nSelling Price Percentiles:")
print(selling_price_percentiles[['25%', '50%', '75%']])

QUES 9&10:

Analyze price distribution against percentiles
# Check how often prices fall below 25th percentile or above 75th percentile
below_25th_percentile = data[data['Selling price'] < selling_price_percentiles['25%']]
above_75th_percentile = data[data['Selling price'] > selling_price_percentiles['75%']]

print("Number of transactions with selling price below 25th percentile:", len(below_25th_percentile))
print("Number of transactions with selling price above 75th percentile:", len(above_75th_percentile))



QUES 11:

The statement that "vendor 4 has to be honored" implies that SYA must fulfill the obligations or commitments to vendor 4. Vendor 4 is the most profitable vendor with the profit of 6903.31.So, on seeing the cost of goods sold,if honoring vendor 4 we requires purchasing goods and services for them at a certain cost,it will affect your COGS,which is a key component in calculating gross margin. if vendor 4 offers favourable terms or competitive prices,it may positively impact your gross margin.

QUES 12: 
The vendor the company should tie up should posses low COGS,quality and reliability,supplier exclusivity,demand and price power, long term partnership, supplychain efficiency, market conditions, economies of scale.
Gross Margin= ((Selling Price-COGS)/ Selling price) ×100%
So, we choose vendor 6 for a strategic tie-up with the goal of achieving the highest gross margin involves several considerations. 
The theoretical max margin the firm could have from that branch is 68.69072 % by vendor 6.

QUES 13
If you increase the price of Sapota by Rs. 1, and the quantity demanded decreases by, for example, 2%, you would have a percentage change in price (
P) of +1% and a percentage change in quantity demanded (
Q) of -2%.
If you decrease the price of Sapota by Rs. 1, and the quantity demanded increases by, for example, 3%, you would have a percentage change in price (
P) of -1% and a percentage change in quantity demanded (
Q) of +3%.
Using these values, you can calculate the price elasticity of Sapota for that branch as follows:
Price Elasticity of Sapota=% Change in Quantity Demanded / % Change in Price
Price Elasticity of Sapota= % Change in Price/ % Change in Quantity Demanded
?
Price Elasticity of Sapota=-2% /1% 
=-2
Price Elasticity of Sapota= 1%/ -2%
?=-2

This would mean that the price elasticity of Sapota for that branch is -2. In practical terms, a price elasticity of -2 suggests that Sapota is relatively inelastic, meaning that changes in its price have a smaller effect on the quantity demanded. A 1% increase in price leads to a 2% decrease in quantity demanded, and a 1% decrease in price leads to a 2% increase in quantity demanded. In other words, consumers are less responsive to price changes for Sapota in this branch.










































