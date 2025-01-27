**Airbnb NYC Data Analysis (2019)**
Exploring Airbnb listings in NYC using Python, Pandas, Matplotlib, and Seaborn.

**Project Overview**
This project analyzes Airbnb listings in New York City (NYC) using exploratory data analysis (EDA) and data visualization techniques.
The goal is to uncover pricing trends, neighborhood insights, and key business recommendations for Airbnb hosts and decision-makers.
**Dataset Details**
Source: Airbnb NYC 2019 Dataset
Size: ~49,000 Airbnb listings
Features: Price, location, room type, number of reviews, availability, etc.
**Tools & Libraries Used**
Python 
Pandas (for data wrangling)
NumPy (for numerical operations)
Matplotlib & Seaborn (for data visualization)
Google Colab (for running the notebook)
**📊 Data Analysis & Visualizations**
Here are key visualizations and insights from the dataset:

1️⃣ Price Distribution
📌 Histogram of listing prices in NYC
Insight: Most listings are priced below $500, but there are extreme outliers.

import matplotlib.pyplot as plt
import seaborn as sns

plt.figure(figsize=(10, 6))
sns.histplot(data['price'], kde=True, bins=30, color='blue')
plt.title('Distribution of Listing Prices', fontsize=16)
plt.xlabel('Price', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.show()

2️⃣ Count of Listings by Room Type
📌 Bar chart of room types (Entire home, Private room, Shared room, etc.)
Insight: Entire homes/apartments are the most common listing type.

plt.figure(figsize=(8, 5))
sns.countplot(x='room_type', data=data, palette='viridis')
plt.title('Count of Listings by Room Type', fontsize=16)
plt.xlabel('Room Type', fontsize=12)
plt.ylabel('Count', fontsize=12)
plt.show()

3️⃣ Average Price by Neighborhood
📌 Comparison of average listing prices across different NYC neighborhoods.
Insight: Manhattan has the highest average price, while the Bronx has the lowest.


plt.figure(figsize=(8, 5))
avg_price = data.groupby('neighbourhood_group')['price'].mean().sort_values()
avg_price.plot(kind='bar', color='teal')
plt.title('Average Price by Neighbourhood Group', fontsize=16)
plt.xlabel('Neighbourhood Group', fontsize=12)
plt.ylabel('Average Price ($)', fontsize=12)
plt.show()

4️⃣ Room Type vs Price (Boxplot)
📌 Analyzing price variations by room type.
Insight: Entire homes have the highest price range, while shared rooms are the cheapest.


plt.figure(figsize=(8, 5))
sns.boxplot(x='room_type', y='price', data=data, palette='muted')
plt.title('Room Type vs Price', fontsize=16)
plt.xlabel('Room Type', fontsize=12)
plt.ylabel('Price ($)', fontsize=12)
plt.ylim(0, 1000)  # Limiting the y-axis for clarity
plt.show()

5️⃣ Correlation Heatmap
📌 Understanding the relationship between numerical features.
Insight: Number of reviews is negatively correlated with price.

plt.figure(figsize=(10, 8))
sns.heatmap(data.corr(), annot=True, cmap='coolwarm', fmt='.2f')
plt.title('Correlation Heatmap of Numerical Features', fontsize=16)
plt.show()

📈 **Business Insights**
Pricing Trends: Most listings are reasonably priced, but some extreme outliers exist.
Popular Room Types: Entire homes/apartments dominate the market.
Location-Based Pricing: Manhattan has the highest prices, Bronx the lowest.
Demand & Reviews: Cheaper listings get more reviews, indicating higher demand.
📌 **Recommendation:**

Hosts should competitively price listings based on room type & location.
Airbnb can optimize marketing strategies for the most popular areas.
Outlier prices should be analyzed further to improve pricing models.


📌 **Future Improvements**
✅ Feature engineering for better predictions
✅ Applying machine learning models for price prediction
✅ Interactive dashboard using Power BI/Tableau
✅ Further analysis on review sentiments & customer preferences


