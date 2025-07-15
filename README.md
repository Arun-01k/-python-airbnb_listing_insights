# Airbnb Listings Insights

- **Project Type**: Data Analysis & Price Prediction using Python
- **Tools**: Python, Pandas, Seaborn, Plotly, Scikit-learn
- **Description**: Performed data cleaning, exploratory analysis, and built a regression model to estimate Airbnb listing prices. Delivered insights on pricing patterns, guest behavior, and host strategy.


## 📌 Overview
This project analyzes Airbnb listings data to uncover insights about pricing, availability, host behavior, and guest engagement. It includes:
- Data cleaning and preprocessing
- Exploratory Data Analysis (EDA)
- Price distribution and review trends
- Room type and geographic patterns
- A regression model to predict price

---

## 🧼 Data Cleaning
The dataset required cleaning to ensure reliability:
- Removed or filled `NaN` values in key columns
- Extracted and cleaned `price` and `service_fee` columns by removing dollar signs and converting to floats
- Inferred missing `service_fee` or `price` values using the 20% fee assumption
- Cleaned `house_rules`, `instant_bookable`, and `host_identity_verified` into binary format (1/0)
- Removed rows with incomplete review data if `number_of_reviews > 0`
- Dropped irrelevant or redundant columns (`license`, `country`, `country_code`, etc.)

---

## 📊 Exploratory Data Analysis (EDA)

### Price & Review Distribution
- The data reveals that although listing prices vary, guest engagement — measured by review volume — is overwhelmingly focused on listings priced under $300. This implies that affordability plays a significant role in booking behavior.
- Number of reviews also shows a long tail; most listings have fewer than 50 reviews

### Correlations
We examined correlations among selected features:
- correlation remains statistically insignificant
- `price` shows weak correlation with most numeric variables, indicating external factors at play

### Date Range
- `last_review` column ranges from **2011 to 2024**, covering a wide timeline of guest activity with some disruption during COVID-19

---

## 🌍 Geographic and Room-Type Insights

### Price & Room Type on Map
- A scatter map using Plotly visualizes price clusters by location
- Listings with higher prices cluster in central locations and tourist zones

### Room Type by City
- Entire homes dominate most cities
- Private rooms form a significant portion in urban neighborhoods

### Stacked Price Distribution
- Listings grouped in $40 bins show most properties are budget-friendly
- Average review count per price bin declines slightly as prices increase

---

## 🤖 Predictive Modeling

### Model Setup
- Features used: `minimum_nights`, `availability_365`, `number_of_reviews`, `review_rate_number`, `reviews_per_month`, `calculated_host_listings_count`, and binary fields
- Model: `RandomForestRegressor`
- Target: `price`

### Performance
- **Mean Absolute Error**: ~$196
- **R² Score**: 0.21

### Interpretation
> While the model explains only ~21% of the variance in price, this is expected due to unobserved human factors such as property aesthetics, location charm, photo quality, and seasonal dynamics — none of which are captured in the dataset.

---

## ✅ Summary & Takeaways
- Prices are heavily driven by non-numeric, human-centered factors
- Structured data like review count and availability provide partial signals
- The dataset offers rich insight into market trends, but predictive power is limited

---

*Built using Python, Pandas, Matplotlib, Seaborn, Plotly, and Scikit-learn.*
