---
layout: page
title: HW5 - UFO Sightings
---

## Visualization 1 — UFO Sightings by Shape and Country

The first visualization shows the top 10 reported UFO shapes ranked by sighting count
in a bar chart, paired with a world bubble map where each country's circle is sized by
its total number of sightings. The bar chart uses a nominal Y axis (shape) and
quantitative X axis (count), colored by shape with the `tableau10` scheme for contrast
across 10 categories. The bubble map uses a Natural Earth projection with size encoding
total sightings per country. A shared `selection_point` on `country_name` is added to
both charts via `.add_params()`, making the interaction bidirectional: clicking a country
bubble filters the bar chart to recompute shape counts only for that country's sightings
via `transform_filter`. No data pre-aggregation was done in pandas for the bar chart —
Vega-Lite recomputes counts from raw rows so the filter works correctly.

<script>
vegaEmbed('#vis1', '/assets/json/chart1.json');
</script>

## Visualization 2 — Duration & Year vs. Hour of Day

The second visualization pairs a scatter plot (top) with a bar chart (bottom). The
scatter plots every individual sighting by year (quantitative X) and log₁₀ sighting
duration (quantitative Y), colored by UFO shape. The log transform was necessary because
raw durations span from 1 second to 86,400 seconds, making a linear scale unreadable.
A `selection_interval` brush on the scatter drives the hour-of-day bar chart below via
`transform_filter(brush)`: Vega-Lite recomputes hourly sighting counts live from raw rows
for only the brushed points. Points outside the brush fade to gray. This lets you explore
questions like: do long-duration sightings cluster at night? Do older-era sightings have
a different hourly pattern than recent ones?

<script>
vegaEmbed('#vis2', '/assets/json/chart2.json');
</script>


<iframe src="/assets/chart1.html" width="100%" height="500"></iframe>

<iframe src="/assets/chart2.html" width="100%" height="600"></iframe>

<div class="left">
<a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv">
  The Data
</a>
</div>
<div class="right">
<a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/ilonaillinois/ilonaillinois.github.io/blob/main/HW5.ipynb">
  The Analysis
</a>
</div>