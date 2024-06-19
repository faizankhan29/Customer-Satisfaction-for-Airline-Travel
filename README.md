# Customer Satisfaction for Airline Travel

The aim of this project is to analyze trends in customer feedback of airport and airline experiences. 

First dataset context:
Customers have given their feedback in a variety of airline trips. The problem we are having has to do with customer satisfaction, there are many users that have been a long time with the airline and have shown dissatisfaction and likewise those users that are not loyal have also showed dissatisfaction with the service provided. It would be interesting to understand the role some variables play in the satisfaction result for these trips.
Second dataset context:
Airport customers have given feedback on a variety of features of the airport. For each of the features customers provide their level of satisfaction and also give an overall satisfaction. The problem we have is that there are many features in which customers show a dissatisfaction with the value provided by the airport; it would be interesting to understand which variables are the most important to the overall customer satisfaction.

## Description of the dataset

The first dataset has 129,880 records and has 23 variables that were measured per trip as detailed below:

<img width="834" alt="Screen Shot 2024-06-18 at 10 33 40 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/1afe19f7-f0ba-4133-9538-361e42259994">

The data was included in the source in 2020 and the information was anonymously given. The name for the airline used for this example is Invistico airlines. The rows represent the individual customer feedback, and the column names are the measures that capture the
customer related information as well as their experience of travelling with the company including how they have rated several airplane features. The columns also mention details about the flight that the customer has taken, as well as features of the particular airplane.
The second dataset has 3501 records and has 37 variables that were measured per customer as detailed below:

<img width="877" alt="Screen Shot 2024-06-18 at 10 34 23 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/638f53a5-9165-42f5-a879-1ae5e3d27a63">

The data was first created for use in 2020. The information comes from customer surveys in Austin-Bergstrom airport. The surveys were conducted from 2015-2017 and are reported per quarters. The rows represent individual customer feedback and the columns detail the users overall satisfaction in many variables such as restaurants for example.

First dataset
Task a
As we can see in the image below, these are the number of missing values per column

<img width="455" alt="Screen Shot 2024-06-18 at 10 39 28 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/d3eca9b3-1ce9-4f1f-938b-ba9973f9ed22">

Given that the dataset is quite big and 393 ends up only being 0.3% of the total rows we have decided to drop the rows with this missing values.
Task b
The following image shows the count per class for the satisfaction variable

  <img width="229" alt="Screen Shot 2024-06-18 at 10 39 47 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/101c953b-12b0-4491-836c-86eafdf1a37e">

Task c
 After validating the data types, they are all the right type of variable. We have classes for our categorical values and ordinal values for our ratings.
 
 <img width="617" alt="Screen Shot 2024-06-18 at 10 40 10 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/c36a3826-6bff-41a1-8483-a70562f9bf7e">

Second dataset
Task a
Below we can see the number of missing values per column we have for the airport customer satisfaction dataset

<img width="381" alt="Screen Shot 2024-06-18 at 10 40 37 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/eb3c35be-cc0e-4318-97ae-80da303001e4">

 Since we want to use the Overall satisfaction column as our classifier, we will drop the 172 rows which don’t have a value since they only make up a 5% of the data.
On the other hand we will impute the rest of the columns with the mode (given that as seen from the histograms, the data is very skewed) to make up for the missing values in each of the columns. We wish to keep them so as to not drop any more information that will come in handy for the classification task.

Task b
The following shows the count per label. It is important to note that users that gave a rating of 4 or 5 are classified as satisfied; all the other have been classified as not satisfied

<img width="176" alt="Screen Shot 2024-06-18 at 10 40 51 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/95ceac78-d02d-4bfe-919f-de5fd1f43ebf">

Task c
  After observing all the variables we see that they have the correct type needed for our classification

<img width="478" alt="Screen Shot 2024-06-18 at 10 41 05 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/19bd7034-6b83-4056-ab25-9699fa04bd9b">

## Decision on keeping the datasets separate
We have decided to keep both the datasets separate as the questions answered from each data set can be answered by using the data in each separately. Both have different numbers of rows and columns, which will make it harder for the information to be merged. For data set one, we will predict whether the customer will take another flight with the airline or not as well as clustering the customer into different groups. For the second data set, we will mainly deal with the attributes that can have an impact on customer satisfaction using binary classification. For this reason, merging the datasets is not required and it is better to treat them separately.
Data Visualization
For both the data sets, we made a histogram and a regplot as that goes with our problem statements. A histogram best explains that for the attributes in both data sets with ratings given from 0 to 5, how much is the count of each star in each attribute. This also gives an idea which attributes were ranked higher in stars than the others and which attributes did poorly. The histogram of these attributes are below:
Data set 1

 <img width="465" alt="Screen Shot 2024-06-18 at 10 41 23 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/d5bf06fb-9316-4f9e-aeb2-9a28c488c3d9">

Data set 2:

<img width="443" alt="Screen Shot 2024-06-18 at 10 41 41 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/52216b59-8740-40bf-98f9-d8ab6f3a4270">

Secondly, we calculated the correlation score of these attributes with satisfaction and plotted a regplot to visualize this information as well as to see what attributes have most impacted the satisfaction score and what type of relationship do they share with the target variable.
Data set 1:

<img width="468" alt="Screen Shot 2024-06-18 at 10 42 02 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/82df7e8e-cecd-4f42-aafc-17f0420b5e4d">

Data set 2:
 
<img width="341" alt="Screen Shot 2024-06-18 at 10 42 14 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/f5e20bff-ce02-463f-9026-3824b7d623dc">

<img width="570" alt="Screen Shot 2024-06-18 at 10 42 29 PM" src="https://github.com/faizankhan29/Customer-Satisfaction-for-Airline-Travel/assets/10673214/57bdd0fe-c9a9-46bc-a9f7-f3b8d68a6a96">

## Define your classification or prediction variables
In the first data set, the classification variable is the first column with the name ‘satisfaction’. This column tells whether each customer was satisfied or not with the airline based on the attributes mentioned in the first dataset.
For the second dataset, our classification variable is the column ‘Overall satisfaction’ where we have two labels; satisfied and non satisfied. This column initially had rating values from 0 to 5. As mentioned above, users that gave a rating of 4 or 5 are classified as satisfied; all the others have been classified as not satisfied.
