# House pricing predictions

### Project Overview
This project aims to predict house prices in the Greater Jakarta area (Jabodetabek) using machine learning techniques. The project starts with Exploratory Data Analysis to understand the structure of the data and several cleaning steps were performed to ensure the data quality

### Data Sources
The dataset used for this analysis is the "jabodetabek_house_price.csv", containing information about residential properties in the region. Features include location, number of bedrooms and bathrooms, land and building size, and other relevant property details.

### Tools
- Python (Pandas, Numpy, Matplotlib, Seaborn, Scikit-learn)

### Data Cleaning
In the initial data preparation phase, I performed the following tasks :
1. Dropping irrelevant or non-informative columns that do not contribute to the predictive analysis such as url, ads_id, title, etc.
2. Checking and imputing missing values, using mean and median values for the numerical columns and modus for the categorical columns.
3. Splitting the data into training and testing data.

### Exploratory Data Analysis
EDA involved exploring the sales  data to answer key questions, such as :
- What is the overall distribution of key variables in the dataset ?
- What is the correlation between all features and the target variable (price) ?

### Data Analysis
![image](https://github.com/user-attachments/assets/b00fc4b0-50f3-41ad-b195-8d3fac351d3d)
Here is the distribution of the data, the data distribution reveals that some features exhibit skewness, which may affect the performance of the predictive model.
So I applied the natural logarithm transformation using np.log to reduce the skewness of the data, and here's the result
![image](https://github.com/user-attachments/assets/34461660-e851-4737-a614-93479e3dea9b)
The skewness has been effectively reduced as the distribution is now approximately centered around zero.

![image](https://github.com/user-attachments/assets/4d36aae4-a5da-4958-82a1-85c0545cd6ab)
and here is the heatmap that showing all the correlations between all features and the target variable (price)
Here are some insights that can be taken:
1. Features That Have High Correlation with Price (price_in_rp):
Building size (0.82) → Has the highest correlation with price. This means that the larger the building size, the higher the price of the house.
- Electricity (0.67) → The electricity capacity of the house also has a strong correlation with price.
- Land size (0.72) → Land area has a significant effect on price.
- Bedrooms (0.54) and Bathrooms (0.53) → The number of bedrooms and bathrooms also has a moderate positive correlation with price.
- Maid Bedrooms (0.54) → The presence of a maid's room also has a slight effect on price.

2. Inter-feature Correlation (Multicollinearity):
- Bedrooms & Bathrooms (0.75) → Houses with more bedrooms tend to also have more bathrooms.
- Land size & Building size (0.79) → Land area is highly correlated with building size, which can cause multicollinearity in the linear regression model.
- Maid Bedrooms & Maid Bathrooms (0.84) → It makes sense because houses with maid rooms usually have maid bathrooms too.

3. Features with Low or Insignificant Correlation:
Carports (0.0026) and Garages (0.23) → Have very low impact on house prices.
- Carports (0.0026) and Garages (0.23) → Have a very low impact on house prices.
- Latitude and Longitude have very small correlations (around 0.16 and 0.22), likely because location is more complex than just coordinates.




