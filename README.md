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

## 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| SQL Server | Enterprise relational database platform |
| SQL Server Management Studio (SSMS) | Database design and development tool |
| Entity Relationship Diagram (ERD) | Visual modeling of entities and relationships |
| Git | Version control |
| GitHub | Repository hosting and collaboration |

## 📦 Prerequisites

Before getting started, ensure you have the following installed on your system:

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

### Step 3: Examine the Models

Navigate to the project folders:
- `1. Models/1. Relational/` - Entity-Relationship Model (ERM/OLTP)
- `1. Models/2. Dimensional/` - Dimensional Model (OLAP/Star Schema)

## 📂 Project Structure

```
HotelAndStars/
│
├── 1. Models/
│   ├── 1. Relational/
│   │   ├── Entity-Relationship diagram
│   │
│   └── 2. Dimensional/
│       ├── Dimensional model diagram
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

- **1. Relational/** - The transactional database design (ERM) showing entities, and relationships
- **2. Dimensional/** - The analytical database design (Star Schema) showing facts, and dimensions

#### 2. Translations/

Brazilian Portuguese translations and localized analysis of the dimensional model, providing multilingual support and regional insights.

## 🎯 Project Objectives

✅ Build a complete Entity-Relationship Model (ERM) for the HotelAndStars business domain

✅ Design and implement a Dimensional Model based on the ERM

✅ Demonstrate transformation from OLTP (transactional) to OLAP (analytical) structures

✅ Apply Star Schema design principles for Business Intelligence

✅ Enable multidimensional analysis of hotel operations and customer stays

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
- **dim_customer_location** - Customers locations
- **dim_accommodation_type** - Accommodation type attributes
- **dim_time** - Time hierarchies (day, month, quarter, year, weekday)

**Fact Table:**
- **fact_stay** - Consolidated transaction table with metrics on length of stay at a granular level of daily occupancy information.

## 📚 Learning Outcomes

This project strengthens skills in:

- Database Design: Designing efficient relational database schemas
- Data Modeling: OLTP vs OLAP architectural differences
- Dimensional Modeling: Star Schema and Kimball methodology
- SSMS Proficiency: Modeling and visualization tools

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
- Portfolio: Business Intelligence

Last Updated: June 2, 2026
Status: Active Development
