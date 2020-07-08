# AirBnB - New York

    ## The Concept:
        Entering into the world of AirBnB as a prospective host can be tricky. With so many properties listed, hosts active, and guest desires, it can be difficult to see how your property can measure up. Knowing what price to attach to your listing can mean the difference between a dormant domicile and a regularly rented residence. We set out in search of what attributes of an AirBnB rental most influenced its price. When searching for a place to stay, the location, number of bedrooms, number of bathrooms, amenities, host reliability, and many other factors play into what you would choose and how much you're willing to pay, but how do we use this to determine the best price for a listing of our own? Below, you can see the steps we took to tackle this very problem.

    ## The Team:
        Justin Frank
        Leo Ramirez
        Veohnti Afokpa
        Tari Okoya-Koren
        Araz Ohanessian
        Milton Dimas

    ## The Process:
    
    ### Locating the Data Source:
        The data we worked with came from an open data source [InsideAirbnb](http://insideairbnb.com/get-the-data.html).
    ### Data Cleaning:
    >[listings_data_cleaning.ipynb](https://github.com/Justin-FrankGH/project3/blob/master/listings_data_cleaning.ipynb)
        Provided with a thorough New York AirBnB listing dataset, the first task was isolating the relevant data and cleaning it for our purposes. Using pandas and data exploration tools in Jupyter Notebook, Leo found Nan value data points, listings with zero availability, and features irrelevent to our process. Considering we were also going to compare price to location, all listings lacking an exact location were dropped. Employing dataframe cleaning measures, he was then able to transform the dataset into one that's cleaner, consistent, and easy to use. Finally, the newly cleaned data was exported as a CSV for application in all the following processes.
        
    ### Tableau - Tari, Araz
        Explore the data in Tableau
        come up with some visualizations based on what we are seeing
        come up with some inputs into a machine learning model
    ### Machine Learning - Veohnti ( Milton)
        Use inputs from Tableau to come up with a list of inputs to machine learning model(s)
    ### Predict Prices	- Justin
        Create a form to take inputs and predict prices
