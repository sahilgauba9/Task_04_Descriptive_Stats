<h1>Overview</h1>
This repository provides three separate Python implementations for performing descriptive statistical analysis on political communication datasets from Facebook Ads, Facebook Posts, and Twitter Posts related to the 2024 U.S. Presidential Election. 
Each script demonstrates a different approach to analyzing identical data:
<h3>Standard Python (no external libraries)

Pandas

Polars</h3>

Across all three methods, the goal is to compute the same set of statistics—mean, count, standard deviation, minimum, maximum, and categorical frequencies. 
The scripts also generate grouped summaries by page_id and, when relevant, by both page_id and ad_id.
```
├── pure_python_stats.py       # Implementation using only Python’s standard library
├── pandas_stats.py            # Implementation using the pandas library
├── polars_stats.py            # Implementation using the polars library
├── README.md                  # Documentation
```

<h1>Running the Scripts</h1>

Place the required CSV files in the same directory as the scripts. Each file will be automatically detected when you run the program.

<h2>Standard Python</h2>

Requires no additional packages.

```
python pure_python_stats.py

```
<h2>Pandas Version</h2>
Install pandas before running:

```
pip install pandas
python pandas_stats.py
```
<h2>Polars Version</h2>
Install polars before running:

```
pip install polars
python polars_stats.py

```
<h1>Data Sources</h1>

The following CSV files were used for analysis:

2024_fb_ads_president_scored_anon.csv

2024_fb_posts_president_scored_anon.csv

2024_tw_posts_president_scored_anon.csv

These datasets include both numeric and categorical variables, such as:

Numeric: estimated_spend, impressions, clicks

Categorical: page_id, ad_id, publisher_platforms

Some columns contain serialized lists or dictionaries stored as strings.


<h2>Project Goals</h2>

Produce consistent statistical summaries across three different processing methods

Manage messy real-world data including missing values and inconsistent types

Compare readability, performance, and development effort between Pure Python, Pandas, and Polars

Reflect on the impact of AI assistants when writing and debugging code


<h2>Methodology</h2>

<h2>Pure Python Approach</h2>
Uses only built-in modules like csv, math, collections, os, and time

Statistical functions (mean, std dev, counts) implemented manually

Uses nested dictionaries for grouping data

Very explicit and customizable, but more verbose and less convenient for large datasets

<h2>Pandas Approach</h2>
Makes use of tools such as .describe(), .value_counts(), and .groupby()

Concise, expressive, and handles missing values gracefully

Easier to write but heavier on memory for large files

<h2>Polars Approach</h2>
Uses describe(), value_counts(), and group_by().agg()

Highly optimized for speed and memory efficiency

A good fit for large datasets, though the API differs slightly from pandas

<h2>Comparison of the Three Methods</h2>

| Feature / Metric      | Pure Python | Pandas    | Polars   |
| --------------------- | ----------- | --------- | -------- |
| Ease of Use           | Medium      | Very Easy | Medium   |
| Performance           | Low         | Moderate  | High     |
| Memory Efficiency     | High        | Low       | High     |
| Code Length           | Long        | Short     | Moderate |
| Visualization Support | None        | Strong    | Limited  |
| Grouped Summaries     | Manual      | Built-in  | Built-in |

<h2>Key Challenges & How They Were Addressed</h2>
| Issue Encountered                          | Solution Implemented                                                  |
| ------------------------------------------ | --------------------------------------------------------------------- |
| Inconsistent data types                    | Implemented type checks and selective casting                         |
| Missing / corrupt rows                     | Applied filtering and safe parsing                                    |
| Columns with nested structures             | Ignored during summarization; flagged for future improvement          |
| Ensuring parity across methods             | Standardized the calculation logic and display outputs                |
| Library version differences (e.g., Polars) | Updated syntax to match current API (`group_by` instead of `groupby`) |

<h2>Notes on Using AI Tools</h2>
AI assistance (e.g., ChatGPT) supported the project by:

Producing initial code templates

Suggesting idiomatic Pandas/Polars operations

Helping identify bugs and fix syntax issues

However, some limitations were observed:

AI tools default to Pandas—even when Polars might be a better choice

They assume well-cleaned datasets

They rarely encourage foundational Pure Python approaches unless asked

Advice for beginners:
Start with Pandas, move to Polars as scale grows, and learn Pure Python for low-level understanding and environments where libraries aren't allowed.


<h2>Future Enhancements</h2>
Parsing and flattening nested list/dict columns using ast.literal_eval

Benchmarking runtime and memory usage across the three methods

Adding CLI arguments to select columns or output formats

<h2>Summary</h2>
This project demonstrates how identical statistical workflows can be implemented using three different Python paradigms. 
Each method offers its own trade offs Pure Python for clarity and control, Pandas for usability, and Polars for performance. 
Together, these scripts highlight how tooling choices influence development speed, scalability, and data handling robustness.
