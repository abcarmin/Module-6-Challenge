# Module-6-Challenge

For this project, I am using data visualizations tools, including data aggregation, interactive visualizations, and geospatial analysis to analyze the San Francisco housing market and find investing opportunities.

---

## Technologies

This project uses pandas programming language and utilizes Anaconda, Git Bash, Jupyter Lab, and Github. This project also uses PyViz to create the data visualizations.

---

## Installation Guide

These are the required libraries and dependencies:

import pandas as pd

import hvplot.pandas

from pathlib import Path


You must also install the PyViz packages in your conda dev environment using the code:
    conda install -c pyviz hvplot geoviews

---

## Usage

I brought in the San Fransisco housing data and created a bar chart showing the number of housing units per year:

    housing_units_by_year.hvplot.bar(xlabel='Year', ylabel='Housing Units', y='housing_units', label='Housing Units by Year').opts(yformatter='%.0f')

I then created a line plot showing the sales price per square foot and average gross rent by year:

    prices_square_foot_by_year_df.hvplot(xlabel='Year', 
                                     ylabel='Sales Price per Square Foot/Gross Rent', 
                                     label='Sales Price per Square Foot by Year and Average Gross Rent')

I then created the same graph, but had it grouped by neighborhoods:

    prices_by_year_by_neighborhood_df.hvplot(x='year', 
                                         label='Average Price per Square Foot & Gross Rent by', 
                                         groupby='neighborhood', 
                                         ylabel='Sales Price per Square Foot/Gross Rent')
                                         
Lastly, I brought in the neighborhood data and created an interactive GeoViews enabled map:

    all_neighborhoods_df.hvplot.points(
    "Lon",
    "Lat",
    geo=True, 
    size = "sale_price_sqr_foot",
    color = "gross_rent",
    tiles = 'OSM',
    frame_width = 700,
    frame_height = 500,
    title = "Interactive San Francisco Neighborhood Map",
    hover_cols = ["Neighborhood","sale_price_sqr_foot","gross_rent"]
    )
                                 

---

## Contributors

Allyssa Carmin

---

## License

SMU Fintech Course