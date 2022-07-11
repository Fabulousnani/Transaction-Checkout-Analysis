![—Pngtree—online shopping payment transactions_5342232](https://user-images.githubusercontent.com/91569726/176081461-8c0e6610-4f24-44ad-b20d-5af3754a6b63.png)
# Transaction-Checkout-Analysis
_______
### Project Description
_______
 The Transaction checkout data is a CSV file of 3255 rows with four columns the "I.d", "Country_code," "Currency"  and "Status" making up the transaction records. . "Status" indicates whether the transaction was successful or not. "Currency" provides the currency Subscribers tried to pay with. "Country_code" indicates the country the customer's card is from.
 I extracted,cleaned,wrangled and transformed the data to get it  ready for analysis. I used Excel and Microsoft PowerBi  to perform the  ETL(Extract, transform and Load),Data query, EDA(Exploratory data analysis) and Visualization.
________
### Problem statement
   With Nigeria making the majority of the subscribers.  Premium subscribers however have the option of paying in Nigerian Naira (NGN) or United States Dollars (USD) Using the Card payment Method where NGN is the default payment Currency.
  International subscribers' payments fail more often, and we want to know what happens if a customer tries to pay in a currency that doesn't match their card's country.
________
### Research Question
 Below are the two research questions from the Problem statement:
If someone with a non-Nigerian card tries to pay in Naira, are they more likely to have a failed transaction than if they paid in USD? 
How does that compare against people paying in Naira with Nigerian cards?
______
### Hypothesis
Null hypothesis (Ho):The use of Non-Nigerian cards to pay in Naira(NGN) is not more likely to have a Failed transaction.
Alternate hypothesis (H1):The use of non-Nigerian cards to pay in Naira(NGN) is more likely to have a Failed transaction.
________

### Data Design/Methodology 
• I extracted the data from the google drive and loaded it  to my workspace.

• I made use of Excel to explore the raw file  then PowerBi for Extract, transform and Load(ETL), DAX (Data Analysis Expression), Data Queries, exploratory data analysis (EDA) and Visualizations.

• Took measures to clean the data as it was a bit dirty; I removed duplicate records, removed empty records, and several “distinct” functions to get the Unique records and Data. This process  reduced the number of rows from 3276 to 3255.

• During the cleaning I observed that transactions with "Abandoned" status  have "null" as Country_Code. This might be because the transaction didn't continue or proceed at some point.

• In the raw file , I  noticed that there was no column specifying the Card type used for the transactions in accordance with the country the customer's card is from. Then it is assumed that subscribers outside Nigeria use a Non-nigerian card for transactions and those with country_code= NG use Nigerian cards whereas others like "Abandoned" status with "null" country_code use Unspecified cards. I used the Data analysis expression (DAX) to Query the Country code column to arrive at the conditional measure(card_Type) where we have Nigerian cards,Non-nigerian cards and Unspecified cards. These were used to Filter and dig deeper into the analysis for more Insights
##### DAX Reference:
Card_Type=SWITCH('checkout_transactions'[country_code],"NG","Nigrian-cards","NULL","Unspecified-cards","Non-nigerian cards")
______
### FINDINGS AND DATA ANALYSIS

Figure 1.0

Overall transactions by status

With a  Total number of 3255 transactions "Abandoned' has the highest number of transactions with 45.64% of the overall transactions. We had little reversed transactions at 1.26% as opposed to failed and Success which were 13.03% and 41.08% respectively.




