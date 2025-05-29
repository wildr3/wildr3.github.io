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


[insert personal photo here]

  Way back in 2014, I visited SeaWorld and, since then, have been fascinated by orca whales, or “killer” whales. Unfortunately, at this time, my family and I weren’t aware of the corruption and animal cruelty in this industry. Despite Dawn Brancheau and Tilikum’s tragic accident way back in 2010, the orca’s cruelty wasn’t publicized. Films like “Blackfish” shed light on the tragic reality behind these performances. After watching this documentary in 2019, I have been fascinated by orcas, not as entertainment, but as emotionally intelligent and complex predators.

[dawn and tilikum/blackfish here]
  
  Part of this interest led to going on a 2-week scuba trip in Anguilla and St. Maarten (we unfortunately didn’t see any orcas). During the trip this summer, my scuba instructors talked about orcas in the Strait of Gibraltar. They were attacking the rudders of boats and have been for quite some time, but why? No one knew for sure. I was hooked. 

[scuba photos here]

  Since 2020, over 500 orca-boat interactions have been recorded, with at least 4 boats sunk. There are many theories: territorial defense, curiosity and playfulness, protective moms, environmental stressors, human interference, or unusual prey. Ranging from food shortages to noise pollution to learned trauma, one orca stands out: White Gladis.

[white gladis and calf photo here]

  One potential reason for these orca attacks was that White Gladis experienced a traumatic event that led her to target rudders, and possibly inspire or teach others to follow. Experts speculate that she may have been pregnant at the time she was hit by a vessel or entangled in a fishing net. Sometime in 2021, despite already giving birth to her calf, she still approached and rammed vessels along the coast. This decision to jeopardize her calf’s safety suggests a severely traumatic event potentially related to a boat or human interference. Orcas rely heavily on their mother in the first two years for a variety of things until they learn how to hunt. Killer whale pods have incredibly distinctive dialects that mothers teach their calves at a young age, culture included. Robert Pitman, a marine ecologist at Oregon State University’s Marine Mammal Institute, told LiveScience in an email “anything the adults learn will be passed along” from the dominant female in a pod to her offspring. Currently, Gladis is one of 11 identified juveniles who ruthlessly and efficiently target the rudders of boats off the Iberian cost.  The behavior appears to be spreading through the Iberian population through social learning, reproducing behaviors they find advantageous or interesting.

  I decided to explore these events using scraped data from the CA cruising association and the GTOA’s website. Was White Gladis actually the catalyst to these events or could it be something else? By uncovering certain patterns in orca behavior and the conditions around the attacks, it could not only further uncover the reason behind these attacks, but also could lead to better strategies for boaters to avoid or minimize dangerous encounters. By limiting these interactions we can help protect the lives of both humans and whales. I turned to altair data visualizations to try and untangle the complexity of Iberian orca behavior by highlighting patterns between attacks seen in the scraped data.


# Graphs Created

<!-- Vega libraries -->
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<div id="vis"></div>

<script type="text/javascript">
  vegaEmbed('#vis', '/assets/img/orca_contact_vs_wind_speed.json').then(function(result) {
    // Access the Vega view instance as result.view
  }).catch(console.error);
</script>

[insert 6 graphs here]


