---
layout: page
title: HW5 - UFO Sightings
---

## Visualization 1 — UFO Sightings by Shape and Country

The first visualization shows the top 10 reported UFO shapes ranked by sighting count 
in a bar chart, paired with a world bubble map where each country's circle is sized by 
its total number of sightings. Clicking a country bubble filters the bar chart.

<iframe 
    src="/assets/chart1.html" 
    width="120%" 
    height="700" 
    frameborder="0">
</iframe>

---

## Visualization 2 — Duration & Year vs. Hour of Day

The second visualization pairs a scatter plot (top) with a bar chart (bottom). 
The scatter plots every individual sighting by year and log10 sighting duration. 
A selection interval brush on the scatter drives the hour-of-day bar chart below.

<iframe 
    src="/assets/chart2.html" 
    width="100%" 
    height="800" 
    frameborder="0">
</iframe>

---

### Project Resources

<div style="display: flex; justify-content: space-between;">
    <a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv">
      View Raw Data
    </a>
    <a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/ilonaillinois/ilonaillinois.github.io/blob/main/HW5.ipynb">
      View Analysis (Notebook)
    </a>
</div>