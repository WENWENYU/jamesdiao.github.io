---
layout: post
title: "Estimated Distributions"
author: James Diao
date: 2018-01-27
location: New Haven, CT
---

Often, my parents or friends will ask me to estimate my beliefs about a probability or a time. For example, they might ask how likely I am to go to an event, or maybe how longer it will take me to get there. It's easy to give a point estimate, but this says nothing about my own uncertainty in this guess. As a result, I made a quick app to build simple distributions that can help with this. It does this by adding range information (minimum and maximum probability or time) and fitting these quantiles to an appropriate family of distributions (I explain my choices below the app). I don't actually use this practically of course, but it was a silly idea and fun to implement.  

The app is hosted at [https://jamesdiao.shinyapps.io/estimateddistributions/](https://jamesdiao.shinyapps.io/estimateddistributions/) and embedded below (may take 5-10 seconds to load). Simply use the sliders to select an estimated value and range. Click on "Beta" for probability estimates, and "Gamma" for time estimates. 


<iframe src="https://jamesdiao.shinyapps.io/estimateddistributions/" style="border: none; width: 820px; height: 830px"></iframe>

Note: I chose to represent probabilities using a Beta distribution because, as the conjugate prior to the binomial, it has an intuitive explanation in terms of observed successes and failures. Similarly, I chose to represent times using a Gamma distribution because, as the conjugate prior to the exponential, it gives an intuitive model of wait time as the sum of independent exponentially-distributed events. These families work reasonably well because they are smooth, unimodal, and within the correct domains (0-1 for probabilities, 0-&infin; for time).  

I found that the Gamma distribution is not as flexible as I hoped, and fails to capture certain shapes (e.g., heavier left tail). I suspect that the PERT distribution (a domain-transformed Beta) would work better; it is commonly used in modeling completion times for commercial projects. I'm hoping to implement it when I have time.  

