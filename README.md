# HotelAndStars

Business intelligence dimensional modeling using SQL Server Management Studio (SSMS).

## 📋 Table of Contents

- [Project Description](#-project-description)
- [Technologies Used](#-technologies-used)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Project Structure](#-project-structure)
- [Project Objectives](#-project-objectives)
- [Key Concepts](#-key-concepts)
- [Learning Outcomes](#-learning-outcomes)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

## 📝 Project Description

This project demonstrates the complete development of database modeling through the creation of an Entity-Relationship Model (ERM) and its transformation into a Dimensional Model using SQL Server Management Studio.

Key Focus Areas:

- Entity-Relationship Modeling (OLTP - Transactional Database Design)
- Dimensional Modeling (OLAP - Analytical Database Design)
- Star Schema implementation for Business Intelligence
- Slowly Changing Dimensions (SCD) implementation
- Time hierarchies for multidimensional analysis
- Database modeling and visualization

## 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| SQL Server | Enterprise relational database platform |
| SQL Server Management Studio (SSMS) | Database design and development tool |
| Entity Relationship Diagram (ERD) | Visual modeling of entities and relationships |
| T-SQL | Database scripting and query language |
| Git | Version control |
| GitHub | Repository hosting and collaboration |

## 📦 Prerequisites

Before getting started, ensure you have the following installed on your system:

- **SQL Server** (Express Edition or higher)
  - Download: https://www.microsoft.com/en-us/sql-server/sql-server-downloads

- **SQL Server Management Studio (SSMS)** (latest version)
  - Download: https://learn.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms

- **Git** (for cloning the repository)
  - Download: https://git-scm.com/

### System Requirements

- OS: Windows, macOS, or Linux
- RAM: Minimum 4GB (8GB recommended)
- Disk Space: At least 500MB free space

## 💻 Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/mlbvncs/HotelAndStars.git
cd HotelAndStars
```

### Step 2: Review the Analysis Documentation

Open `Analysis.pdf` to understand:
- Project objectives and scope
- Entity-Relationship Model design
- Dimensional Model specifications
- Design decisions and rationale

### Step 3: Examine the Models

Navigate to the project folders:
- `1. Models/1. Relational/` - Entity-Relationship Model (ERM/OLTP)
- `1. Models/2. Dimensional/` - Dimensional Model (OLAP/Star Schema)

### Step 4: Access the Models in SSMS

1. Open SQL Server Management Studio
2. Connect to your SQL Server instance
3. Review the ERD diagrams and model visualizations
4. Examine the generated SQL scripts and schema definitions

## 📂 Project Structure

```
HotelAndStars/
│
├── 1. Models/
│   ├── 1. Relational/
│   │   ├── Entity-Relationship diagrams
│   │   ├── OLTP schema definitions
│   │   └── Transactional database structure
│   │
│   └── 2. Dimensional/
│       ├── Dimensional model diagrams
│       ├── OLAP schema definitions
│       ├── Star Schema structure
│       ├── Fact and Dimension tables
│       └── Hierarchies and relationships
│
├── 2. Translations/
│   ├── Brazilian Portuguese translations
│   └── Dimensional model analysis (pt-br)
│
├── Analysis.pdf
│   └── Comprehensive project documentation and specifications
│
├── LICENSE
│   └── MIT License
│
├── .gitignore
│   └── Git ignore configuration
│
└── README.md
    └── This file
```

### Key Folders Explained

#### 1. Models/

Contains the core database models in both OLTP and OLAP structures:

- **1. Relational/** - The transactional database design (ERM) showing entities, relationships, and constraints
- **2. Dimensional/** - The analytical database design (Star Schema) showing facts, dimensions, and hierarchies

#### 2. Translations/

Brazilian Portuguese translations and localized analysis of the dimensional model, providing multilingual support and regional insights.

## 🎯 Project Objectives

✅ Build a complete Entity-Relationship Model (ERM) for the HotelAndStars business domain

✅ Design and implement a Dimensional Model based on the ERM

✅ Demonstrate transformation from OLTP (transactional) to OLAP (analytical) structures

✅ Apply Star Schema design principles for Business Intelligence

✅ Enable multidimensional analysis of hotel operations and customer stays

✅ Implement Slowly Changing Dimensions (SCD) with temporal validity tracking

✅ Create time hierarchies for drill-down and drill-up analysis capabilities

## 🏗️ Key Concepts

### Entity-Relationship Model (ERM)

The OLTP model represents the transactional system with:
- Core business entities (Customer, Accommodation, Stay, etc.)
- Relationships between entities
- Normalized structure for operational efficiency
- Primary and foreign key constraints

### Dimensional Model (Star Schema)

The OLAP model transforms the ERM into an analytical structure with:

**Dimensions:**
- **dim_customer** ('who?') - Customer attributes with temporal versioning
- **dim_accommodation** ('where?') - Accommodation attributes with temporal versioning
- **dim_time** ('when?') - Time hierarchies (day, month, quarter, year, weekday)

**Fact Table:**
- **fact_stay** - Consolidated transaction table with stay metrics at customer-stay granularity

### Slowly Changing Dimensions (SCD)

Type 2 implementation preserves historical dimension changes with:
- `validity_start_date` - When the record became valid
- `validity_end_date` - When the record expired
- Enables temporal analysis and trend identification

### Dimension Hierarchies

Time dimension with multiple levels supporting:
- Drill-down analysis (year → quarter → month → day)
- Roll-up aggregation
- Comparative analysis across time periods

## 📚 Learning Outcomes

This project strengthens skills in:

- Database Design: Designing efficient relational database schemas
- Data Modeling: OLTP vs OLAP architectural differences
- Dimensional Modeling: Star Schema and Kimball methodology
- Business Intelligence: End-to-end BI solution architecture
- SSMS Proficiency: Database modeling and visualization tools
- Temporal Data Management: Slowly changing dimensions and versioning
- Data Visualization: Understanding logical data structures for analytics

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome!

To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

This project is available for educational and portfolio purposes.

## 👤 Author

Malba Vinicius Lopes Santos

- GitHub: [@mlbvncs](https://github.com/mlbvncs)
- Portfolio: Business Intelligence & Database Design

Last Updated: June 2, 2026
Status: Active Development
