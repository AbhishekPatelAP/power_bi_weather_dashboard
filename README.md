# 🌦️ Real-Time Weather and Air Quality Dashboard using Power BI & WeatherAPI

This project demonstrates how to build a **real-time Weather and Air Quality Index (AQI) Dashboard** in **Power BI** using data from the [WeatherAPI](https://www.weatherapi.com/). It includes live weather metrics, AQI indicators, and dynamic city filters — ideal for learning or deploying a live weather monitoring report.

---

Here’s a preview of the Power BI Weather Dashboard :

![Dashboard Screenshot](https://github.com/AbhishekPatelAP/power_bi_weather_dashboard/blob/main/screenshots/1.png)



## 📌 Features

- 🔄 **Live weather data** integration via API  
- 📊 Dynamic Power BI visuals: cards, gauges, charts, and maps  
- 🌫️ **AQI Indicators** (color-coded) for multiple pollutants (PM2.5, CO, NO₂, etc.)  
- 📍 City-wise filtering and dynamic interactivity  
- 🎨 Clean design with weather icons and intuitive layout  

---

## 🔧 Prerequisites

To use or replicate this project, ensure you have :

- ✅ [Power BI Desktop](https://app.powerbi.com/groups/me/reports/1a283fdf-8bdf-47dc-9af7-0413840e76f8/7f5b1b168225399960d0?experience=power-bi)
- ✅ An account at [WeatherAPI.com](https://www.weatherapi.com/) (free/paid)  
- ✅ Basic Power BI skills (data transformation, visualization)  

---

## 🗝️ Step 1: Get WeatherAPI Key

1. Sign up at [WeatherAPI](https://www.weatherapi.com/).
2. Go to your profile and copy the **API key**.

---

## 🌐 Step 2: Build API URL

Use the following endpoint to get current weather data for a city:


Replace `YOUR_API_KEY` and `CITY_NAME` with your credentials.

---

## 🔌 Step 3: Connect Power BI to WeatherAPI

1. Open Power BI Desktop  
2. Click on **Get Data → Web**  
3. Paste your API URL  
4. Click **OK**  
5. Power Query Editor will open — expand the `current` record  
6. Expand sub-records like `condition` and `air_quality`  
7. Rename columns appropriately  
8. Click **Close & Apply**

---

## 🧠 Step 4: Add AQI Logic (DAX)

Here are some reusable DAX measures you can use:

### 🎨 AQI Color
```DAX
AQI Color = 
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm2_5]), 0)
RETURN
SWITCH(
    TRUE(),
    AQI <= 50, "#43d946",        // Good
    AQI <= 100, "#fff570",       // Moderate
    AQI <= 150, "#ff9800",       // Poor
    AQI <= 200, "#d99343",       // Unhealthy
    AQI <= 300, "#ff5b0f",       // Very Unhealthy
               "#d95243"         // Hazardous
)

## 📌 Features

- 🔄 **Live weather data** integration via API  
- 📊 Dynamic Power BI visuals: cards, gauges, charts, and maps  
- 🌫️ **AQI Indicators** (color-coded) for multiple pollutants (PM2.5, CO, NO₂, etc.)  
- 📍 City-wise filtering and dynamic interactivity  
- 🎨 Clean design with weather icons and intuitive layout  

---

## 🔧 Prerequisites

To use or replicate this project, ensure you have:

- ✅ [Power BI Desktop](https://powerbi.microsoft.com/desktop/) installed  
- ✅ An account at [WeatherAPI.com](https://www.weatherapi.com/) (free/paid)  
- ✅ Basic Power BI skills (data transformation, visualization)  

---

## 🗝️ Step 1: Get WeatherAPI Key

1. Sign up at [WeatherAPI](https://www.weatherapi.com/).
2. Go to your profile and copy the **API key**.

---

## 🌐 Step 2: Build API URL

Use the following endpoint to get current weather data for a city:


Replace `YOUR_API_KEY` and `CITY_NAME` with your credentials.

---

## 🔌 Step 3: Connect Power BI to WeatherAPI

1. Open Power BI Desktop  
2. Click on **Get Data → Web**  
3. Paste your API URL  
4. Click **OK**  
5. Power Query Editor will open — expand the `current` record  
6. Expand sub-records like `condition` and `air_quality`  
7. Rename columns appropriately  
8. Click **Close & Apply**

---

## 🧠 Step 4: Add AQI Logic (DAX)

Here are some reusable DAX measures you can use:

### 🎨 AQI Color
```DAX
AQI Color = 
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm2_5]), 0)
RETURN
SWITCH(
    TRUE(),
    AQI <= 50, "#43d946",        // Good
    AQI <= 100, "#fff570",       // Moderate
    AQI <= 150, "#ff9800",       // Poor
    AQI <= 200, "#d99343",       // Unhealthy
    AQI <= 300, "#ff5b0f",       // Very Unhealthy
               "#d95243"         // Hazardous
)
````

### 🧾 AQI Suggestion

```DAX
AQI Suggestion = 
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm2_5]), 0)
RETURN
SWITCH(
    TRUE(),
    AQI <= 50, "Air is clean and healthy",
    AQI <= 100, "Acceptable air quality, stay active",
    AQI <= 150, "Sensitive groups should reduce outdoor time",
    AQI <= 200, "Limit prolonged outdoor exertion",
    AQI <= 300, "Avoid outdoor activity if possible",
              "Stay indoors, wear a mask if outside"
)
```

### 🚦 AQI Status

```DAX
AQI Status = 
VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm2_5]), 0)
RETURN
SWITCH(
    TRUE(),
    AQI <= 50, "Good",
    AQI <= 100, "Moderate",
    AQI <= 150, "Unhealthy for Sensitive",
    AQI <= 200, "Unhealthy",
    AQI <= 300, "Very Unhealthy",
              "Hazardous"
)
```

> Replace `pm2_5` with other pollutants like `co`, `no2`, etc., to customize for various AQI measures.

---

## 🧱 Step 5: Design Your Dashboard

Use Power BI visuals to build your report:

* **Cards** for: Temperature, Humidity, UV, Visibility
* **Gauges** for Wind Speed
* **Line/Bar Charts** for hourly or daily trends
* **Map Visual** for city-based weather
* **Slicers** for filtering by city or AQI status

---

## 🙌 Credits

Created by [Abhishek Patel](https://github.com/AbhishekPatelAP)
Data provided by [WeatherAPI.com](https://www.weatherapi.com/)


