# 📊 IT Asset Management Power BI Dashboard  
### Complete IT Asset Lifecycle, Warranty, Risk, Utilization & Cost Analysis  

This project presents a comprehensive **IT Asset Management (ITAM)** analytics dashboard built using **Power BI**.  
Using a Kaggle dataset, the solution simulates a real enterprise ITAM environment and demonstrates strong skills in:

- Power Query transformation  
- Data modeling & relationships (Star Schema)  
- DAX measures & KPIs  
- IT lifecycle reporting (EOL, Warranty, Risk)  
- Professional dashboard design & visualization  

---

## 📁 Dataset

**Source:** Kaggle — IT Asset Management Dataset  
**Rows:** 50  
**Columns include:**

- `AssetType`
- `Department`
- `PurchaseDate`
- `WarrantyExpiry`
- `LicenseExpiry`
- `RiskLevel`
- `Status`
- `MaintenanceCost`
- `VendorName`

### **Calculated Fields**

- `AssetAge`
- `DaysToWarrantyExpiry`
- `IsEOL`
- `WarrantyStatus`
- `IsUnderutilized`

---

## 🧩 Data Modeling

The data model consists of:

### **Fact Table**
- `cleaned_asset_management_data`

### **Date Dimension Table**
Created using DAX:

DateTable =
ADDCOLUMNS(
CALENDAR(MIN(cleaned_asset_management_data[PurchaseDate]),
MAX(cleaned_asset_management_data[WarrantyExpiry])),
"Year", YEAR([Date]),
"Month", FORMAT([Date], "MMM"),
"YearMonth", FORMAT([Date], "YYYY-MM")
)


### **Relationships**
- `PurchaseDate` → `DateTable[Date]`  
- `WarrantyExpiry` → `DateTable[Date]`  
- `LicenseExpiry` → `DateTable[Date]`

---

## 🖥 Dashboard Pages

# **PAGE 1 — Executive Summary Dashboard**
*(Insert your screenshot below)*

![Executive Dashboard](assets/dashboard_page1.png)

### 🔍 **Key Highlights**

- ✔ Total Asset Count  
- ✔ Active vs. Inactive Assets  
- ✔ Underutilized Assets  
- ✔ End-of-Life (EOL) Forecast  
- ✔ Out-of-Warranty Assets  
- ✔ Total Cost Summary  
- ✔ Asset Distribution by Department & AssetType  
- ✔ Warranty Status Breakdown  
- ✔ Cost Trends Over Years  
- ✔ Slicers for Department, Location, AssetType, Status, RiskLevel  

### **Visuals on This Page**

- KPI Cards (Total, Active, EOL, Underutilized, Out-of-Warranty, Total Cost)  
- Assets by Department  
- Assets by Asset Type  
- Warranty Status Donut  
- Total Cost by Year (Line Chart)  

---

# **PAGE 2 — Lifecycle & Optimization Dashboard**
*(Insert your screenshot below)*

![Lifecycle Dashboard](assets/dashboard_page2.png)

### 🔍 **Key Highlights**

- ✔ Lifecycle Distribution (In Lifecycle vs. EOL)  
- ✔ Warranty Risk by Department  
- ✔ Warranty Expiry Timeline  
- ✔ Asset Age Distribution  
- ✔ Underutilized Assets by Business Units  
- ✔ High-Risk Asset Matrix  

### **Visuals on This Page**

- KPI Cards (High Risk, EOL Assets, Avg Asset Age, Out-of-Warranty)  
- Lifecycle Donut Chart  
- Warranty Risk by Department  
- Warranty Expiry Bar/Line  
- Asset Age Histogram  
- Underutilized Asset Distribution  
- High-Risk Asset Table (AssetID, Type, Department, Risk, Warranty, Dates)  

---

## 🧠 Technical Skills Demonstrated

### **Power BI Skills**
- Power Query cleaning & normalization  
- Data modeling (relationships, star schema)  
- DAX: KPIs, calculated columns, measures  
- Time Intelligence (Year, Quarter, Month)  
- Interactive dashboard design (UX, slicers, drill-through)  

### **IT Domain Skills**
- IT Asset Lifecycle Management  
- Warranty & Compliance Analysis  
- Asset Utilization Monitoring  
- EOL & Replacement Forecasting  
- Risk Analysis & Categorization  
- ITAM/CMDB Reporting Fundamentals  

---

## 📂 Folder Structure

IT-Asset-Management-PowerBI-Dashboard/
│── IT_Asset_Management.pbix
│── README.md
│── assets/
│ ├── dashboard_page1.png
│ ├── dashboard_page2.png
│ └── kpi_summary.png

