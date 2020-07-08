# AirBnB - New York

## The Concept:
Entering into the world of AirBnB as a prospective host can be tricky. With so many properties listed, hosts active, and guest desires, it can be difficult to see how your property can measure up. Knowing what price to attach to your listing can mean the difference between a dormant domicile and a regularly rented residence. We set out in search of what attributes of an AirBnB rental most influenced its price. When searching for a place to stay, the location, number of bedrooms, number of bathrooms, amenities, host reliability, and many other factors play into what you would choose and how much you're willing to pay, but how do we use this to determine the best price for a listing of our own? Below, you can see the steps we took to tackle this very problem.

## The Team:
- Justin Frank
- Leo Ramirez
- Veohnti Afokpa
- Tari Okoya-Koren
- Araz Ohanessian
- Milton Dimas

## The Process:
    
### Locating the Data Source:
The data we worked with came from an open data source [InsideAirbnb](http://insideairbnb.com/get-the-data.html).
### Data Cleaning:
>[listings_data_cleaning.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/listings_data_cleaning.ipynb)

Provided with a thorough New York AirBnB listing dataset, the first task was isolating the relevant data and cleaning it for our purposes. Using pandas and data exploration tools in Jupyter Notebook, Leo found Nan value data points, listings with zero availability, and features irrelevent to our process. Considering we were also going to compare price to location, all listings lacking an exact location were dropped. Employing dataframe cleaning measures, he was then able to transform the dataset into one that's cleaner, consistent, and easy to use. Finally, the newly cleaned data was exported as a CSV for application in all the following processes.
        
### Tableau part 1- Tari, Araz
>Tableau Visualizations: [1](https://public.tableau.com/profile/tariere#!/vizhome/AirBnBFeatures-HypothesizedImpactfulFeatures/ZipCode) [2](https://public.tableau.com/profile/araz.ohanessian#!/vizhome/RoomType_15934540785170/ReviewScores?publish=yes) [3](https://public.tableau.com/profile/tariere#!/vizhome/AirBnB-Amentities/AmenitiesvsMedianPrice?publish=yes)

Furthering the data exploration process, Tari and Araz created Tableau visualizations to ascertain which features showed a strong correlation with a listing's price. The items seen to show an impact on price were logged and then used to train the machine learning models, referenced below.

### Machine Learning part 1 - Veohnti, Milton
>[LINK HERE]()

Using the features deemed relevant from Tableau, Veohnti and Milton trained both Ridge and SVR maching learning models. Unfortunately, however, the models returned dismal accuracy scores. While these models were ultimately unusable, we learned two things from the process:
    1. Our feature selection was narrow and limited to our presupposed notion of what would impact price. With such an expansive dataset, it was important for us to explore the possibility of seemingly inconsequential features affecting price. 
    2. The visualizations we created were only showing the correlation between price and a given feature. What they didn't tell us were the weights each feature had on price affect. This is to say, we could conclude which features were affecting price, but not which were affecting price the most.
    
### Machine Learning part 2 - Leo
>[xgboost_airbnb_ny.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/xgboost_airbnb_ny.ipynb)

### Tableau part 2 - Tari, Araz

### Predict Prices	- Justin
>[user_input.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/user_input.ipynb)

Working with the cleaned data provided by Leo, I created drop downs, fill-in fields, and other widgets (using the ipynb widgets library) that can be plugged into a user-interactive 'form'. Once all property details are filled in, the task was then to pull the input values, and plug them into the newly created machine learning model. Once the collected data was cleaned and adjusted into an XGBoost prediction-friendly format, 
