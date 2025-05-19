README - PostgreSQL Database Schema: Planet
===========================================

Purpose:
--------
This PostgreSQL schema, named `planet`, is designed as the foundation of a data architecture that supports automation of the most commonly used reports by the Operations and Continuous Improvement teams.

The schema provides a structured, relational model for managing performance metrics, survey data, contact rates, ticketing activity, and agent productivity—enabling efficient query building and automated data pipelines.

Schema Highlights:
------------------
- **SCHEMA**: `planet`
- **Custom Types**:
  - `mpaa_rating`: ENUM
  - `year`: DOMAIN with validation constraints
- **Sequences**: Auto-increment IDs for all primary entities (e.g., `actor`, `address`, `agent`, etc.)
- **Tables**:
  - Core Entities: `department`, `agent`, `tl`, `date`
  - Performance Data: `productivity`, `call_performance`, `quality_evaluations`, `repeat_rate`
  - Survey Feedback: `VoC`, `contact_rate`, `tickets_sla`, `incoming_tickets`, `outbounds`
- **Views**:
  - Aggregated KPIs by month, week, department, and agent (e.g., `CSAT_Service_monthly_agent`, `VoC_Results_2025`, `NPS_per_month`, etc.)
- **Functions & Triggers**:
  - Automated logic to calculate date fields, set month names, and evaluate inventory stock.
  - Trigger-based updates to ensure date dimensional consistency.

Usage:
------
1. Deploy the schema by executing `L1 SCHEMA.sql` using your PostgreSQL tool (e.g., DBeaver, pgAdmin, or CLI).
2. Use the provided views to build dashboards or feed into BI tools such as Power BI or Excel.
3. Extend the schema as needed to support additional reporting requirements (e.g., financial metrics, SLA trends, etc.)

Author:
-------
This schema is maintained and enhanced by the Continuous Improvement team to support operational insights at scale.

Recommended Next Steps:
------------------------
- Integrate with your BI tools via direct PostgreSQL connection.
- Schedule batch loads for daily/weekly updates.
- Automate CSV exports if required by downstream systems.
