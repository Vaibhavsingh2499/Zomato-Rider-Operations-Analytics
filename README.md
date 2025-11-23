# Zomato-Rider-Operations-Analytics
<img width="793" height="400" alt="image" src="https://github.com/user-attachments/assets/cf541389-f1f2-49c3-b087-804af77e76d9" />


This project presents a complete operational analytics deep-dive into Zomato-style last-mile delivery performance using rider-level order data.  
It examines where delays occur in the delivery funnel, why cancellations happen, and how delivery efficiency can be improved using data-driven insights.

The project includes data cleaning, feature engineering, exploratory analysis, DAX measures, and interactive Power BI dashboards — all structured like a real business analytics case study.

---

## 📦 **Dataset Access**

Due to GitHub’s 25 MB file limit, the dataset (both raw and cleaned versions) is stored on Google Drive.

👉 **Download Dataset (Raw + Cleaned Files):**  
https://drive.google.com/drive/folders/1R8aR6bx9XsujSE-ygAmaRVFJ8Oyka7Wj?usp=drive_link

**Files included:**
- `Rider-Info Raw.xlsx`
- `Rider-Info CLEAN.xlsx` (fully processed dataset used in Power BI)

---

## 🎯 **Problem Statement**

To evaluate and optimize operational efficiency in Zomato-style last-mile delivery by analyzing:

- End-to-end delivery delays  
- Rider performance patterns  
- Restaurant preparation bottlenecks  
- Cancellations and undelivered orders  
- Distance and time-of-day impact on delivery time  

The goal is to identify actionable operational insights and propose strategies to enhance delivery speed, reduce cancellations, and increase overall reliability.

---

## 🧰 **Tools Used**

- **Excel** → Data cleaning, preprocessing, feature creation  
- **Power BI** → Data modeling, DAX measures, dashboards  
- **GitHub** → Documentation and version control


## 📊 **Dataset Overview**

Each row represents a **single order handled by a rider**.  
Key columns include:

### **Timestamps**
- `order_time`
- `allot_time`
- `accept_time`
- `pickup_time`
- `delivered_time`

### **Rider Information**
- `rider_id`
- `lifetime_order_count`
- `session_time`

### **Distances**
- `first_mile_distance`
- `last_mile_distance`
- `Total Distance`

### **Order-Level Status**
- `delivered_orders`
- `cancelled`
- `undelivered`
- `Order Status`

### **Derived Operational Metrics (Created During Cleaning)**
- Acceptance Delay  
- Pickup Delay  
- Delivery Time  
- Turnaround Time  
- Total Distance  
- Efficiency (Orders per Hour)  
- TAT Bucket (0–10, 10–20, 20–30, etc.)

---

## 🔧 **Data Cleaning & Feature Engineering (Excel)**

Key cleaning and engineering steps included:

- Converting all time columns → datetime  
- Removing nulls in rider IDs and critical time fields  
- Replacing blank operational columns with zeros  
- Creating new operational features:
  - `Acceptance_Delay = accept_time – allot_time`
  - `Pickup_Delay = pickup_time – accept_time`
  - `Delivery_Time = delivered_time – pickup_time`
  - `Turnaround_Time = delivered_time – order_time`
  - `Total_Distance = first_mile_distance + last_mile_distance`
  - `Efficiency = delivered_orders / session_time`
  - `Order_Status` (Delivered / Cancelled / Undelivered)

---

## 📈 **Dashboards**

### **1️⃣ Overview Dashboard**

Shows high-level KPIs:
- Total Orders  
- Delivered Orders  
- Cancelled Orders  
- Undelivered Orders  
- Average Turnaround Time  
- Average Distance  
- Average Delivery Time  
- Rider Efficiency  
- Orders Over Time  
- Order Status Distribution  

📌 *Screenshot:*  
![Overview Dashboard](https://github.com/Vaibhavsingh2499/Zomato-Rider-Operations-Analytics/blob/main/Zomato%20Rider%20Overview%20.png)

---

### **2️⃣ Delay Analysis Dashboard**

Helps identify operational bottlenecks:
- Average delay by stage (Acceptance / Pickup / Delivery / Turnaround)
- Delay by hour of day
- Turnaround Time vs Distance (scatter plot)
- TAT bucket distribution
- TAT by Order Status

📌 *Screenshot:*  
![Delay Analysis Dashboard](https://github.com/Vaibhavsingh2499/Zomato-Rider-Operations-Analytics/blob/main/image.png)

---

## 🔍 **Key Insights**

### **Delay Insights**
- Pickup Delay is the largest contributor to total turnaround time.  
- Evening hours (7–10 PM) show the highest delays.  
- Morning deliveries (9 AM – 1 PM) are fastest.  
- Orders longer than 4–5 km frequently exceed 30 minutes.  
- Cancellations increase sharply during delay-heavy hours.

### **Order Flow Insights**
- Undelivered orders are unusually high, indicating operational instability.  
- Riders respond quickly; acceptance delays are minimal.  
- Majority of orders fall in the 20–40 min TAT sweet spot.

### **Business Impact Insights**
- Small reduction in pickup delay → major improvement in TAT.  
- Distance and kitchen speed are the strongest predictors of delivery success.

---

## 💡 **Business Recommendations**

- Enforce restaurant SLAs and implement a prep-time prediction model.  
- Strengthen peak-hour rider allocation (7–10 PM).  
- Reduce delivery radius for slow-performing kitchens.  
- Implement smart distance-based batching.  
- Use real-time heatmaps for rider deployment.  
- Introduce efficiency-based incentives for riders.  
- Improve kitchen load forecasting to reduce bottlenecks.  
- Optimize auto-reassignment logic for faster acceptance.  

Full detailed recommendations available in:  
📄 `https://github.com/Vaibhavsingh2499/Zomato-Rider-Operations-Analytics/blob/main/Zomato%20Rider%20%26%20Delivery%20Operations%20Insights%20and%20Business%20Recommendations.pdf`

---

## 🧪 **How to Use This Project**

1. Download the dataset from Google Drive  
2. Open the Power BI file:
   - `/dashboard/Zomato_Rider_Operations.pbix`
3. Refresh the data source path to:
   - `Rider-Info CLEAN.xlsx`
4. Explore:
   - Overview Page  
   - Delay Analysis Page  
   - Insights Document  

--


