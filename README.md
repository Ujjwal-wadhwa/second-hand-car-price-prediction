# second-hand-car-price-prediction

This project aims to predict the prices of used cars using a dataset collected from cars24.com. The dataset contains 8015 entries with 9 different features, including Car Name, Year, Owner, Fuel, Location, Drive, Type, Distance, and Price.

## Data Collection

A web scraper was developed using Selenium to scrape used car listings from cars24.com to obtain the dataset. The scraper navigated through the website, collected information about each car listing, and stored it in a structured format. The main reason for choosing selenium for building the scrapper was that the site had an infinite scrolling feature so it  was automated using selenium. The scraping process resulted in a dataset with 8015 entries and 9 features. If you would like more details about the scrapper, Please read the README of my separate repository for it https://github.com/Ujjwal-wadhwa/Cars24_Scrapper.

## Data Preprocessing

Before building the predictive model, various preprocessing steps were performed on the dataset:

- Removed duplicates to ensure data integrity.
- Transformed the 'Distance' variable to 'log_distance' using the formula `1/5*round(5*np.log10(1+x))`.
- Converted 'Year' to string format and filled missing values with 'None'.
- Handled missing values in 'Location' and 'Car Name' by filling them with 'None'.
- Lowercased all car names for uniformity.
- Encoded categorical variables, such as 'Car Name', 'Fuel', 'Location', 'Drive', and 'Type', using the RareLabelEncoder to handle infrequent categories.

## Exploratory Data Analysis (EDA)

EDA was performed using various visualizations, including scatter plots, box plots, groupby tables, pivot tables, and a heatmap. ANOVA tests were also conducted to assess the correlation between categorical variables and the target variable (Price).

## Model Building

A CatBoostRegressor model was chosen for predicting used car prices due to its ability to handle categorical variables effectively. The model was trained on the preprocessed dataset and evaluated using RMSE and R-squared metrics.

## SHAP Visualization

To gain insights into the model's predictions, SHAP (SHapley Additive exPlanations) visualizations were utilized. SHAP summary plots, layered violin plots, and dependence plots were created to interpret feature importance and understand how the predicted outcome changes with the variation of input features.

## Conclusion

This project demonstrated collecting, preprocessing, exploring, and modelling used car data. The data was scraped from cars24.com using a Selenium web scraper, and the resulting dataset was used to train a CatBoostRegressor model for predicting used car prices. The SHAP visualizations enhance interpretability, allowing users to understand the model's decision-making process.

If you would like more details, please refer to the Jupyter Notebook and source code in the repository.

