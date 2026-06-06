# 🏨 HotelAndStars - Business Intelligence Dimensional Modeling

> A comprehensive Business Intelligence project demonstrating database modeling transformation from transactional (OLTP) to analytical (OLAP) structures using SQL Server Management Studio.

**Status:** ✅ Complete | **Last Updated:** June 6, 2026

---

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Business Requirements](#-business-requirements)
- [Architecture](#-architecture)
- [Technical Stack](#-technical-stack)
- [Project Structure](#-project-structure)
- [Data Models](#-data-models)
- [Getting Started](#-getting-started)
- [Key Concepts](#-key-concepts)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Project Overview

**HotelAndStars** is a Business Intelligence project for a fictional hotel chain management company. The project demonstrates the complete lifecycle of dimensional modeling—from understanding business requirements, building a transactional Entity-Relationship Model (ERM/OLTP), and transforming it into an analytical Dimensional Model (OLAP) using Star Schema design principles.

This project is ideal for learning:
- How to translate business questions into data models
- The architectural differences between transactional (OLTP) and analytical (OLAP) databases
- Star Schema design for Business Intelligence
- Practical SQL Server modeling with SSMS

---

## 📊 Business Requirements

### The Manager Wants to Know:

✅ **Daily Sales Analysis**
- How many accommodations are sold per day
- What types of accommodations are most popular

✅ **Revenue Insights**
- Daily revenue metrics
- Revenue trends and patterns

✅ **Customer Geographic Distribution**
- Where customers are from (country, state, city)
- Geographic trends in bookings

✅ **Seasonal Patterns**
- How holidays influence accommodation sales
- How school vacations affect occupancy rates

### What They Don't Need:

❌ Personally identifiable information (who stayed)
- The model is designed for aggregate analysis, not individual tracking

---

## 🏗️ Architecture

### Two-Layer Database Design

```
┌─────────────────────────────────────────────────────┐
│    OLAP (Analytical Database)                       │
│    Star Schema - Business Intelligence              │
│    Used for: Reporting, Analysis, Dashboards        │
├─────────────────────────────────────────────────────┤
│              ↑ Data Transform ↑                      │
├─────────────────────────────────────────────────────┤
│    OLTP (Transactional Database)                    │
│    Entity-Relationship Model - Business Operations  │
│    Used for: Daily operations, Data Entry           │
└─────────────────────────────────────────────────────┘
```

---

## 🛠 Technical Stack

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Database Platform** | SQL Server 2019+ | Enterprise relational database |
| **Design & Development** | SQL Server Management Studio (SSMS) | Database modeling and visualization |
| **Version Control** | Git | Source code management |
| **Repository** | GitHub | Collaboration and documentation |
| **Documentation** | Markdown & PDF | Project specifications |

---

## 📂 Project Structure

```
HotelAndStars/
│
├── 📁 1. Models/
│   │
│   ├── 📁 1. Relational/
│   │   ├── 📊 ERM_HotelAndStars.png (or .bak)
│   │   └── Entity-Relationship Model diagram
│   │       - Shows operational database design
│   │       - Customer, Accommodation, Stay, Holiday tables
│   │       - Primary/Foreign key relationships
│   │
│   └── 📁 2. Dimensional/
│       ├── 📊 DM_HotelAndStars.png (or .bak)
│       └── Dimensional Model diagram
│           - Shows analytical database design
│           - 3 Dimensions + 1 Fact Table
│           - Star Schema structure
│
├── 📁 2. Translations/
│   ├── 📄 Analise_DM_pt-br.md
│   └── Brazilian Portuguese documentation
│
├── 📄 Analysis.pdf
│   └── Complete project specification and design rationale
│
├── 📄 README.md
│   └── This file
│
├── 📄 LICENSE
│   └── MIT License
│
└── 📄 .gitignore
    └── Git configuration
```

---

## 📊 Data Models

### OLTP: Entity-Relationship Model (ERM)

**Core Entities:**

| Entity | Purpose | Key Attributes |
|--------|---------|-----------------|
| **Customer** | Customer information | customer_id, customer_name, customer_country, customer_state, customer_city |
| **Accommodation** | Hotel room/unit details | accommodation_id, accommodation_type_id, accommodation_capacity |
| **Accommodation Type** | Room categories | accommodation_type_id, accommodation_type_name |
| **Stay** | Booking records | stay_id, customer_id, accommodation_id, stay_check_in, stay_check_out, stay_daily_rate |
| **Holiday** | Holiday calendar | holiday_date, holiday_name |
| **School Vacation** | Vacation periods | vacation_start_date, vacation_end_date |

### OLAP: Dimensional Model (Star Schema)

#### **Fact Table: fact_stay**

The central fact table measuring hotel occupancy and revenue at daily granularity.

| Column | Type | Description |
|--------|------|-------------|
| `stay_key` | INT (PK) | Primary Surrogate Key |
| `customer_location_key` | INT (FK) | Reference to customer location dimension |
| `accommodation_type_key` | INT (FK) | Reference to accommodation type dimension |
| `time_key` | INT (FK) | Reference to time dimension |
| `stay_daily_rate` | DECIMAL | Daily revenue per accommodation |
| `amount` | INT | Unit count (always 1, used for summation) |

**Grain:** One row per accommodation per day of stay

---

#### **Dimension Tables**

##### 1️⃣ **dim_customer_location**
*Answer: Where are the customers from?*

| Column | Description |
|--------|-------------|
| `customer_location_key` | Surrogate Key (PK) |
| `customer_id` | Natural Key |
| `customer_country` | Customer country of origin |
| `customer_state` | Customer state of origin |
| `customer_city` | Customer city of origin |

##### 2️⃣ **dim_accommodation_type**
*Answer: What types of accommodations are sold?*

| Column | Description |
|--------|-------------|
| `accommodation_type_key` | Surrogate Key (PK) |
| `accommodation_type_id` | Natural Key |
| `accommodation_type` | Accommodation category (e.g., Single, Double, Suite) |
| `accommodation_type_name` | Descriptive name |

##### 3️⃣ **dim_time**
*Answer: When were the stays booked? Are holidays/vacations influential?*

| Column | Description |
|--------|-------------|
| `time_key` | Surrogate Key (PK) |
| `time_date` | Full date (YYYY-MM-DD) |
| `time_day` | Day of month (1-31) |
| `time_month` | Month (1-12) |
| `time_year` | Year |
| `time_weekday` | Day of week (1-7) |
| `time_quarter` | Quarter (Q1-Q4) |
| `time_holiday` | Flag: Is this a holiday? (YES/NO) |
| `time_vacation` | Flag: Is this during school vacation? (YES/NO) |

---

## 🚀 Getting Started

### Prerequisites

- **SQL Server 2019 or later** (Developer Edition is free)
- **SQL Server Management Studio (SSMS)** v18.0+
- **Git** (for cloning the repository)
- **Windows, macOS, or Linux** with 4GB+ RAM

### Installation Steps

#### 1. Clone the Repository

```bash
git clone https://github.com/mlbvncs/HotelAndStars.git
cd HotelAndStars
```

#### 2. Review the Analysis Document

Open `Analysis.pdf` to understand:
- Complete business requirements
- ERM design decisions and entity relationships
- Dimensional Model specifications
- Data transformation logic

#### 3. Examine the Models

**For the OLTP Design:**
- Navigate to `1. Models/1. Relational/`
- Open the Entity-Relationship diagram in SSMS
- Study the normalized table structure and relationships

**For the OLAP Design:**
- Navigate to `1. Models/2. Dimensional/`
- Open the Dimensional Model diagram in SSMS
- Review the Star Schema with facts and dimensions

#### 4. Explore Translations (Optional)

For Brazilian Portuguese documentation:
- Check `2. Translations/` folder for localized analysis

---

## 📚 Key Concepts Explained

### OLTP vs OLAP

**OLTP (Online Transactional Processing)** - The ERM Model
- Optimized for **daily operations**
- Normalized structure (3NF) to prevent data redundancy
- Fast writes and updates
- Used for: Booking systems, reservations

**OLAP (Online Analytical Processing)** - The Dimensional Model
- Optimized for **analytical queries**
- Denormalized structure for query speed
- Optimized for reads and aggregations
- Used for: Reports, dashboards, trend analysis

### Star Schema Benefits

✅ **Simple & Intuitive** - Easy to understand dimension hierarchies
✅ **Fast Queries** - Fewer joins needed compared to normalized designs
✅ **Flexible Analysis** - Support for drill-down, slice-and-dice operations
✅ **Standard for BI** - Industry best practice (Kimball methodology)

---

## 📈 Analysis Examples

With this dimensional model, you can answer questions like:

🔍 **"What was the total revenue on holidays vs. regular days?"**
```
Slice by: time_holiday = YES/NO
Measure: SUM(stay_daily_rate)
```

🔍 **"Which accommodation types are most popular in each country?"**
```
Group by: customer_country, accommodation_type_name
Measure: COUNT(amount)
```

🔍 **"How does school vacation affect occupancy?"**
```
Compare: time_vacation = YES vs. NO
Measure: SUM(amount)
```

🔍 **"What is the daily revenue trend by city?"**
```
Drill-down: time_date, customer_city
Measure: SUM(stay_daily_rate)
```

---

## 🎓 Learning Outcomes

Completing this project will help you master:

✅ **Database Design Principles**
- Normalization and denormalization strategies
- Entity relationships and cardinality

✅ **Data Modeling Methodologies**
- OLTP architectural patterns
- OLAP and dimensional modeling
- Star Schema design (Kimball methodology)

✅ **SQL Server Skills**
- SSMS modeling tools
- Logical data model creation
- Database design best practices

✅ **Business Intelligence Thinking**
- Translating business requirements into technical specifications
- Defining facts, dimensions, and granularity
- Building models that support analytical queries

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!

### How to Contribute

1. **Fork** the repository
2. **Create** a feature branch:
   ```bash
   git checkout -b feature/your-amazing-feature
   ```
3. **Commit** your changes:
   ```bash
   git commit -m 'Add: Your amazing feature description'
   ```
4. **Push** to the branch:
   ```bash
   git push origin feature/your-amazing-feature
   ```
5. **Open** a Pull Request with a clear description

### Contribution Ideas

- 🔧 Improved SQL scripts or model implementations
- 📝 Additional documentation or translations
- 🐛 Bug reports or model refinements
- ✨ Enhancement suggestions

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

**Educational & Portfolio Use:** This project is provided for educational and portfolio purposes. Feel free to use it as a learning resource or reference for your own projects.

---

## 👤 Author

**Malba Vinicius Lopes Santos**

- 🐙 GitHub: [@mlbvncs](https://github.com/mlbvncs)
- 💼 Focus: Business Intelligence & Data Modeling
- 📧 Open to collaboration and feedback

---

## 📞 Support & Questions

For questions or issues:
1. Check the `Analysis.pdf` for detailed specifications
2. Review the model diagrams in the `1. Models/` folders
3. Open an issue on GitHub with detailed questions

---

<div align="center">

**⭐ If you find this project helpful, please consider starring it! ⭐**

Made with 💙 for Data Enthusiasts and BI Professionals

</div>
