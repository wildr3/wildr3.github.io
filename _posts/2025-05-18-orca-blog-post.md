---
layout: post
title: Final Project.... Killer Whale Behavior!
subtitle: Analyzing Simulated Roulette Dataset
cover-img: /assets/img/roulette.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/roulette.jpg
tags: [books, test]
author: Ruby Wildman
---


# Analyzing Orca Whale Rudder Attacks

Way back in 2014, I visited SeaWorld and since then, have been fascinated by Cetaceans, especially Orca Whales or “Killer” Whales. Unfortunately, at this time, my family and I weren’t aware of the corruption and animal cruelty in this industry. Despite Dawn Brancheau and Tilikum’s tragic accident way back in 2010, the orca’s cruelty wasn’t publicized. Films like “Blackfish” shed light on the tragic reality behind these performances. I became fascinated by orcas, not as entertainment, but emotionally intelligent and complex predators. 
During a 2-week scuba trip over summer 2024, my scuba instructors spoke about orcas attacking boats in the Strait of Gibraltar- I had to dig deeper. Since 2020, over 500 orca-boat interactions have been recorded, with at least 4 boats sunk. Scientists and sailors since have been scrambling to understand, why are the orcas doing this? 
There are many theories: territorial defense, curiosity and playfulness, protective moms, environmental stressors, human interference, or unusual prey. Ranging from food shortages to noise pollution to learned trauma, one orca stands out: White Gladis. She experienced a traumatic event that potentially led her to target rudders, and possibly inspire or teach others to follow. I decided to explore these events using scraped data from public whale reports, comparing environmental conditions, and eventually bluefin tuna population data.


# Graphs Created 

<head>
  <script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
  <script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
</head>

<div id="vis"></div>

<script type="text/javascript">
  var spec = "https://raw.githubusercontent.com/vega/vega/master/docs/examples/bar-chart.vg.json";
  vegaEmbed('#vis', /Users/rubywildman/AOD/wildr3.github.io/assets/img/orca_contact_vs_wind_speed.json).then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
</script>
