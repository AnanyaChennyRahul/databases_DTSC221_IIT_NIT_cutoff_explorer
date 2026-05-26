# IIT-NIT Cutoff Explorer

Final project for the **Databases for Data Science** course submitted by Ananya Chenny Rahul and Anannya Umesh.

## Problem Statement
Students preparing for engineering admissions in India often need to compare IIT and NIT options across many dimensions at once: cutoff trends, institute quality indicators, branch availability, location, and category-wise seat competitiveness. In practice, this information is scattered across multiple sources and presented in formats that are difficult to query quickly.

The core problem this project solves is:
- How can an aspirant move from raw admission and institute datasets to an interactive, database-backed decision support tool?
- How can users filter and explore cutoff data by round, category, institute type, institute, and program without manually searching large tables?
- How can contextual information (rankings, NAAC grades, enrollment, events, and location) be surfaced alongside cutoff records to support better choices?

## Our Solution
We designed and built a compact decision-support application: **IIT-NIT Cutoff Explorer**.

The solution combines:
- A relational database model for structured admission and institute data
- Data ingestion from CSV sources into database tables
- A Python desktop UI (Jupyter Notebook + Tkinter) for user interaction
- Query-driven filtering and lookup workflows
- Supplementary views for FAQs, institute details, and map-based navigation

### What the application enables
- Search and filter options by:
- JoSAA round
- Institute type (IIT/NIT)
- Institute name
- Program/branch
- Category/quota
- View institute metadata (establishment year, campus size, enrollment, NAAC, NIRF)
- Access event and contextual institute information
- Use map view to understand geographic distribution of institutes
- Read FAQ-style guidance for common admission queries

## Database Design Overview
The project uses a relational schema centered around three major datasets:

1. `student_data`
- Admission-oriented records, including year, round, institute/program details, category/quota, and ranks.
- Serves as the primary fact table for option discovery and cutoff filtering.

2. `institute_details`
- Institute profile information such as location, year of establishment, campus metrics, enrollment, NAAC grade, and NIRF rank.
- Joined with admission records to provide richer context for decision-making.

3. `events`
- Event metadata linked to institutes for additional campus-level exploration.

Supporting files such as `Table_desc.pdf` document table structure and attributes in detail.

## Data and Files Included
- `data.csv` - main cutoff/admission dataset
- `table_2csv.csv` - institute details dataset
- `Event_details - Sheet1.csv` - events dataset
- `dtsc221_IIT_NIT_EXPLORER.ipynb` - application notebook and UI logic
- `pics/` - institute images used in the interface
- `Table_desc.pdf` - table descriptions/documentation

## Tech Stack
- Python (Jupyter Notebook)
- Tkinter (GUI)
- MySQL / MySQL Connector for Python
- tkintermapview (map visualization)

## Setup and Run
1. Install required Python packages:
```bash
pip install tkintermapview mysql-connector-python
```

2. Create a MySQL database (recommended name used in project: `iit_nitcutoff`).

3. Import CSV files into corresponding database tables.

4. Ensure image assets under `pics/` are present and notebook paths point to this local folder.

5. Open and run:
- `dtsc221_IIT_NIT_EXPLORER.ipynb`

## Project Significance
This project demonstrates how database systems can be used for practical, user-facing analytics workflows in education counseling contexts. Instead of static cutoff tables, the explorer provides structured querying, filtering, and multi-factor comparison in one place.

## Course Context
This repository contains the **final project submission** for the **Databases for Data Science** course (`DTSC221`).

## Privacy Note
This repository has been prepared to avoid publishing personal local machine paths or personal credentials. If any environment-specific path remains in local testing cells, replace it with project-relative paths before further releases.
