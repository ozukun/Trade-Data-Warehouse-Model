# Trading-metrics-datamodel

Trade Data Warehouse Model

This repository contains the complete Trade Data Warehouse (DWH) dimensional model used for analytics, reporting, and historical trade snapshots.
It includes:

A full Entity–Relationship Diagram (ERD)

A complete DBML schema describing all tables, keys, and relationships

A fact table capturing trade snapshots over time

Multiple dimension tables covering product hierarchies, traders, accounts, companies, metadata, and more

📊 Overview

The model follows a Kimball-style dimensional design, centered around the FACT_TRADE_SNAPSHOT table, which stores daily snapshots of trade activity with full SCD2-compliant dimensions.

This structure supports:

Historical trade analysis

PnL and revenue reporting

Position and volume analytics

Product and category roll-ups

Organizational analytics (traders, accounts, companies)

Cross-dimensional filtering (currency, UOM, direction, trade type, status, etc.)

📐 Entity–Relationship Diagram (ERD)

The full ERD is included in the repository:

ERD File: /mnt/data/ACT_Model.png
(Drag the file into the GitHub repo when uploading.)

🗂 Schema File

All tables and relationships are defined in:

Schema: /mnt/data/All_Scripts_Relations.txt

This file uses DBML format, compatible with tools such as dbdiagram.io and DBML-to-SQL generators.

🏗 Core Components
1. Fact Table

FACT_TRADE_SNAPSHOT
Captures trade metrics per snapshot date, including volume, prices, revenues, COGS, PnL, and record metadata.

2. Key Dimensions

DIM_DATE – Calendar attributes

DIM_PRODUCT – Linked to product group & category hierarchies

DIM_ACCOUNT – Accounts with SCD2 history

DIM_TRADER – Traders with positions & departments

DIM_COMPANY – Company SCD2 records

DIM_CURRENCY / DIM_UOM – Market metadata

DIM_DIRECTION / DIM_TRADETYPE / DIM_TRADESTATUS – Trading attributes

DIM_RECORDSOURCE – Source system tracking

DIM_MATCHIND – Matching indicator

3. Hierarchies

Product Group Hierarchy (Group → Subgroup)

Product Category Hierarchy (Category → Subcategory)

Each hierarchy supports recursive parent–child navigation.
