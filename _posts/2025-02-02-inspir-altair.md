---
layout: post
title: Inspir Altair Experimenting 
subtitle: Creating graphs inspired by NYT visualizations
cover-img: /assets/img/trump_word_freq.jpg
thumbnail-img: /assets/img/trump_word_freq.png
share-img: /assets/img/trump_word_freq.jpg
tags: [books, test]
author: Ruby Wildman
---

# First source: 

![Result](/assets/img/trump_word_freq.png)
https://www.nytimes.com/interactive/2025/01/20/us/politics/presidents-inaugural-address-speech.html 

## 1. What is the data visualization showing?
This data visualization shows the frequency of specific words used in different president’s (specifically Trump) inaugural addresses. 

## 2. What do you find interesting about this data visualization? Why did you choose it?
I found this data visualization interesting because it’s relevant to our society today and uses size and location to represent frequency, which I thought was cool. It also showcases different political eras depending on the president and allows readers to observe how political discourse has changed or evolved depending on the words in each graph. 


## 3. What are the marks and channels?
The marks are the circles, and the channels are the size of the circles or colors to differentiate between different words or presidents. 

## 4. My Data Visualization:
<head>
  <!-- Import Vega & Vega-Lite (does not have to be from CDN) -->
  <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
  <!-- Import vega-embed -->
  <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
</head>

<div id="vis"></div>

<script type="text/javascript">
  var spec = "https://raw.githubusercontent.com/wildr3/wildr3.github.io/refs/heads/master/assets/data/barley.json";
  vegaEmbed('#vis', spec).then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
</script>


~~~
barley = data.barley()

#finding total yield per variety
barley_agg = barley.groupby('variety', as_index=False)['yield'].sum()


chart = alt.Chart(barley_agg).mark_circle().encode(
    x=alt.X('variety:N', axis=None),  # trying to get rid of x & y axis
    y=alt.Y('variety:N', axis=None),  
    size=alt.Size('yield:Q', scale=alt.Scale(range=[100, 2000]), title='Total Yield (Frequency)'),
    color=alt.Color('variety:N', title='Barley Variety'),  # get color for each variety with a key/legend
    tooltip=['variety', 'yield']
).properties(
    title='Barley Yield Frequency as Bubble Chart',
    width=300,
    height=400
)

chart.configure_view(strokeWidth=0)  #changed stroke for aesthetic purposes
~~~

### the process:
I really struggled finding a dataset on vegadatasets that was similar to to structure of this graph (like a speech or song lyrics maybe), but I wanted to represent something using bubbles/circles as both a mark and a channel. I found this dataset that has different varieties of barley alongside their yeild, year, and site. This isn't by any means the best visualization of different types of barley and their yield because I couldn't quite figure out how to make it scattered and fully get rid of any axis (thats why they're diagonal spaced on the page). 

Issues:
Trump's graph occurs from a speech, while the barley dataset tracks crop yields. The barley graph introduces misleading elements: the y-axis, which was meant to be removed, still affects layout (has no relation to count but appears as if there is a relationship), and the x-axis sorts varieties alphabetically rather than by yield. Unlike in the Trump graph, where size directly represented word frequency, in the barley visualization you can barley (haha) tell which frequency is greater. A better approach would use a bubble chart with no axes, to make sure there is yield-driven positioning. 

# My Second (Slightly Better) Source: 

![Result](/assets/img/tornado_graph.png)
https://www.nytimes.com/interactive/2024/12/18/us/tornadoes-2024.html


## 1. What is the data visualization showing?
This data visualization shows the paths of tornados that occurred in 2024 in the United States. It allows you to hover over each path, and you can see the date, intensity, and duration of the tornado's activity. 
## 2. What do you find interesting about this data visualization? Why did you choose it?
I found this dataset interesting because it allows you to visualize the geographical distribution and impact of tornados. 
## 3. What are the marks and channels?
The marks are the tornados and the channels are their position geographically.

## 4. My Data Visualization

<head>
  <!-- Import Vega & Vega-Lite (does not have to be from CDN) -->
  <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
  <!-- Import vega-embed -->
  <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
</head>

<div id="vis1"></div>

<script type="text/javascript">
  var spec = "https://raw.githubusercontent.com/wildr3/wildr3.github.io/refs/heads/master/assets/data/hurricane.json";
  vegaEmbed('#vis1', spec).then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
</script> 



~~~
import altair as alt
from vega_datasets import data

pop = data.population_engineers_hurricanes()
states = alt.topo_feature(data.us_10m.url, 'states')
#variable_list = ['population', 'engineers', 'hurricanes']

alt.Chart(states).mark_geoshape().encode(
    color='hurricanes:Q'
).transform_lookup(
    lookup='id',
    from_=alt.LookupData(pop, 'id', list(pop.columns))
).properties(
    width=500,
    height=300
).project(
    type='albersUsa'
)
~~~

### the process:
For my second data visualization, I tried to recreate the tornado path graph from the NYT using vega datasets, but I ran into a few issues. First was struggling to find a dataset that actually had tornado paths, so I had to end up using a dataset called population_engineers_hurricanes, which tracks hurricanes instead. I figured because this was still weather related and could be mapped geographically, I could still use this dataset to represent frequency of an event on a map, which was my main goal anyways. I used alt.topo_feature to make a U.S. map and colored states based on hurricane frequency, but this didn’t resemble the NYT visualization because there weren’t trajectories in my data which was state-level with no actual paths. Also in the NYT visualization, you can hover over the tornadoes to see things like intensity and data, and my visualization didn’t have this function like the first visualization I created. 
