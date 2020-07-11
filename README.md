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

## The Data Source:
The data we worked with came from an open data source [InsideAirbnb](http://insideairbnb.com/get-the-data.html).

## The Process:
    
### Data Cleaning:
>[listings_data_cleaning.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/listings_data_cleaning.ipynb)

Provided with a thorough New York AirBnB listing dataset, the first task was isolating the relevant data and cleaning it for our purposes. Using pandas and data exploration tools in Jupyter Notebook, Leo found Nan value data points, listings with zero availability, and features irrelevent to our process. Considering we were also going to compare price to location, all listings lacking an exact location were dropped. Employing dataframe cleaning measures, he was then able to transform the dataset into one that's cleaner, consistent, and easy to use. Finally, the newly cleaned data was exported as a CSV for application in all the following processes.
        
### Tableau part 1- Tari, Araz
>[Tableau Public](https://public.tableau.com/profile/tariere#!/vizhome/AirBnBFeatures-HypothesizedImpactfulFeatures/ZipCode) 

Furthering the data exploration process, Tari and Araz created Tableau visualizations to ascertain which features showed a strong correlation with a listing's price. The items seen to show an impact on price were logged and then used to train the machine learning models, referenced below.

### Machine Learning part 1 - Veohnti, Milton
>[initial_machine_learning_attempt.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/initial_machine_learning_attempt.ipynb)

Using the features deemed relevant from Tableau, Veohnti and Milton trained both Ridge and SVR maching learning models. Unfortunately, however, the models returned dismal accuracy scores. While these models were ultimately unusable, we learned two things from the process:
    1. Our feature selection was narrow and limited to our presupposed notion of what would impact price. With such an expansive dataset, it was important for us to explore the possibility of seemingly inconsequential features affecting price. 
    2. The visualizations we created were only showing the correlation between price and a given feature. What they didn't tell us were the weights each feature had on price affect. This is to say, we could conclude which features were affecting price, but not which were affecting price the most.
    
### Machine Learning part 2 - Leo
>[xgboost_airbnb_ny.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/xgboost_airbnb_ny.ipynb)

To correct our approach, XGBoost was employed to gain the weights of each feature and more accurately train a model. Once done, the XGBoost model presented a 70% accuracy score, a far better result than the preceeding regression models. 

### Tableau part 2 - Tari, Araz
>Tableau Public [1](https://public.tableau.com/profile/araz.ohanessian#!/vizhome/RoomType_15934540785170/ReviewScores?publish=yes) [2](https://public.tableau.com/profile/tariere#!/vizhome/AirBnB-Amentities/AmenitiesvsMedianPrice?publish=yes)

Seeing the new weights and relevant features, Tari and Araz once again applied Tableau to the data and reconfirmed the relations of features to median price. The visuals show why or why not a feature had a relation to a given listing's price.

### Machine Learning part 3 - Veohnti, Milton
>[neural_net_models.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/neural_net_models.ipynb)

To ensure that a 70% accuracy score was the most accurate model we could apply, Veohnti and Milton experimented with Neural Net Modeling. Using multiple layers and an SGD Optimizer, several accuracy tests were performed. The end results showed scores just shy of that of the XGBoost model. 

### Predict Prices	- Justin
>[user_input.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/jupyter_notebooks/user_input.ipynb)

Working with the cleaned data provided by Leo, Jupyter Notebook widgets were imported and used to create an interactive user input form. The input values were set to be live updating and could be pulled for use in a machine learning model prediction formula. After compiling the new input data, a function was defined to first aggregate and zip the data with their respective titles. Next, the data was logged, scaled using the predefined training data, and funneled through the XGBoost predict method. Finally, the output was produced and put through and inverse logarithm function. This resulted in the final predicted price for the user's listing. 

## How to use:
Run the data through the data cleaning notebook and it will generate a CSV title "listings.csv". Once created, you can run the xgboost_airbnb_ny.ipynb notebook which will automatically pull "listings.csv". This notebook will run further cleaning and transformations to set up the data for machine learning. Then, the notebook will proceed to perform analyses, provide visuals, and create the XGBoost machine learning model. Once completed, this will also export two new CSVs for use in the user_input.ipynb notebook. This notebook will finally create the input form for listing price prediction.
