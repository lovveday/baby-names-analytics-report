Baby Names Analytics Dashboard (SSA website inspired) 
By _Osekhuemen Peter-Imoisili_


**Project Story**

I came across the baby names dataset on data.gov, which contained a ZIP file of yearly text files and a link to the SSA website.

After exploring the site, one thing stood out immediately: it wasn’t just data, it was interactive.

That’s what inspired this project.

Instead of building a static dashboard, I set out to recreate that experience in Power BI — something users can explore, not just look at.


**My Objective**
To build a fully interactive analytics dashboard that allows users to:

Search any name
Explore trends across years and decades
Compare male vs female name popularity
Identify rising and declining names

Basically, turn raw data into something people can play with.


Data Pipeline (End-to-End)

🔹 Data Source:
The dataset was downloaded from data.gov
Provided as a ZIP file containing _.txt_ files for each year

🔹 Data Processing (Python)
The data was extracted and combined from multiple yearly files, 
and the raw .txt data was converted into a structured CSV. 
The dataset was cleaned and standardized

🔹 Data Storage (SQL)
The cleaned data was loaded into an SQL database
The data was queried to validate the structure and relationships
Ran checks to ensure accuracy before visualization

(Yes, I didn’t just trust Power BI blindly 😄)

🔹 Data Visualization (Power BI)
I built an interactive dashboard inspired by the SSA website
Verified Power BI results against SQL queries for consistency


**Key Features**
Name Explorer Page:
There you can Search any name
View popularity trend over time
Track ranking changes dynamically

Dynamic Ranking System:
Real-time ranking based on filters
_Works across:_
Year
Gender
Decade
Handles ranking edge cases (ties, duplicates)

Change in Popularity:
Tracks how names rise or fall over time
Based on rank movement (SSA-style)

Gender Comparison Table (Top 10 names page)
Displays top male and female names side-by-side
Custom-built ranking system aligned by rank

Decade Analysis:
Aggregated insights across decades
Helps identify long-term naming trends


Interactive Filters

Users can filter by:

Year (Dropdown slider)
Gender
Name (search-enabled slicer)
Decade


**What I Learned**
How to handle filter context in DAX (this one humbled me 😅)
Building ranking systems that actually work
Importance of validating dashboards with SQL
Designing reports for user interaction, not just visuals


**Challenges & Solutions**
🔸 Ranking always returned 1

Fixed by adjusting filter context using ALL() instead of ALLSELECTED()

🔸 Duplicate names in ranking

Solved by implementing tie-breaking logic

🔸 Aligning male & female rankings

Used a helper rank table to map both sides correctly

🔸 Making Power BI feel like a web app

Used slicers, dynamic titles, and measures to simulate interactivity

🚀 Why This Project Matters

This project demonstrates my ability to:

Build an end-to-end data pipeline (Python → SQL → Power BI)
Work with real-world messy data
Design interactive dashboards
Translate data into meaningful insights
