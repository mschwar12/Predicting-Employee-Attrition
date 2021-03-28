# Predicting Housing Prices in King County, WA, Using Multiple Linear Regression

**Author**: [Matt Schwartz](mailto:mtschwart@gmail.com)

## Overview 

The following report provides data and analysis on housing prices in King County, Washington State, and details a number of multiple regression models used to predict these prices. 

## Business Problem

Buying a home can be a frustrating process. Everyone has some idea of their dream home, but when it comes down to actually buying one, chances are there are blockers to getting the exact one you want. Maybe the square footage isn't right, or you wish it had another bedroom, or you simply don't have enough cash on hand to cover the down payment. Whatever it is, the process is long and arduous and requires lots of research.

As a prospective home buyer, one of the last things you'd want to do is overpay for that home. It's hard to know when you're getting fleeced, especially when you're really desparate to buy. This project is meant to help buyers not overpay for their home. By building a reliable prediction engine, we can help new home buyers know if they're getting a good price. We'd also be able to tell them what factors influence prices, and by how much. In theory, waterfront property will be cost more, but by how much? Does a house that's been renovated have much higher prices than those that haven't? How about how old the house is, or the zipcode in which it was built?

The following will attempt to build a prediction engine that prospective home buyers can use when searching for ideal home. In the future, this model can be used as the backbone for an app or website, in which you can input the information of a house that is on sale, predict what the market price should be, and compare it to listings across the internet on sites like Zillow.

## Data

The data in this project comes from King County of Washington State. The county includes both Seattle and Bellevue, so we're looking at a large number of houses - over 21K. The dependent variable in this analysis will be home prices.

To help predict the price, we will be using the following explanatory variables:

- Rooms
- Square footage in each house, and the square footage of the houses' 15 closest neighbors
- Year built
- Year renovated (if applicable)
- Condition (overall condition of the house)
- Grade (overall grade given to each house by the King County Grading System)
- Zipcode
- Latitude and longitude
- Using these variables, and others I create, I will attempt to create a quality model (defined by satisfying the assumptions of linear regression, a high R2, and a low root mean squared error) that can accurately predict the price of a house and also provide clarity into how different variables affect the price.

## Methods

To build a prediction engine, we utilized multiple linear regression. By regressing the variables listed above on price, we were able to account for a significant portion of the variation in price. To eliminate the influence of major outliers, we limited the sample to houses that sold for between $100,000 and $1,000,000, and that were smaller than 4500 square feet in total space.

In addition, we create a number of variables based on our existing data. These include each houses' distance from downtown Seatlle in miles, age, and a dummy variable for whether a house was renovated or not.

## Results

Our final model, which included zipcodes, improved the R2 value by 16 percentage points over our baseline model. It also reduced root mean squared error by $26K. 

Baseline Model:

![baseline model](/images/benchmark_model_results.png)

Final Model:

![final model](/images/final_model_results.png)

In addition, we calculated the impact that each independent variable had on price. These findings include:

  - A one unit increase square footage increases price by 19% on average, holding all else equal.
  - An extra year of age decreases price by an average of about 1.4%.
  - One extra mile further from downtown decreases price by an average of about 13%.
  - A house on the waterfront is 72% more expensive than a house that isn't, on average.


## Conclusions

Our final model has good predicitive power - as mentioned above, it accounts for over 80% of the variation in price - but does have some issues. It's very heteroscedastic, meaning the residuals are not randomly distributed, and the root mean squared error, although much smaller than we started, is still $85K, meaning that each prediction has an average error of $85K. There is future work to be done. 

## Further Analysis

In the future, the main goal would be to gather more data to eliminate hidden variable bias. There are likely many more factors that influence housing price which we are not capturing in our models. Doing so would reduce our errors, improve prediction power, and create a prediction engine powerful enough to support a new application or website.

## For More Information

Please find the full analysis in the Jupyter notebook contained in this respository.

For any questions, please contact Matt Schwartz at [mtschwart@gmail.com](mailto:mtschwart@gmail.com)



## Repository Structure

```
├── data
├── images
├── .canvas
├── .gitignore
├── CONTRIBUTING.md
├── King_County_Home_Price_Predictions_Presentation.pdf
├── Link_to_Presentation_Recording.docx
├── Predicting_Housing_Prices_In_King_County.ipynb
├── Predicting_Housing_Prices_In_King_County_Jupyter_Notebook.pdf
├── README.md
```
