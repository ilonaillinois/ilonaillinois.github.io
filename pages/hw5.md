---
layout: page
title: HW5 - UFO Sightings
---

## Visualization 1 — UFO Sightings by Shape and Country

#### Introduction:
<br>
The first visualization visualizes the global distribution of UFO sightings, broken down by the shape of the reported UFO and the country of the sighting.
Users can select the year, month and hour they want to observe.
The two bars charts below show the count of sightings by the shape and country, and each reponds dynamically to the filters applied by the others. Users can also click on the shape bar or country bar to explore more information.

#### Encoding choices:
<br>
The top filter bars all use a bar mark with positional encodings - year bin, mpnth and hour mapped to the x-axis and count on the y-axis. Below are the shape and country bar charts, which use a horizontal layout with count on the x-axis and categorical variable on y. I used descended sorting by count so that the most common categories will show on the top. The color used is used as a highlight encoding rather than an information encoding (selected bars are shown in a distinct color, unselected bars will fade to gray, making the selection more obvious).

#### Color scheme:
<br>
For the shape bar chart, I used Altair's `tableau20` scheme, which is a popular color theme and provides 20 distinct colors to differentiate the many UFO shapes. For the country bar chart, I used the `set2` scheme because I want to differentiate it from the shape chart. 

#### Data transformations: 
<br>
The raw dataset did not include column headers, so I manually assigned them. The `datetime` column was parsed from a string into a proper datetime type, from which I pulled out the `year`, `month` and `hour` as separate columns to provide more detailed insights. Rows missing `datetime`, `shape`, `country` or `duration_seconds` were dropped. In addition, for the year filter, I used a `year_bin` column by flooring each year to the nearest 5 to prevent the x-axis from being too crowded.

### Questions you can explore with Visualization 1

**1. In June 2010, what is the most observed UFO shape, and how many sightings occurred in Canada?**

**2. In June 2010, how are Fireball sightings distributed across countries?**

**3. In June 2010, what are the top 3 shapes reported in Canada?**


<iframe 
    src="/assets/chart1.html" 
    width="120%" 
    height="700" 
    frameborder="0">
</iframe>

---

## Visualization 2 — Duration & Year vs. Hour of Day

The second visualization focuses on US sightings and lets users explore the relationship between shape, duration and geographic location. At first, I wanted to involve all countries, but the graph will be a little complicated (because I also want to include the state information), so I decided to focus on a single country. Users can select the shape they want to explore from the dropdown (I also tried to put the dropdown on the very top but things did not work). The map shows where sightings occured across the country, a bar chart beside it shows the top 5 states by sighting count, and the scatter plot below shows sighting duration (log scale) versus year. Users can brush a region on the scatter plot, and both the map and the state bar chart will reflect only the sightings in that time and duration range.

#### Encoding choices:
<br>
The map uses longitude and latitude as positional encodings with a circle mark, placing each sighting at its geographical location. The scatter plot below uses year on x and duration (transformed to log) on y with a circle mark, giving a view of how sighting duration are distributed. The states bar chart uses count on x-axis and state on y (sorted by count), making it easy to rank states. Opacity is used in both the map and scatter plot as a secondary encoding to indicate brush selection status (the unselected ones will fade).

#### Color scheme:
<br>
All three views share the same `dark2` qualitative color scale (each shape has its own color). This ensures the same shape always appears as the same color for each graph, which I think is more consistent. I chose `dark2` because it has distinct hues so that users can clearly know they have successfully chosen a different shape after manipulating the dropdown function.

#### Data transformations:
<br>
As mentioned before this chart was filtered to US to reduce complexity. I also applied a log transformation on duration since it spanned several orders of magnitude (from seconds to tens of thousands of seconds), by doing so, the range is compressed and the scatter plot became more readble. Null values in `state` and `shape` were filled with 'unknown' so they remain groupable. The state bar chart is computed with Vega-Lite transforms so it can repond to the brush selection.

### Questions you can explore with Visualization 2

**1. For the Light shape, when and where was the earliest sighting?**


**2. Where does the three longest-duration sightings occur (light shape)?**


<iframe 
    src="/assets/chart2.html" 
    width="100%" 
    height="900" 
    frameborder="0">
</iframe>

---


### Interactivity
<br>
Both of the charts are interactive. In Visualization 1, clicking any bar in the year, month or hour selectors filters the shape and country bar charts below. So for example, if a user wanted to know the top 3 shapes in June 2010, just click on the year bar chart and the month bar chart, and the shape bar chart will respond immediately. To go further, the user can then click on the shape to observe the occurences in each country. They can also click on the country to look at the top shapes.
<br>
In Visualization2, the dropdown controls which UFO shape is shown across all three views (the default shape is light since it has the most sightings). The scatter plot brush dynamically filters the map and the states bar chart to show only sightings in the selected year and duration range. 

### Project Resources

<div style="display: flex; justify-content: space-between;">
    <a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/ufo-scrubbed-geocoded-time-standardized-00.csv">
      View Raw Data
    </a>
    <a class="m-1 btn btn-outline-primary btn-2" href="https://github.com/ilonaillinois/ilonaillinois.github.io/blob/main/HW5.ipynb">
      View Analysis (Notebook)
    </a>
</div>

