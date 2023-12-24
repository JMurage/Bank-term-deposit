# Bank-term-deposit

## Introduction
This dataset, titled Direct Marketing Campaigns for Bank Term Deposits, is a collection of data related to the direct marketing campaigns conducted by a Portuguese banking institution. These campaigns primarily involved phone calls with customers, and the objective was to determine whether or not a customer would subscribe to a term deposit offered by the bank.

## About this dataset

The dataset contains various features that provide insights into customer attributes and campaign outcomes. These features include:
*	Age: The age of the customer.
*	Job: The occupation of the customer.
*	Marital Status: The marital status of the customer.
*	Education: The education level of the customer.
*	Default: Whether or not the customer has credit in default.
*	Balance: The balance of the customer's account.
*	Housing Loan: Whether or not the customer has a housing loan.
*	Contact Communication Type: The method used to contact the customer (e.g., telephone, cellular).
*	Day: The day of the month when the last contact with the customers was made.
*	Duration: The duration (in seconds) of the last contact with customers during a campaign.
*	Campaign Contacts Count: Number of contacts performed during this campaign for each customer
```
        - pdays : number days passed since previously contacted form previous campaign
        - poutcome : outcome from previous marketing campaign
```      

## The Task: Explore the Direct Marketing Campaigns datasets with Pandas

![image photo of a bank](images/Bank.jpeg)

Image by <a href="https://risingnepaldaily.com/storage/media/5875/bank.jpg">Nabil</a>

### Data Understanding

Each record (row) in this dataset represents a customer.

Each feature (column) in this dataset is some attribute of that customer. You can view the file `data/data_description.txt` in this repository for a full explanation of all variables in this dataset — 12 columns in total.

We are going to focus on the following features:

**Age**: `Numerical values between 19 and 90`

**Job**: `Managenent, blue-collar, other`

**Marital** : `married, single, other`

**Education**: `secondary, tertiary, other`

**Balance**: `Numerical values `

**Housing**: `Categorical data true, false`

**Loan**: `Categorical data true, false`


## 1. Loading the Datasets with Pandas

Importing Libraries such as:
* `pandas` with the standard alias `pd`
* `matplotlib.pyplot` with the standard alias `plt`

And set `%matplotlib inline` so the graphs will display immediately below the cell that creates them.

* Using pandas to open the files located at `data/bank_main_file.csv`and `data/bank_sub_file.csv` 
* Inspect the contents of the dataframe:
    `print(f'df1 shape: {df1.shape}')`
    `print(f'df2 shape:{df2.shape}')`
* output: `df1 shape: (4521, 17)`
            `df2 shape:(11162, 17)    `

## 2. Combining the dataframes

Combining the dataframe df1 with df2 using the `outer` join
* df3 = df1.merge(df2, how="outer")

## 3. Explore Data Distributions

Write code to produce histograms showing the distributions of `Age`,`Job`, `marital`, `education`, `balance`, `housing`, `loan` e.t.c.
### (a) Age
The `age` of the customer.
`From the Histogram, Majority of customers were of the age between 30 years and 58 years.The most prevalent age range is [30 - 47]`

### (b) Job
The occupation/`employment` status of the customer.
`From the Histogram plot, Majority of customers were in management job category, followed by blue-collar and technicians.`

### (c) Marital status
The `marital` status of the customer.
`The plot shows that Majority of customers were married`

### (d) Education Level of customers
The `education` level attained by the customer.
`From the Histogram ploted, Majority of customers had attained the secondary level education followed by tertiary level.`

### (e) Credit in Default Feature
Whether the customer has credit in default or not.
`since the "no" values is very poor, the default column may not be useful thus it can be ignored.`

### (f) Bank balances of customers
The balance in the customer's account.
`The customers have a average account balance of 1496.43. The distribution has a median of 514 and a standard deviation of 3205.71`

### (g) Housing Loan Feature
Whether the customer has a housing loan or not.
`The housing loan was equally shared by the at 50%`

### (h) Loan Feature
Whether the customer has a loan or not.
`The customer without loan constituted the largets percentage of 86.66%.` 

### (i) Contact Feature
Type of communication used to contact customers.
`Most of the contacts were done using the cellular form of contact`

### (j) Day and month Feature 
Day and month when customers were last contacted.
`contacts were distributed across the days ofg the month but the campaign was more intesified in the in the month of May.`

### (k) Campaign Feature 
Number of contacts performed during this campaign and for this client

### (l) Days passed before previous Campaign (pdays)
number days passed since previously contacted form previous campaign

### (m) Target field 
Has the client subscribed a term deposit?
    `no     8331`
    `yes    4829`

Converting the categorical data to numerical data.
## 4. Explore Correlations

To understand more about what features of these dataset to higher deposit, we look at some correlations.

In the cell below, we print out both the name of the column and the Pearson correlation for the column that is ***most positively correlated*** with `depoit` (other than `deposit`, which is perfectly correlated with itself).
`using a heat map to show the correlation`

 ***most positively correlated*** column: 
    `Strongest +ve Corr:`
 ```  
    duration    0.480934
    previous    0.157287
    pdays       0.143235
    balance     0.127208
 ``` 
 ***most negatively correlated*** column: 
```
    housing    -0.202405
    contact    -0.153109
    campaign   -0.122950
    poutcome   -0.118487
    loan       -0.103877
```