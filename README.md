# Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time
Repository for my project assessing trends and changes in frequency of plane crashes between 1918 and 2022.

This is the repo for my ITEC 4220 Advanced Analytics project in which I assess trends in air crashes and their associated fatalities over time. To start, I 
downloaded the historical plane crash data set as PlaneCrashes.csv from Kaggle at the url https://www.kaggle.com/datasets/abeperez/historical-plane-crash-data. 
With this project, I hope to evaluate the relative safety of air travel across different eras of aviation.

[Here is some preliminary analysis in R](https://rpubs.com/petedavis2002/1340287)

[html](https://github.com/PeteDavis2002/Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time/blob/main/PlaneCrashesMarkdown.html)

[PlaneCrashes dataset as JSON](https://raw.githubusercontent.com/PeteDavis2002/Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time/refs/heads/main/PlaneCrashes.json)

[GitHub repo](https://petedavis2002.github.io/Analyzing-Trends-in-the-Frequency-of-Plane-Crashes-Over-Time)

Part of this project was experimenting with D3 in JavaScript, which was novel to me. I put on a web dev hat that I didn't know I had and created this chart where the radius of semicircles at the top of the svg represents the total fatalities of each plane crash, and the radius of semicircles at the bottom of the svg represents the total number of passengers aboard the plane.
<p class="codepen" data-height="300" data-default-tab="html,result" data-slug-hash="dPGNoWj" data-pen-title="D3 v7 load data" data-user="PeteDavis2002" style="height: 260px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/PeteDavis2002/pen/dPGNoWj">
  D3 v7 load data</a> by Peter Davis (<a href="https://codepen.io/PeteDavis2002">@PeteDavis2002</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://public.codepenassets.com/embed/index.js"></script>
