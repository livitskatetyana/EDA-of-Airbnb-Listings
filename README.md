# EDA-of-Airbnb-Listings
This project analyzes NYC Airbnb listings to identify factors affecting rental prices. Room type and neighbourhood are the strongest influences, with entire homes and Manhattan listings being pricier. Other factors like host listing count and availability have moderate impact, while reviews and minimum nights show minimal effect.
# Airbnb NYC Price Analysis

## 1. Dataset Overview

- **Number of rows:** 48,895  
- **Number of columns:** 16  
- **Main variables:**  
  - `price`, `log_price`, `minimum_nights`, `calculated_host_listings_count`, `availability_365` (numerical)  
  - `room_type`, `neighbourhood_group` (categorical)  

**Data Cleaning Steps:**
- Removed columns related to reviews (`number_of_reviews`, `last_review`, `reviews_per_month`)  
- Dropped rows with missing `name` and `host_name`  
- Removed extreme values in `price` (< $10 or > $1000) and `minimum_nights` (<1 or >30)  

---

## 2. Statistical Summary

**Numerical variables (mean / median / std):**

| Variable | Mean | Median | Std Dev |
|----------|------|--------|---------|
| price | 141.33 | 105.00 | 116.89 |
| log_price | 4.72 | 4.66 | 0.66 |
| minimum_nights | 5.58 | 2.00 | 8.20 |
| calculated_host_listings_count | 7.17 | 1.00 | 33.14 |
| availability_365 | 111.46 | 43.00 | 131.06 |

**Categorical variables:**
- `room_type` – 3 unique values (`Entire home/apt`, `Private room`, `Shared room`)  
- `neighbourhood_group` – 5 unique values (Brooklyn, Manhattan, Queens, Staten Island, Bronx)  

---

## 3. Price Analysis by Key Factors

### Neighbourhood Group
- Manhattan has the highest prices on average.  
- Brooklyn and Queens have medium prices.  
- Bronx and Staten Island are the cheapest.  
- Price variation within districts is high.  

### Room Type
- `Entire home/apt` is the most expensive type.  
- `Private room` is moderately priced.  
- `Shared room` is the cheapest.  

**Visualizations:**
- **Boxplots:** price vs room_type, neighbourhood_group, accommodates  
- **Scatterplots:** price vs reviews_per_month  

---

## 4. Correlation Analysis

- `price` and `log_price` are strongly positively correlated (0.89).  
- **Strongest factors influencing price:**
  - `room_type_Private room` (negative correlation with price: -0.45 / log_price: -0.58)  
  - `neighbourhood_group_Manhattan` (positive correlation with price: 0.29 / log_price: 0.35)  
- Moderate positive correlations:
  - `calculated_host_listings_count` (0.13 / 0.14)  
  - `availability_365` (0.12 / 0.09)  
- Weak or negligible correlations: `minimum_nights`, `latitude`, `longitude`  

**Heatmap:** correlation between numerical and categorical (dummy) variables  

---

## 5. Key Takeaways

1. **Most influential factors on Airbnb price:**  
   - Type of room (`Entire home/apt` vs `Private room`)  
   - District (`Manhattan` vs other boroughs)  
2. **Moderate influence:**  
   - Host listings count, availability  
3. **Minimal influence:**  
   - Minimum nights, reviews per month, latitude/longitude  

---

## 6. Figures

- Boxplots and scatterplots for price vs key categorical and numerical features  
- Correlation heatmap  


