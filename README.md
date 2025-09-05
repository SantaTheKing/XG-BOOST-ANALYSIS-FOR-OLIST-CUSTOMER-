# OLIST E-commerce Data Analytics Pipeline

## 📋 Project Overview

This project presents a comprehensive data analytics pipeline for **OLIST**, Brazil's largest department store marketplace that connects small businesses nationwide. The analysis covers approximately **100,000 orders** from October 2016 to October 2018, providing insights into customer behavior, seller performance, and demand forecasting.

### 🎯 Objectives
- Build a complete PostgreSQL database from raw CSV data
- Perform exploratory data analysis using SQL queries
- Develop time series forecasting models for demand planning
- Create interactive dashboards for business intelligence

## 📊 Dataset Information

**Source**: [OLIST Dataset on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

**Scope**: ~100,000 orders (October 2016 - October 2018)

**Data Components**:
- 👥 Customers information and demographics
- 🏪 Sellers data and locations
- 📦 Orders and order items
- 💳 Payment methods and transactions
- ⭐ Product reviews and ratings
- 🌍 Geolocation data

## 🗂️ Project Structure

```
olist_customer/
├── OLIST DATA/                    # Raw CSV datasets
│   ├── olist_customers_dataset.csv
│   ├── olist_orders_dataset.csv
│   ├── olist_order_items_dataset.csv
│   ├── olist_order_payments_dataset.csv
│   ├── olist_order_reviews_dataset.csv
│   ├── olist_products_dataset.csv
│   ├── olist_sellers_dataset.csv
│   └── olist_geolocation_dataset.csv
├── create_table.sql               # Database schema creation
├── import_data.sql               # Data import scripts
├── ANALISIS CON SQL.ipynb        # SQL exploratory analysis
├── XG-BOOST DEMANDPLANIING.ipynb # ML forecasting models
└── README.md                     # Project documentation
```

## 🚀 Setup Instructions

### Prerequisites
- Python 3.12
- PostgreSQL with pgAdmin4
- Jupyter Notebook

### 1. Database Setup

**Step 1**: Create PostgreSQL Database
```sql
-- Run in pgAdmin4 or psql
CREATE DATABASE olist;
```

**Step 2**: Create Tables
```bash
# Execute the table creation script
psql -d olist -f create_table.sql
```

**Step 3**: Import Data
```bash
# Update file paths in import_data.sql to match your local directory
# Then execute the import script
psql -d olist -f import_data.sql
```

### 2. Python Environment Setup

**Install Required Dependencies**:
```bash
pip install pmdarima holidays plotly xgboost matplotlib statsmodels scikit-learn numpy
pip install "numpy<2.0" "pmdarima==2.0.4"
```

**Core Libraries**:
- `pandas` - Data manipulation and analysis
- `numpy` - Numerical computing
- `matplotlib` - Data visualization
- `statsmodels` - Statistical modeling
- `scikit-learn` - Machine learning algorithms
- `xgboost` - Gradient boosting framework
- `pmdarima` - Time series analysis
- `holidays` - Holiday calendar integration

## 📈 Project Workflow

### Phase 1: Database Construction
- **File**: `create_table.sql`, `import_data.sql`
- **Objective**: Build normalized PostgreSQL database
- **Output**: Structured relational database with 8 interconnected tables

### Phase 2: SQL Exploratory Analysis
- **File**: `ANALISIS CON SQL.ipynb`
- **Key Analyses**:
  - 📊 Order volume trends and patterns
  - ⏱️ Delivery time performance metrics
  - 👥 Customer segmentation analysis
  - 🏆 Top-performing sellers by revenue
  - 🌍 Geographic distribution insights
  - 💰 Payment method preferences

### Phase 3: Machine Learning Forecasting
- **File**: `XG-BOOST DEMANDPLANIING.ipynb`
- **Models Implemented**:
  - **SARIMAX**: Seasonal AutoRegressive Integrated Moving Average with eXogenous factors
  - **XGBoost**: Extreme Gradient Boosting for time series
- **Features**:
  - Calendar feature engineering (day, month, year, weekday)
  - Seasonal decomposition analysis
  - Model comparison and validation
  - 7-day ahead demand forecasting

### Phase 4: Business Intelligence Dashboard
- **Tool**: Power BI
- **Components**:
  - Sales performance KPIs
  - Interactive geographic visualizations
  - Trend analysis charts
  - Strategic decision-making metrics

## 🔍 Key Insights & Results

### SQL Analysis Highlights
- **Order Patterns**: Identified peak ordering periods and seasonal trends
- **Delivery Performance**: Analyzed delivery time distributions across regions
- **Customer Behavior**: Segmented customers by purchase frequency and value
- **Seller Analytics**: Ranked top performers by revenue and order volume

### Machine Learning Results
- **Model Performance**: Comparative analysis between SARIMAX and XGBoost
- **Forecasting Accuracy**: Validated models using time series cross-validation
- **Demand Predictions**: Generated 7-day rolling forecasts for inventory planning

## 🛠️ Technologies Used

| Category | Technologies |
|----------|-------------|
| **Database** | PostgreSQL, pgAdmin4 |
| **Programming** | Python 3.12, SQL |
| **Data Analysis** | Pandas, NumPy, Jupyter Notebook |
| **Machine Learning** | XGBoost, SARIMAX, Scikit-learn |
| **Visualization** | Matplotlib, Plotly, Power BI |
| **Time Series** | Statsmodels, pmdarima |

## 📋 Usage Instructions

1. **Database Analysis**: Open `ANALISIS CON SQL.ipynb` to explore SQL-based insights
2. **Forecasting Models**: Run `XG-BOOST DEMANDPLANIING.ipynb` for demand predictions
3. **Custom Queries**: Use the PostgreSQL database for additional analysis
4. **Dashboard**: Import data into Power BI for interactive visualizations

## 🎯 Business Impact

This analytics pipeline enables:
- **Inventory Optimization**: Accurate demand forecasting reduces stockouts and overstock
- **Performance Monitoring**: Real-time tracking of seller and delivery metrics
- **Strategic Planning**: Data-driven insights for business expansion decisions
- **Customer Experience**: Understanding delivery patterns to improve satisfaction

## 🔮 Future Enhancements

- Real-time data pipeline integration
- Advanced ML models (LSTM, Prophet)
- Automated reporting and alerting
- Customer lifetime value prediction
- Recommendation system development

## 📞 Contact & Support

For questions or contributions to this project, please refer to the analysis notebooks for detailed methodology and implementation notes.

---

**Project Status**: ✅ Complete  
**Last Updated**: 2024  
**Analysis Period**: October 2016 - October 2018