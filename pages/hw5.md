---
layout: page
title: HW5 - UFO Sightings
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

## Visualization 1 — UFO Sightings by Shape and Country

The first visualization shows the top 10 reported UFO shapes ranked by sighting count 
in a bar chart, paired with a world bubble map. Clicking a country bubble filters 
the bar chart to recompute shape counts only for that country's sightings.

<div id="vis1"></div>

<script>
  vegaEmbed('#vis1', '/assets/json/chart1.json').catch(console.error);
</script>

---

## Visualization 2 — Duration & Year vs. Hour of Day

The second visualization pairs a scatter plot (top) with a bar chart (bottom). 
The scatter plots every individual sighting by year and log10 sighting duration. 
A selection interval brush on the scatter drives the hour-of-day bar chart below.

<div id="vis2"></div>

<script>
  vegaEmbed('#vis2', '/assets/json/chart2.json').catch(console.error);
</script>

---

### Project Links

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