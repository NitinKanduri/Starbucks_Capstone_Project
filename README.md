## Project Context

Starbucks, recognized as one of the largest global coffee enterprises, operates over 31,000 stores worldwide. In 2017, the company introduced its most sophisticated AI-driven initiative, Deep Brew. This proprietary recommendation platform was designed to engage customers across diverse channels, including the Starbucks ordering app. Additionally, the industry-leading Starbucks Rewards Program, launched in 2007, has seen consistent growth and success. Leveraging AI technology has become increasingly crucial in optimizing and enhancing the overall customer experience.

## Goal

To deliver a highly personalized experience from order placement to loyalty app offers, it is imperative to accurately identify and target the appropriate customer segments. The challenge lies in determining the most effective personalized offer to send to users in order to maximize conversion rates. Additionally, understanding which customer groups are most responsive to specific types of offers and identifying the optimal method for presenting each offer is critical for success.

The objective of this project is to develop a machine learning model capable of determining the most suitable type of offer for each customer. The dataset will be categorized into three distinct offer types and utilized to train three supervised classification models. These models will predict whether a customer will respond positively to an offer when presented. Furthermore, by analyzing the feature importance within the models, the key factors influencing customer decisions and transactions can be identified. 

This approach provides a robust solution for accurately segmenting customer groups based on their responsiveness to different offer types. It also enables the optimization of offer presentation strategies, ensuring a more effective and targeted customer engagement process.

## Data Components

The data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed
  
The schema and detailed explanation of each variable in the files are outlined below

#### portfolio.json

* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)
  
#### profile.json

* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income
  
#### transcript.json

* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Software Components
This project uses *Python 3.6* and the following necessary libraries:

* pandas
* numpy
* math
* json
* matplotlib
* sklean
* seaborn
* scipy

## Project Design
The project is designed with the following steps
#### Data Preparation and Cleaning  
The initial step involves integrating transaction, demographic, and offer data into a unified dataset. This phase includes analyzing the relationships between columns and datasets to extract as much meaningful information as possible.  

#### Data Exploration  
To better analyze the problem in subsequent sections, the datasets must be explored thoroughly. This includes identifying and addressing missing values, visualizing data distributions, and gaining insights into the overall structure and characteristics of the data.  

#### Data Preprocessing  
To determine the primary factors influencing transaction completion triggered by offers, the data preprocessing phase involves aligning and consolidating events for each specific offer. This includes identifying which offers were received, viewed, and ultimately resulted in completed transactions.  

#### Feature Engineering  
Post-basic processing, this phase focuses on creating new features from existing data. Examples include calculating the duration of a customer's membership, counting the number of offers received by each user, and determining the time intervals between consecutive offers.  

#### Model Building  
Following data preprocessing and feature engineering, a machine learning model is constructed. The model leverages a response flag generated in earlier steps to predict whether a customer will respond positively to a given offer.  

#### Model Tuning  
Model performance is evaluated using selected metrics, and the initial model parameters are optimized using the GridSearch method to achieve superior results.  

#### Conclusion and Future Enhancements  
The final model's performance is compared against a benchmark to assess its effectiveness in delivering personalized offers. Additionally, the entire development process is reviewed to identify potential areas for further improvement and refinement of the model in future iterations.

## Future Work
- Overfitting may occur and can be mitigated by incorporating a larger volume of data or applying regularization techniques to improve model generalizability.  

- Design and implement a robust pipeline to streamline the classification of new data, ensuring scalability and reproducibility in data processing and model inference.  

- Construct a machine learning model to accurately predict transaction amounts, leveraging relevant features to optimize precision and minimize error.  

- Deploy the machine learning model to a web platform, enabling seamless integration and real-time predictions for end-users.

## Licencing & Acknowledgements
Thanks to Starbucks for the dataset, and to Udacity for bringing the opportunity to work with it.
