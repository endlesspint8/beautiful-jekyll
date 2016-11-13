---
layout: post
title: Data Guide for the Beer Perplexed II
subtitle: Part II - What's in a Style? 
tags: ["RShiny", "datavis"]
shortlink:
twitimg: 
---

## What's in a style?


As we inch our way closer to beer authority [FN: that's a fine name but it's already taken by a New York City bar (link) situated across the street from the Port Authority], approaching the topic from many angles it is important to occasionally take a deeper dive. This is not one of those times. Not really. Well sort of. We will get more information on beer categories and develop an idea of their characteristics on a closer but still superficial level. It's like knowing the stats of a player. You may be able to discuss them with more understanding but if you haven't seen them in action you can't truly speak about their presence. Ultimately, knowing any subject is to have made yourself more intimately familiar with it then from just reading about it. So once you're done with this piece (but not before!) go out there, grab a pint, and get yourself some learnin’.

The characteristics we will cover are primarily three: ABV, IBU, & SRM, four if you include temperature. My throwing acronyms, can appear quite inline with the sports analogy from above. These letters represent a solid grounding, certainly a necessary one, in better understanding beer styles but they will ultimately be sterile and insufficient without some first-hand experience. Nevertheless, this information is important in getting closer to understanding what is expected f styles and how they relates when comparing one beer to another.

To give these three measures more soul let's bring our senses into the mix and match each of the measures with one or more of them.

