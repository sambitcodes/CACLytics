# CACLytics

CACLytics is a data analysis and machine learning application built using Python and Streamlit. It provides exploratory data analysis (EDA), preprocessing, and prediction capabilities on a **Customer Acquisition Dataset** of a supermarket chain in the USA.

## Dataset Overview
The dataset consists of **60,428 rows** and **40 features** with no missing values. It includes information on food sales, store characteristics, and customer demographics. Below is a brief description of the columns:

| Column Name                        | Description |
|------------------------------------|-------------|
| **food_category**                  | Category of food item |
| **food_department**                | Department in the supermarket |
| **food_family**                    | Family group of the food item |
| **store_sales (in millions)**      | Total store sales in millions |
| **store_cost (in millions)**       | Total store cost in millions |
| **unit_sales (in millions)**       | Number of units sold in millions |
| **promotion_name**                 | Name of promotion applied |
| **sales_country**                  | Country of sales occurrence |
| **marital_status**                 | Customer's marital status |
| **gender**                         | Customer's gender |
| **total_children**                 | Number of children in household |
| **education**                      | Educational level |
| **member_card**                    | Membership card status |
| **occupation**                     | Type of occupation |
| **houseowner**                     | Homeownership status |
| **avg_cars_at_home (approx)**      | Approximate number of cars owned |
| **avg. yearly_income**             | Customer's yearly income |
| **num_children_at_home**           | Number of children living at home |
| **brand_name**                     | Brand of the product |
| **SRP**                             | Suggested retail price |
| **gross_weight**                   | Gross weight of the product |
| **net_weight**                     | Net weight of the product |
| **recyclable_package**             | Whether the packaging is recyclable |
| **low_fat**                        | Whether the product is low fat |
| **units_per_case**                 | Number of units per case |
| **store_type**                     | Type of store |
| **store_city**                     | City where store is located |
| **store_state**                    | State where store is located |
| **store_sqft**                     | Total store square footage |
| **grocery_sqft**                   | Grocery section square footage |
| **frozen_sqft**                    | Frozen section square footage |
| **meat_sqft**                      | Meat section square footage |
| **coffee_bar**                     | Availability of a coffee bar |
| **video_store**                    | Availability of a video store |
| **salad_bar**                      | Availability of a salad bar |
| **prepared_food**                  | Availability of prepared food section |
| **florist**                        | Availability of florist section |
| **media_type**                     | Type of media used for advertising |
| **cost**                            | Cost of acquiring a customer |

## Features of CACLytics

### 1. Playground Page
- View and explore the dataset.
- Get feature descriptions and data type (categorical/numerical).
- Perform basic Exploratory Data Analysis (EDA).

### 2. EDA Page
- Provides **24 predefined explorations** to help understand the dataset better.

### 3. Preprocessing Page
A **7-step preprocessing pipeline** for data cleaning and transformation:

#### 3.1 Basic Preprocessing
- Removes redundant column: **`avg_cars_at_home(approx).1`**.
- Removes dollar signs from **`avg. yearly_income`** column.

#### 3.2 Feature Construction
- Creates a new feature **`profile_strength`** using weighted sum of:
  - `education` (0.1)
  - `houseowner` (0.15)
  - `member_card` (0.2)
  - `income` (0.3)
  - `occupation` (0.1)
  - `avg_cars_at_home(approx)` (0.15)

#### 3.3 Encoding Ordinal Variables
- Encodes ordinal columns while preserving the order.

#### 3.4 Encoding Nominal Variables
- Uses **Binary Encoding** for high-cardinality categorical columns to avoid excessive dataset size.

#### 3.5 Handling Outliers
- Handles outliers in:
  - **`store_sales (in millions)`**
  - **`store_cost (in millions)`**
- Uses **quantile capping** to treat extreme values.

#### 3.6 Feature Selection
- Optional but helps:
  - Determine feature importance.
  - Check correlation between features.

#### 3.7 Data Scaling
- Uses **MinMax Scaler** to normalize values, ensuring compatibility with distance-based algorithms.

### 4. Prediction Page
- Users provide input for various features.
- Predicts **cost of acquiring a customer** using media campaigns.

---
### How to Run CacLytics
```sh
# Clone the repository
git clone https://github.com/sambitcodes/CACLytics.git

# Navigate to the project directory
cd CACLytics

# Install dependencies
pip install -r requirements.txt

# Run the Streamlit app
streamlit run app.py
```

### Technologies Used
- **Python**
- **Streamlit**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **Matplotlib & Seaborn**

### Live Demo
You can use the application here: [CACLytics App](https://caclytics.streamlit.app/)


---
### Contact
For any issues or contributions, feel free to raise an issue or submit a pull request.

Enjoy using **CACLytics** 🚀!

