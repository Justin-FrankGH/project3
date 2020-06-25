# AirBnB - New York

    # The Concept:
        Entering into the world of AirBnB as a prospective host can be tricky. With so many properties listed, hosts active, and guest desires, it can be difficult to see how your property can measure up. Knowing what price to attach to your listing can mean the difference between a dormant domicile and a regularly rented residence. We set out in search of what attributes of an AirBnB rental most influenced its price. When searching for a place to stay, the location, number of bedrooms, number of bathrooms, amenities, host reliability, and many other factors play into what you would choose and how much you're willing to pay, but how do we use this to determine the best price for a listing of our own? Below, you can see the steps we took to tackle this very problem.

    # The Team:
        Justin Frank
        Leo Ramirez
        Veohnti Afokpa
        Tari Okoya-Koren
        Araz Ohanessian
        Milton Dimas

    # The Process:
    
    Data Cleaning:
        Provided with a thorough New York AirBnB listing dataset, the first task was isolating the relevant data and cleaning it for our purposes. 
        Outliers in fields
        No data fields
        Listings with 0 square feet - possibly drop these
        Google avg square footage - look at this to see if there are items that below 1 standard deviation from the average
        2500 listings that don't have the exact locations - delete these
        Drop URLS 
    Tableau - Tari, Araz
        Explore the data in Tableau
        come up with some visualizations based on what we are seeing
        come up with some inputs into a machine learning model
    Machine Learning - Veohnti ( Milton)
        Use inputs from Tableau to come up with a list of inputs to machine learning model(s)
    Predict Prices	- Justin
        Create a form to take inputs and predict prices
