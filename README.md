<h1>Overview</h1>
This repository provides three separate Python implementations for performing descriptive statistical analysis on political communication datasets from Facebook Ads, Facebook Posts, and Twitter Posts related to the 2024 U.S. Presidential Election. 
Each script demonstrates a different approach to analyzing identical data:
<h3>Standard Python (no external libraries)

Pandas

Polars</h3>

Across all three methods, the goal is to compute the same set of statistics—mean, count, standard deviation, minimum, maximum, and categorical frequencies. 
The scripts also generate grouped summaries by page_id and, when relevant, by both page_id and ad_id.
'''
├── pure_python_stats.py       # Implementation using only Python’s standard library
├── pandas_stats.py            # Implementation using the pandas library
├── polars_stats.py            # Implementation using the polars library
├── README.md                  # Documentation
'''

