# 🚕 Uber NYC Rides Analysis Dashboard 📊

## ✨ Project Overview

This project aims to analyze Uber trip data in New York City to understand key patterns and trends in rider and driver behavior. A combination of Python (Jupyter Notebook) was used for initial data preparation, and Power BI was utilized to build an interactive and impactful dashboard to uncover actionable insights.

## 🚀 Key Objectives

* Clean and prepare raw Uber trip data.
* Explore temporal patterns of rides (by hour, day, month).
* Understand the distribution of passenger counts per trip.
* Identify the most active pick-up locations.
* Build an interactive dashboard in Power BI to enable users to easily explore the data.

## 💾 Data Source

The data used in this analysis is a dataset specific to Uber trips in New York City. The file includes data such as:
* `key`: Unique identifier for each trip.
* `fare_amount`: Fare amount of the trip.
* `pickup_datetime`: Date and time of trip start.
* `pickup_longitude`, `pickup_latitude`: Longitude and latitude coordinates of the pick-up point.
* `dropoff_longitude`, `dropoff_latitude`: Longitude and latitude coordinates of the drop-off point.
* `passenger_count`: Number of passengers in the trip.

## 🛠 Tools Used

* **Python (Jupyter Notebook):** For initial data processing, cleaning, and adding helper columns.
    * Pandas: For data manipulation.
* **Microsoft Power BI Desktop:** For data modeling, creating measures (DAX), and designing the interactive dashboard.
* **GitHub:** For hosting the project file (`.pbix`) and project documentation.

## 🧹 Data Preparation Steps (Jupyter Notebook)

The following steps were performed in a Jupyter Notebook environment to ensure data quality and readiness for analysis in Power BI:

1.  **Load Data:** Read the `uber.csv` file into a Pandas DataFrame.
2.  **Initial Data Cleaning:**
    * Remove duplicate rows.
    * Handle missing values.
    * Filter data to remove anomalous/unreasonable values such as:
        * `fare_amount` less than 0 or greater than a reasonable value.
        * `passenger_count` less than 1 or greater than a reasonable value.
        * `latitude`, `longitude` coordinates outside the reasonable geographic range for New York City.
3.  **Data Type Conversion:** Ensure columns have the correct data types (e.g., converting `pickup_datetime` to datetime format).
4.  **Create Derived Time-based Columns:**
    * **`Hour`:** Extract the hour from `pickup_datetime`.
    * **`DayOfWeek`:** Extract the day name from `pickup_datetime` (e.g., Monday, Tuesday).
    * **`Month`:** Extract the month name from `pickup_datetime` (e.g., January, February).
    * **`DayOfWeekNumber`:** Extract the day number from `pickup_datetime` (for correct sorting in Power BI).
    * **`MonthNumber`:** Extract the month number from `pickup_datetime` (for correct sorting in Power BI).
5.  **Save Cleaned Data:** The processed data was exported to a new CSV file (or directly loaded into Power BI) for subsequent use.

## 📊 Data Modeling & Measures (Power BI Desktop & DAX)

In Power BI Desktop, the following were implemented:

1.  **Data Loading:** Imported the cleaned data file.
2.  **Manage Relationships:** (If multiple tables were present).
3.  **Set Data Categories:**
    * `pickup_latitude` was set as `Latitude`.
    * `pickup_longitude` was set as `Longitude`.
4.  **Apply Sort by Column:**
    * The `DayOfWeek` column was set to sort by `DayOfWeekNumber` to ensure correct day order in visuals.
    * The `Month` column was set to sort by `MonthNumber` to ensure correct month order in visuals.
5.  **Create DAX Measures:**
    * **`Total Uber Rides`:** A measure to calculate the total count of rides (e.g., `COUNTROWS('YourTableName')` or `COUNT('YourTableName'[key])`).
    * **`Average Trip Fare`:** A measure to calculate the average trip fare (e.g., `AVERAGE('YourTableName'[fare_amount])`).

## 📈 Visualizations & Dashboard

An interactive dashboard was designed featuring the following key visualizations:

* **Card:** Displaying **"Total Uber Rides"**.
* **Card:** Displaying **"Average Trip Fare"**.
* **Clustered Column Chart:** Showing **"Uber Ride Distribution by Hour"**.
* **Clustered Column Chart:** Showing **"Uber Ride Distribution by Day of Week"**.
* **Clustered Column Chart:** Showing **"Uber Ride Distribution by Month"**.
* **Clustered Column Chart:** Showing **"Passenger Count Distribution"**.
* **Map Visual:** Displaying **"Uber Pick-up Locations Map"**, with bubble sizes varying based on ride count.
* **Slicer:** For interactive filtering by **"Day of Week"** (dropdown style).
* **Slicer:** For interactive filtering by **"Month"** (dropdown style).
* **Main Title Bar:** Providing an attractive and clear title for the dashboard.


## 🧑‍💻 Contributors

* [Khoshaba Odeesho/Assyrian91](https://github.com/Assyrian91)

---