* Alcohol by volume (ABV; https://en.wikipedia.org/wiki/Beer_measurement#Strength) -> taste & touch
* International bittering units (IBU; https://en.wikipedia.org/wiki/Beer_measurement#Bitterness) -> taste & smell
* Standard Reference Method (SRM; https://en.wikipedia.org/wiki/Standard_Reference_Method) -> sight
* Temperature -> taste [FN: that's right newbie, temperature has an impact on the taste of beer] & touch

This association only leaves out primary sense, hearing, which is a weird one to consider for the direct tasting of beer but is indispensable in learning from others and appreciating convivial company. Additionally, we’re stretching a little bit (though not much) to mention smell with respect to IBU. Now that we've teased this out long enough let us get down to particulars.

I can rattle off specifics on what style has what and how it compares to another, how certain styles are similar, how they're different and so forth. However, you need not sit here idly through my rambling, shit you may have already clicked over to another site by now. No sir, instead we're going to use the wonderful interactive features of the Internet to breathe still more life into these characteristics.

We will use two primary graphs to explore this data world further. 

The first is a one feature exploration of ABV, IBU, SRM, & Tempby grouped by beer category, glass, and yeast. 

**boxplots**

<iframe src="https://endlesspint8.shinyapps.io/cb_sh_bxplt/" width="800" height="600" frameborder="0" marginwidth="0" marginheight="0"></iframe>
<sub>Data Source: <a href="http://www.craftbeer.com/beer-styles" target="_blank">CraftBeer.com</a> / 
Scraping Template: <a href="https://github.com/cs109/content/blob/master/labs/lab2/Lab_2_A_Live.ipynb" target="_blank">CS109</a> / 
Vis Code: <a href="http://bl.ocks.org/mbostock/4062045" target="_blank">Force-Directed Graph</a> & <a href="http://www.coppelia.io/2014/07/an-a-to-z-of-extra-features-for-the-d3-force-layout/" target="_blank">Extra Features</a> / <b>Share <a href="https://twitter.com/intent/tweet?text=pic.twitter.com/mT5QiQ9Ncz Data Guide for the Beer Perplexed, Part 1&url=http://bit.ly/prplxd1&via=endlesspint8&hashtags=D3,beer,dataviz" target="_blank" title="Share on Twitter">Hairball</a></b></sub>

Far from it for me to tell you how to go about your beer adventure but I suggest for the data exploration in the first graph, which displays group characteristics as boxplots, we stick with the categories. Categories?! Wait, what? I thought we were talking about the 70+ styles from the previous guide entry (link). We still are but at one higher level. You should have noticed that some styles, even if you knew nothing else about beer, appear to have natural groupings based on their names. For instance there are several country specific names, such as American, Belgium, British and German. A country name surely does not suggest all said beers are similar but there is a common heritage nonetheless (something for another time). Beyond the easily identifiable country names there are common descriptors: Pale Ale, Indian Pale Ale, Stout, etc. You can be sure that regardless of country origin these distinguishing characteristics cross borders.

Don't get too excited by the category idea, it was already introduced last time by way of the color groupings used in both the link and node (link) and co-occurrence matrix visuals (link). It is these groupings that we are looking at and will be getting a handle on first. This is a more manageable exercise since there are fewer to keep track of and the differences between them are more distinguished.

Trying several styles within a category helps to pick up on nuances of both the styles and categories. You will see the features in common that bind them together as well as their differences which help distinguish them. The latter may not be readily identifiable when starting out, hence the comparisons across categories which helps build up observational qualities and knowing what to look for.

Back to the graph. Sticking with the style categories on the X axis, mess around and vary the Y axis to display the features. If you haven't seen a boxplot (https://en.wikipedia.org/wiki/Box_plot) in a while, maybe since high school math class, allow me to provide a quick recap. Each box represents information in the same way: the bisecting line represents the median, fancy talk for the 50th percentile, half the beers appear above this line and the other half below, the top of the box is the 75th percentile and the bottom the 25th.

INSERT

WHAT DO YOU SEE IN THE PLOT FOR... ABV, TEMP, ETC.

The second graph is slightly more sophisticated, allowing for more than one feature to be plotted, lending itself to be used as a comparative tool. What you will see here are the beer features standardized (https://en.wikipedia.org/wiki/Feature_scaling#Standardization). We have the opportunity to map three data elements onto each point, a variable each on the X axis, Y axis, and the dots themselves by way of using color. The graph defaults to ABV against IBU. 

**scatter** 

<iframe src="https://endlesspint8.shinyapps.io/cb_sh_sct/" width="800" height="700" frameborder="0" marginwidth="0" marginheight="0"></iframe>
<sub>Data Source: <a href="http://www.craftbeer.com/beer-styles" target="_blank">CraftBeer.com</a> / 
Scraping Template: <a href="https://github.com/cs109/content/blob/master/labs/lab2/Lab_2_A_Live.ipynb" target="_blank">CS109</a> / 
Vis Code: <a href="http://bl.ocks.org/mbostock/4062045" target="_blank">Force-Directed Graph</a> & <a href="http://www.coppelia.io/2014/07/an-a-to-z-of-extra-features-for-the-d3-force-layout/" target="_blank">Extra Features</a> / <b>Share <a href="https://twitter.com/intent/tweet?text=pic.twitter.com/mT5QiQ9Ncz Data Guide for the Beer Perplexed, Part 1&url=http://bit.ly/prplxd1&via=endlesspint8&hashtags=D3,beer,dataviz" target="_blank" title="Share on Twitter">Hairball</a></b></sub>

Without doing anything else it is pretty clear that there is a positive general correlation between the two beer characteristics. Beers with higher alcohol content tend to have more bittering units and the other way around. To get an idea of what styles fall where, use the third drop-down menu option, "Color By", to select a grouping of your choosing. Again, I recommend "category". 

There are a lot of dots and a lot of colors. Don't just sit there, use your web browser zoom capabilities to make the graph bigger in order to get a better view. Still a lot going on but we see some general groupings: Strong Ales, IPAs, and Stouts gravitate toward the upper right-hand corner while Wheats, Wild Sours, and Dark Lagers are found in the opposite corner. What's the relation of IBU to color? Change the Y axis from ABV to SRM. We now have a more dispersed cloud. In order to see the general trend click the "Smooth" checkbox. A lazy upside down "U" presents itself. This indicates that the lighter colored beers fall on either end of the IBU spectrum (Wheats and Pales) with the darker beers in the middle (Porters and Stouts).