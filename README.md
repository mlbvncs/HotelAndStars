# 🏨 HotelAndStars - Business Intelligence Dimensional Modeling

Business Intelligence project demonstrating dimensional modeling transformation from transactional (OLTP) to analytical (OLAP) using SQL Server Management Studio.

---

## 🎯 Quick Overview

**HotelAndStars** is a BI project for a fictional hotel chain that translates business questions into a data warehouse using the **Star Schema model**.

### Manager's Requirements:
- ✅ How many accommodations per day (and by type)
- ✅ Daily revenue metrics
- ✅ Customer geographic distribution (country, state, city)
- ✅ Seasonal patterns (holidays & school vacations influence)
- ❌ Personal data (no individual tracking needed)

**For complete technical documentation, see [Analysis.pdf](./Analysis.pdf)**

---

## 🏗️ Architecture

```
┌──────────────────────────────┐
│   OLAP (Analytical Layer)    │
│   Star Schema for BI         │
├──────────────────────────────┤
│   Data Transformation        │
├──────────────────────────────┤
│   OLTP (Operational Layer)   │
│   Entity-Relationship Model  │
└──────────────────────────────┘
```

### Dimensional Model (Star Schema)

**Fact Table:**
- `fact_stay` - Daily accommodation metrics (revenue, count)

**Dimensions:**
1. `dim_customer_location` - Where customers are from
2. `dim_accommodation_type` - Types of accommodations
3. `dim_time` - Dates with holiday & vacation flags

---

## 🛠 Technologies

| Component | Technology |
|-----------|-----------|
| **Database** | SQL Server 2019+ |
| **Design Tool** | SQL Server Management Studio (SSMS) |
| **Version Control** | Git |

---

## 📂 Project Structure

```
HotelAndStars/
├── 1. Models/
│   ├── 1. Relational/          # OLTP Entity-Relationship Model
│   └── 2. Dimensional/         # OLAP Star Schema
├── 2. Translations/            # Portuguese documentation
├── Analysis.pdf                # Complete technical specification
├── README.md
└── LICENSE
```

---

## 📊 Data Models

### OLTP: Entity-Relationship Model

| Entity | Purpose |
|--------|---------|
| **Customer** | Geographic information |
| **Accommodation** | Room/unit details |
| **Accommodation Type** | Room categories |
| **Stay** | Booking records |
| **Holiday** | Holiday calendar |
| **School Vacation** | Vacation periods |

### OLAP: Star Schema

#### **Fact Table: fact_stay**
- Grain: One row per accommodation per day
- Metrics: `stay_daily_rate` (revenue), `amount` (count)
- Foreign Keys: customer_location, accommodation_type, time

#### **Dimensions**

| Dimension | Columns |
|-----------|---------|
| **dim_customer_location** | customer_id, country, state, city |
| **dim_accommodation_type** | accommodation_type_id, name |
| **dim_time** | date, day, month, year, weekday, quarter, holiday_flag, vacation_flag |

---

## 🚀 Getting Started

### Prerequisites
- **SQL Server 2019+** (Developer Edition is free)
- **SQL Server Management Studio (SSMS)** v18.0+
- **Git**

### Quick Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/mlbvncs/HotelAndStars.git
   cd HotelAndStars
   ```

2. **Read the Analysis:**
   - Open `Analysis.pdf` for complete specifications
   - Review ERM and Dimensional Model design rationale

3. **Examine the Models:**
   - `1. Models/1. Relational/` - OLTP Entity-Relationship diagram
   - `1. Models/2. Dimensional/` - OLAP Star Schema diagram

---

## 📚 Key Concepts

### OLTP vs OLAP

**OLTP (Operational):**
- Normalized for fast transactions
- Used for: Booking systems, reservations
- Daily operations

**OLAP (Analytical):**
- Denormalized for fast queries
- Used for: Reports, dashboards, analysis
- Optimized for aggregations

### Star Schema Benefits

✅ Simple and intuitive  
✅ Fast queries (fewer joins)  
✅ Flexible drill-down analysis  
✅ Industry standard (Kimball methodology)

---

## 💡 Analysis Examples

With this model, answer questions like:

📊 *"Total revenue: holidays vs regular days?"*
- Slice by: `time_holiday = YES/NO`
- Measure: `SUM(stay_daily_rate)`

📊 *"Most popular accommodation types by country?"*
- Group by: `customer_country`, `accommodation_type_name`
- Measure: `COUNT(amount)`

📊 *"School vacation impact on occupancy?"*
- Compare: `time_vacation = YES vs NO`
- Measure: `SUM(amount)`

---

## 🎓 Learning Outcomes

✅ Database normalization & denormalization  
✅ OLTP vs OLAP architectural patterns  
✅ Star Schema dimensional modeling  
✅ SQL Server SSMS design tools  
✅ Business requirements to technical specifications  

---

## 🤝 Contributing

Contributions welcome! Fork → Branch → Commit → Push → PR

**Ideas:**
- 🔧 Improved SQL implementations
- 📝 Additional translations
- 🐛 Model refinements
- ✨ Enhancement suggestions

---

## 📄 License

MIT License - see [LICENSE](LICENSE) for details.

**For educational and portfolio purposes.**

---

## 👤 Author

**Malba Vinicius Lopes Santos**  
🐙 GitHub: [@mlbvncs](https://github.com/mlbvncs)

---

**Last Updated:** June 6, 2026  
**Status:** Complete  
**Type:** Educational Portfolio

⭐ **If you find this useful, please consider starring the repository!**
