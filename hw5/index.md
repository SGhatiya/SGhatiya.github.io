---
title: Homework 5 – Bigfoot Visualizations
---

# Homework 5: Bigfoot Sightings Visualized

## Visualization 1: Geographic Spread of Bigfoot Sightings

*Description:*  
When I first opened the dataset, I had a question I genuinely wanted to answer: “Is Bigfoot just a Pacific Northwest legend, or is the phenomenon more widespread?”

This plot helped me get closer to that answer.

Using the provided latitude and longitude values, I mapped every sighting in the dataset across the U.S., layered over a muted geoshape map of U.S. states using an Albers USA projection (best fit for continental U.S.). To avoid overwhelming the viewer with overlapping points, I reduced the point size and opacity slightly.

What makes this plot interactive is the dropdown menu that lets the user filter sightings by their classification type (Class A, B, or C). This allows for focused exploration. For example, Class A reports (often considered the most credible) tend to cluster heavily in the Pacific Northwest. Class B and C are more dispersed. This filtering helped me notice how some states like Ohio and Florida surprisingly show up with dense clusters, breaking the myth that Bigfoot is only a "forest legend."

Color was mapped directly to the classification column to help users intuitively distinguish the reports.

This is the kind of plot that invites exploration: it starts with a story I’m curious about and gives users the tools to investigate it themselves, exactly the kind of visualization that aligns with the “viz for self” and “viz for peers” mindset we discussed in class.

<iframe src="/hw5/chart1.html" width="100%" height="500px" frameborder="0"></iframe>

---

## Visualization 2: Seasonal Sightings by Year

*Description:*  
This chart visualizes the number of Bigfoot sightings reported in each season, using a bar plot grouped by season. To reduce clutter and add focus, I included an interactive dropdown filter that allows the viewer to select a specific year. This helps identify seasonal peaks or shifts over time. The x-axis encodes the Season as an ordinal type, and the y-axis encodes the count of sightings (quantitative). For color, I used a categorical color palette based on season to provide clear visual distinction and highlight seasonal variation at a glance.

To prepare the data, I extracted the year from the date column using pandas’ to_datetime, then filtered out any rows missing a season. I grouped the cleaned data by year and season, counted the number of reports, and passed that summary into Altair. The interactivity is implemented using alt.selection_point() with a dropdown binding on the Year field, which allows the user to dynamically explore changes across decades. This is more meaningful than .interactive() alone because it lets the viewer isolate years and compare seasonality across time.

<iframe src="/hw5/chart2.html" width="100%" height="500px" frameborder="0"></iframe>

