# 🚍 Transport Management System – Oracle SQL Project

This project is a full-scale **relational database design and implementation** for a fictional **Transport Management System**, built using **Oracle SQL**. It demonstrates proficiency in SQL-based data modeling, table creation, data integrity constraints, and initial data population for a complex transport scenario involving employees, agents, cities, vehicles, schedules, routes, meals, stops, tickets, and sales data.

---

## 📁 Table of Contents

- [🔍 Project Overview](#-project-overview)
- [🧰 Tech Stack](#-tech-stack)
- [🗃️ Database Schema](#️-database-schema)
- [📦 Data Population](#-data-population)
- [📌 Features](#-features)
- [📈 Sample Queries](#-sample-queries)
- [⚙️ How to Run](#️-how-to-run)
- [🧑‍💻 Author](#-author)

---

## 🔍 Project Overview

The Transport Management System provides a backend solution for managing transportation operations including scheduling buses, assigning drivers, managing ticket sales, tracking city routes, managing agent activities, and tracking meals served during transit. This is a sample enterprise-grade database solution for logistics and transport companies.

---

## 🧰 Tech Stack

- **Database:** Oracle SQL
- **Tools Used:** Oracle SQL Developer / SQL\*Plus / DBeaver
- **Language:** SQL (DDL, DML)
- **Format:** `.sql` script file (drop, create, insert operations)

---

## 🗃️ Database Schema

The database contains **10 interrelated tables** with properly defined keys and constraints:

| Table Name   | Description                              |
|--------------|------------------------------------------|
| `EMP`        | Employee details including role & manager |
| `CITY`       | List of cities covered by the network     |
| `ROUTE`      | Routes between cities                     |
| `STOP`       | Intermediate stops along each route       |
| `AGENT`      | Ticket-selling agents and their info      |
| `MEAL`       | Meals served at stops en route            |
| `SALES_LIST` | Sales records tied to agents              |
| `VEHICLE`    | Vehicle specs and registration info       |
| `SCHEDULE`   | Trip schedules including date and pricing |
| `TICKET`     | Ticket issuance linked to schedules       |

Each table includes:
- **Primary Keys**
- **Foreign Keys**
- **Unique and Not Null constraints**
- **Check constraints** for data validation

---

## 📦 Data Population

Over **100+ sample records** have been inserted into the schema using `INSERT` statements, simulating a real-world operational dataset. The data includes:
- 10+ employees (managers, drivers, etc.)
- 10+ cities and 10+ routes
- 20+ stops
- 10+ vehicles and their schedule data
- 10 agents and 10+ sales records
- Various ticket purchases linked to sales and schedules

---

## 📌 Features

- 🔁 **Data Integrity** through primary/foreign key relationships  
- ✅ **Validation** through constraints like `CHECK`, `UNIQUE`, `NOT NULL`  
- 🔄 **Referential Integrity** through cascading constraints  
- 🔍 **Query-ready structure** for further analysis, reporting or BI integration  
- ⚙️ Ready to be scaled for a front-end application or dashboard

---

## 📈 Sample Queries

Here are a few example queries you might run after setup:

```sql
-- 1. Total tickets sold by each agent
SELECT AGENT_ID, SUM(QTY_OF_TICKET_SOLD) AS TOTAL_SOLD
FROM SALES_LIST
GROUP BY AGENT_ID;

-- 2. Get all schedules for a specific route
SELECT *
FROM SCHEDULE
WHERE ROUTE_ID = 'NEWD';

-- 3. List all drivers and their assigned schedules
SELECT E.FIRST_NAME, E.LAST_NAME, S.SCHEDULE_ID, S.DEP_DATE
FROM EMP E
JOIN SCHEDULE S ON E.EMP_ID = S.VEHICLE_ID
WHERE E.DESIGNATION = 'DRIVER';
```

## ⚙️ How to Run

1. **Set up Oracle DB Environment:**  
   - Use any Oracle-compatible SQL tool like **Oracle SQL Developer**, **DBeaver**, or **SQL*Plus**.  
   - Ensure your user account has privileges to **CREATE**, **DROP**, and **INSERT** into tables.

2. **Download or Clone the Project:**  
   - Clone this repository or download the `.sql` script file containing the full DDL (table definitions) and DML (data inserts).

3. **Execute the Script:**  
   - Open your SQL environment.
   - Load and run the script:
     - It will **drop existing tables** (if they exist),
     - **Create** new ones with constraints,
     - And **populate** them with initial data.

4. **Test the Database:**  
   - After successful execution, try sample SQL queries.
   - Validate relationships, run aggregations, joins, and subqueries to explore the dataset.

5. **Next Steps (Optional):**  
   - Connect to visualization tools like **Power BI**, **Excel**, or **Tableau** to build dashboards.  
   - Integrate with a backend API or frontend interface for dynamic interaction.





