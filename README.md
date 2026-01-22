# Analyzing & Validating Scientific Data Migration at NSLS-II

## Overview
This repository documents a large-scale data validation project completed during a
Data Science Internship at Brookhaven National Laboratory’s National Synchrotron Light
Source II (NSLS-II).

The project evaluated the integrity of a **10+ petabyte scientific data migration**
from a MongoDB (NoSQL) backend to PostgreSQL (SQL) within the Tiled data management
system, which supports data access and analysis across NSLS-II beamlines.

Due to data sensitivity and infrastructure restrictions, source code and raw data
are not publicly available. This repository serves as a **technical case study**
describing the methodology, validation approach, and findings.

---

## Project Goal
Ensure that scientific data, metadata, and query outputs remained consistent before
and after migration—supporting reliable, high-throughput access for researchers and
enabling a future facility-wide SQL rollout.

---

## My Role
As a Data Science Intern, my responsibilities included:

- Validating correctness of NoSQL → SQL data migration
- Comparing query outputs between legacy and new database systems
- Monitoring migration stability using logs and summary statistics
- Visualizing trends to communicate migration health to stakeholders
- Translating technical findings into actionable summaries

---

## Validation Approach

### 1. Data Volume Verification
- Queried daily Bluesky run counts (2021–2025) across both systems
- Compared daily and monthly trends to confirm no data loss
- Identified expected gaps due to maintenance periods

### 2. Metadata Consistency Checks
- Analyzed run-type distributions on the HXN beamline
- Verified that scan-type labels (e.g., FlyPlan 1D, FlyPlan 2D) were preserved
- Confirmed identical distributions before and after migration

### 3. Migration Log Analysis
- Parsed migration logs and categorized outcomes
- Quantified successful runs, warnings, and errors
- Identified patterns indicating potential system issues

---

## Key Findings
- Run-type distributions matched within **<0.5%** across systems
- **64.5%** of runs migrated with no issues
- **~35%** completed with warnings but preserved data integrity
- Only **0.1%** of runs failed
- FlyPlan 1D and 2D scans accounted for **76%** of HXN activity

---

## Impact
This validation confirmed that the SQL-backed system preserves scientific data integrity
at scale, supporting faster access, improved reliability, and simplified administration.

The findings contributed to confidence in expanding the migration beyond the pilot
HXN beamline.

---

## Tools & Technologies
- Python
- PostgreSQL
- MongoDB
- Matplotlib
- Data validation & logging
- Scientific data infrastructure (Bluesky, Tiled)

---

## Notes on Availability
- Source code and raw data are not included due to institutional restrictions
- Figures and results shown are derived summaries approved for sharing
- Methodology reflects production-scale validation practices

---

## Acknowledgements
This project was completed during a Data Science Internship at Brookhaven National
Laboratory.

Special thanks to my mentor, Yevgen (Eugene) Matviychuk, and the NSLS-II Data Science team.
