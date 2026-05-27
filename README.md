# Enrolment KPI Tracker
**Tools:** SQL (SQLite) | Excel Online | DB Browser for SQLite

## Why I Built This
During my time at Smart Move Education Group, I worked with multi-regional 
enrolment data to track KPIs and build reporting dashboards. This project 
recreates that workflow end-to-end using SQL for data management and Excel 
for visualisation — demonstrating how raw data can be turned into actionable 
business insights.

## What This Project Does
- Tracks student enrolments across 4 regions (North, South, East, West)
- Monitors 3 courses: Data Analytics, Business Management, Marketing
- Measures actual enrolments vs monthly targets by region
- Calculates dropout rates by course
- Visualises trends via an interactive Excel dashboard

## Database Structure
Two tables built in SQLite:

**students** — 50 rows
| Column | Type | Description |
|---|---|---|
| student_id | INTEGER | Primary key |
| name | TEXT | Student name |
| region | TEXT | North/South/East/West |
| course | TEXT | Course enrolled in |
| enrolment_date | TEXT | Date of enrolment |
| fee_paid | REAL | Fee amount paid |
| status | TEXT | enrolled/completed/dropped |

**monthly_targets** — 16 rows
| Column | Type | Description |
|---|---|---|
| month | TEXT | Year-month (2024-01) |
| region | TEXT | North/South/East/West |
| target_enrolments | INTEGER | Target headcount |
| target_revenue | REAL | Target revenue |

## SQL Queries Written

### 1. Monthly Enrolments by Region
Grouped actual enrolments and revenue by month and region,
excluding dropped students.

### 2. Dropout Rate by Course
Calculated total students, dropout count and dropout percentage
per course using CASE WHEN logic.

### 3. Actual vs Target Attainment
JOIN between students and monthly_targets to compare actual
enrolments and revenue against targets, with attainment % calculated.

## Excel Dashboard
The dashboard contains:
- **Pivot Table** — enrolments broken down by month and region
- **Line Chart** — enrolment trend over time by region
- **Bar Chart** — dropout rates by course
- **Attainment Table** — actual vs target with conditional formatting
  (green = on target, red = below target)

## Key Findings
- North region consistently hit or exceeded enrolment targets
- Data Analytics had the highest dropout rate at 27.8%
- Q1 2024 total enrolments reached 144 against a combined target of 148
- Revenue attainment averaged 91% across all regions

## Files in This Repository
| File | Description |
|---|---|
| enrolment_tracker.db | SQLite database with all raw data |
| monthly_enrolments.csv | Query result — enrolments by month and region |
| dropout_rates.csv | Query result — dropout analysis by course |
| actuals_vs_targets.csv | Query result — target attainment by region |
| Enrolment_KPI_Dashboard.xlsx | Excel dashboard with charts and pivot tables |
