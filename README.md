# SQL Project — Data Job Analysis

Analyzing the data analytics job market using PostgreSQL. This project explores the highest-paying remote data analyst roles and the skills they demand.

## Data Source

Job posting data from [Luke Barousse's SQL for Data Analytics course](https://www.lukebarousse.com/sql) — a real-world dataset of job listings including salaries, skills, locations, and company information.

## Project Structure

```
├── sql_load/                          # Database setup scripts
│   ├── 1_create_database.sql          # Creates the sql_course database
│   ├── 2_create_tables.sql            # Schema: 4 tables with PKs, FKs, indexes
│   └── 3_modify_tables.sql            # Imports CSV data via COPY commands
├── project_sql/                       # Analysis queries
│   ├── 1_top_paying_jobs.sql          # Top 10 highest-paying remote data analyst roles
│   ├── 2_top_paying_job_skills.sql    # Skills required for those top roles
│   └── 2_top_paying_job_skills.csv    # Query results exported
└── README.md
```

## Database Schema

4 tables with foreign key relationships:

- **`company_dim`** — Company information (id, name, link)
- **`skills_dim`** — Skill definitions (id, skill name, type)
- **`job_postings_fact`** — Job listings (title, salary, location, company, etc.)
- **`skills_job_dim`** — Many-to-many join: which skills belong to which jobs

## Analysis Queries

| Query | Description |
|---|---|
| `1_top_paying_jobs.sql` | Top 10 remote data analyst jobs by average yearly salary |
| `2_top_paying_job_skills.sql` | Skills required for each of those top 10 jobs (uses CTE) |

### Key Skills Used

- **CTEs** (Common Table Expressions) for modular query structure
- **LEFT JOINs** and **INNER JOINs** across 4 tables
- **Aggregation** and sorting
- **NULL handling** for clean results
- **Index creation** on foreign keys for query performance

## How to Run

1. Run `sql_load/1_create_database.sql` to create the database
2. Run `sql_load/2_create_tables.sql` to build the schema
3. Update file paths in `sql_load/3_modify_tables.sql` and run to import CSV data
4. Run `project_sql/` queries to view results

## Requirements

- PostgreSQL
- pgAdmin or any SQL client
- CSV data files (see `sql_load/3_modify_tables.sql` for expected paths)

---

*Project built as part of Luke Barousse's SQL for Data Analytics course.*