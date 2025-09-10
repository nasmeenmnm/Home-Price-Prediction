House Price Prediction
This project is a machine learning web application that predicts house prices in Bangalore. It uses a Linear Regression model to predict prices based on key features, with a Flask backend serving the predictions to a frontend built with HTML, CSS, and JavaScript.

🧐 How It Works
The system predicts house prices by leveraging a machine learning model trained on a real estate dataset. Here's a summary of the process:

Data Cleaning and Preprocessing: The project begins by loading a dataset of Bangalore house prices. The data is cleaned by removing irrelevant columns like area_type, society, balcony, and availability. Missing values are also handled by dropping the rows with NaN values.

Feature Engineering: A new feature, price_per_sqft, is created to help with outlier detection. The size column, which contains values like '2 BHK' or '4 Bedroom', is converted into a numerical bhk (Bedrooms, Hall, Kitchen) column. The total_sqft column is also cleaned to handle various formats (e.g., ranges and non-numeric values) by converting them into a single numerical value.

Outlier Removal: Outliers are removed based on a few assumptions:

Any property with a total_sqft per bhk less than 300 is considered an outlier and removed.

Properties with price_per_sqft values that fall outside one standard deviation from the mean for a given bhk are also removed.

Properties where the number of bathrooms (bath) is significantly more than the number of bedrooms (bhk + 2) are also cleaned.

Model Training: The cleaned data is used to train a Linear Regression model. The model is trained on total_sqft, bath, and bhk to predict the price.

Backend (Flask): The trained model is saved using pickle. A Flask backend loads this model and an accompanying columns.json file. The backend takes user input (square footage, number of bathrooms, and BHK), uses the model to predict the price, and returns the result.

Frontend: The user interface is built using HTML, CSS, and JavaScript. It allows users to input the property details and view the predicted price.

🚀 Getting Started
To run this project, you need a Python environment with the required libraries. The core libraries used are Pandas, Numpy, and Scikit-learn. The web server is powered by Flask.

💡 Key Features
Accurate Price Prediction: Uses a Linear Regression model to provide a reliable price estimate.

Robust Data Processing: Includes comprehensive data cleaning and outlier removal techniques to improve model accuracy.

User-Friendly Interface: The frontend allows for easy input and quick display of results.

Modular Design: The project separates the backend logic (Python/Flask) from the frontend presentation (HTML/CSS/JS).
