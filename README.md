# hotel-recommendation-ayatem-using-hybride
🏨 Hybrid Hotel Recommendation System

A smart hotel recommendation engine combining content-based and collaborative filtering to suggest hotels in Ethiopia based on amenities, reviews, and user preferences.
✨ Features

✅ Hybrid Recommendation Model

    60% Content-Based (TF-IDF + Cosine Similarity for amenities)

    40% Collaborative (Normalized review score comparison)

✅ Flexible Hotel Search

    Partial name matching (e.g., "Ax" → "Axum Hotel")

    Filters:

        ★ Star rating (min. threshold)

        💵 Max price (ETB)

        📍 City/Region

        🛁 Required amenities (e.g., "Pool, Breakfast, WiFi")

✅ Transparent & Customizable

    Returns hotel name, location, rating, price, and amenities

    Easy-to-tweak similarity weights (e.g., 0.7 * content + 0.3 * reviews)

🚀 Quick Start
1. Install Dependencies
bash

pip install pandas scikit-learn numpy

2. Load Data & Run Recommendations
python

import pandas as pd
from recommendation_engine import recommend_hotels_partial

# Load dataset
df = pd.read_csv("processed_hotels.csv")  

# Get recommendations
recommendations = recommend_hotels_partial(
    hotel_name="Axum",
    min_star=3,
    max_price=8000,
    required_amenities=["Pool", "Breakfast", "Free Parking"]
)

print(recommendations)

Example Output
Name	City	Region	Stars	Price (ETB)	Amenities
Axum Paradise Resort	Axum	Tigray	⭐⭐⭐⭐	7500	Pool, Breakfast, Free Parking
Queen Sheba Hotel	Axum	Tigray	⭐⭐⭐½	6800	Pool, Breakfast, Free Parking
📂 Repository Structure
text

.
├── data/  
│   └── processed_hotels.csv          # Sample dataset  
├── notebooks/  
│   └── Hotel_Recommendation_Demo.ipynb  # Example usage  
├── recommendation_engine.py          # Core recommendation logic  
├── requirements.txt                  # Dependencies  
└── README.md  

🛠 Customization

    Adjust similarity weights: Modify hybrid_sim = 0.6 * cosine_sim + 0.4 * collab_sim in code.

    Add new filters: Extend the recommend_hotels_partial() function (e.g., distance-based sorting).

📜 License

MIT License - Free for academic and commercial use.

💡 Ideal for: Travel apps, hotel aggregators, tourism analytics.
🔍 Dataset Requirements: Hotel names, amenities, ratings, prices, and locations.

👉 Try it out and customize for your needs
