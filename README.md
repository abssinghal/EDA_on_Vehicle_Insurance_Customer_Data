# EDA_on_Vehicle_Insurance_Customer_Data
A company has customer data that contains 8 columns of customer details and another table having name customer_policy data contains the policy details of the customer.   The company intends to offer some discount in premium for certain customers. To do that they ask their Data scientist team to get some information

1. Add the column names to both datasets:

i. Column Name for customer details table:

           customer_id, 

           Gender,

           age, 

           driving licence present,

           region code, 

           previously insured, 

           vehicle age 

           and vehicle damage, in respective order. 

ii. Column Name for customer_policy table:

           customer_id, 

           annual premium (in Rs), 

           sales channel code, 

           vintage and response. 
           
           
![image](https://user-images.githubusercontent.com/78210738/212067000-56cfff6a-88dc-446c-8a9a-8a97ac85ee78.png)

2. Checking and Cleaning Data Quality:

i. Null values

Generate a summary of count of all the null values column wise
Drop Null values for customer_id because central tendencies for id’s is not feasible.
Replace all null values for numeric columns by mean. 
Replace all null values for Categorical value by mode.
![image](https://user-images.githubusercontent.com/78210738/212067223-540846f8-57cf-44d1-a7b6-727cffcafca2.png)

ii. Outliers

Generate a summary of count of all the outliers column wise
Replace all outlier values for numeric columns by mean. 
(Hint1: for outlier treatment use IQR method as follows:

For example: for a column X calculate Q1 = 25th percentile and Q3 = 75th percentile then IQR = Q3 – Q1 ) then to check outlier, anything lower than a Q1 – 1.5IQR or greater than Q3 + 1.5 IQR would be an outlier

Hint2: For getting percentile value, explore pd.describe() function)

![image](https://user-images.githubusercontent.com/78210738/212067341-b867c502-a234-4b74-9b95-8ba6c9db536c.png)
![image](https://user-images.githubusercontent.com/78210738/212067426-3c6bf67e-6017-4e16-871e-1d08eacbe3a2.png)
![image](https://user-images.githubusercontent.com/78210738/212067462-2ab50c88-2297-4338-a29b-54c0a9a7ddae.png)


iii. White spaces

Remove white spaces
iv. case correction(lower or upper, any one) 

v. Convert nominal data (categorical) into dummies 

for future modeling use if required
vi. Drop Duplicates (duplicated rows)

![image](https://user-images.githubusercontent.com/78210738/212067532-f9b3376b-7ef4-400a-ad2f-3dec12477b9b.png)

3. Create a Master table for future use. Join the customer table and customer_policy table to get a master table using customer_id in both tables.

(Hint: use pd.merge() function)
![image](https://user-images.githubusercontent.com/78210738/212067582-75a39480-8ed1-40b0-be81-b637955d6901.png)

4. Company needs some important information from the master table to make decisions for future growth.They needs following information:

 i. Gender wise average annual premium
![image](https://user-images.githubusercontent.com/78210738/212067623-661b08e7-0c3c-46f2-9494-db5ffe912a55.png)

ii. Age wise average annual premium
![image](https://user-images.githubusercontent.com/78210738/212067661-a97dfda3-15f6-46cf-b0c4-252e38b84d29.png)

iii. Is your data balanced between the genders?
![image](https://user-images.githubusercontent.com/78210738/212067690-c4321df0-5855-469d-862b-10cb17a686d4.png)

          (Hint: Data is balanced if number of counts in each group is approximately same)

iv. Vehicle age wise average annual premium.
![image](https://user-images.githubusercontent.com/78210738/212067717-7f553655-44a7-43de-870f-9bcae4b5fa91.png)

5. Is there any relation between Person Age and annual premium?

Hint: use correlation function (Correlation describes the relationship between two variables). 

Correlation coefficient < -0.5           - Strong negative relationship

Correlation coefficient > 0.5            -  Strong positive relationship

0.5 < Correlation coefficient < 0.5   - There is no relationship. 
![image](https://user-images.githubusercontent.com/78210738/212067786-8292ee5e-6d40-467a-aec9-7133287807da.png)
