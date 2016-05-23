### Summary
 
Prosper is a peer-to-peer loan facilitator. 
Since it opened in 2014 it has facilitated over $1 Billion in loans. 
I am interested in: a) the types of loans it facilitates and b) the return on those loans.
My visualization will use the loan data to display those two facets.

_______________________________________________________

### Design

Explain any design choices you made including changes to the visualization after collecting feedback
<ol>
<li>The main issue that I faced was: How to reduce the dimensionality of a multi-dimensional dataset, where the story that I wanted to tell
 depended on many variables (and also categories within those variables).


The first attempt at this aspect was not successful: 
Original Visualization: http://www.mylescallan.com/udacity/analytics/ProjectSix/ProjectSix/index.html


That original visualization focused too much on information and too little on the story. The evolution of the vizualization explains the decisions that I made:
<ol>
  <li>The first chart remains, broadly the same: A storyboard of the evolution of loans over the years.
    <ul>
    <li> animation: over years
    <li> color: aggregation, over loan types
    <li> position: disaggregation, over states
        </ul>
  <li> I moved the second chart and made it a companion chart (as, as Sheng_Kung pointed out, it displays similar information in a different way).
      <ul>
    <li> this chart contains the same design decisions as the previous chart, but using a map instead of a bar chart.
      </ul>
  <li> The third chart I moved to be a companion of the next chart. It is a chart of loan status over time (which is required information as it tells a story about the reliability of information in the main chart):
        <ul>
    <li> color: aggregated bar chart (over loan status)
    <li> position: for each year
    <li> content: I changed this, for the submitted version, to reflect both percentage and dollar value (again, as the result of a comment from Sheng_Kung)
      </ul>
  <li> The fourth chart captures information about the yield for each loan. This was the most complicated information to display in my visualization:
        <ul>
        <li> animation: over credit rating
    <li> color and position: for time (this double encoding was warranted due to multi-dimensional aspect of this part of the visualization)
    <li> color: shading to highlight potential problems with the reliabilty of some of the data.
    <li> scale: for loan value for each time period (where the circle areas are proportional to the loan value)
    <ul>
    </ol>
Even with a high level of encoding of information, this visualization required a commentary for each page, which is supplied in a "Details" section for each chart.

 <li> Based on the Comments from @Sheng_Kung, I made the following changes (essentially one change for each paragraph of his critique):
Reduced the visualization to 2 main charts (with 2 companion charts)
Added "Notable Features" section to "Details"
Re-sized charts, so the visual height should be set for all/most devices
Bubble areas proportional to Loan Values (note added to chart)
Changed units for charts (Yield chart begins with fixed axes, Loan Status added percentages).

 <li> Based on Comments from sathya_67045301587081d, I made the following changes:
Added text to side column to explain that clicking on an item in that chart stops the chart and displays the selection.

 <li> Based on Comments from my wife:
Used vh instead of height, to constrain the charts in different devices. Used CSS to format the text so that it is presented in 'chunks' that correspond to the information that it conveying about the charts.

 <li> Submitted Visualization:
http://www.mylescallan.com/udacity/analytics/ProjectSix/Github/index.html
</ol>

_______________________________________________________

### Feedback 

Include all feedback you received from others on your visualization from the first sketch to the final visualization
<br>
Link to Feedback: https://discussions.udacity.com/t/p6-request-for-feedback-on-data-visualization-project/169217
<br>
<br>

<ol>
<li> Sheng_Kung Udacity Coach
<ul>
<li>The visualizations you've built are nice from a technical perspective, but I think more work needs to be done to better convey the story you want to tell. Many of the visualizations in the presentation lean too far in the exploration direction, so some additional guidance or focus is suggested to make them more explanatory in nature. You can allow readers the ability to explore your visualizations, but the first thing that you need to show your reader for each figure is the main point of why that visualization is useful to look at. Another thing that can help here is to use the text in your "Details" sidebar to explicitly note the main point of each visualization.

<li>There are a few suggestions that are common between multiple visualizations. The scale for the size of bubbles is not clear in any visualization where they are used. A legend will be useful to show what values correspond with certain sizes of bubble. In addition, make sure that your values vary linearly with the bubbles areas rather than their radii. Otherwise, large values may be interpreted as much more dramatically more prominent than they should.

<li>A second general suggestion applies for the use of color in the second and fifth plots. Since there is only one point per category on the horizontal axis, the color is a bit redundant with the horizontal axis label. You might consider removing color or the legend to provide increased space for the main body of the plot; double encoding is best used if there's something of special importance to be conveyed. Note that the suggestion does not apply as strongly for the fourth plot, since there are multiple points in each year and color serves as a good way of seeing the differences between years.

<li>One more general note to make about plots: on smaller windows, parts of the visualizations can get cut off. For my laptop window size, the bottom of the final button got cut off for the first, fourth, and fifth visualization. Parts of the map got cut off for the map in the third visualization; if there was additional information that was supposed to be conveyed from zooming in to the map, it wasn't visible.

<li>Moving on to more specific details, there are a few suggestions for the navigation of the visualizations. I noticed faint shadows of up and down arrows next to the left and right arrows; if you don't have any use for these additional buttons then you might want to see if these buttons can be removed. You should also consider moving the left / right navigation to the center of the page rather than having it be on the left side of the page. I do not think that the "Details" button needs to be so large as to span most of the length of the page.

<li>For the first plot, I would suggest starting with the "fixed axis" option rather than variable axis. This makes the match up between the main plot and the horizontal bars on the year navigation more salient, and provides a better anchor for readers who are just getting to know the dataset. Moving back to general suggestions for a moment, you might want to cut down the dataset to just loans from 2006-2013. Since there are only a couple of months from 2005 and 2014 in the dataset, people might end up drawing false conclusions based on counts or summed values for these two years. As for things that I noticed in the plot, I saw that most loans are part of the "debt" category, and that there does not appear to be too many dramatic differences in loan values for each state across the years.

<li>It feels like the visualization type does not serve the main findings for the second visualization well. The main thing I saw was that the majority of loans went from "Completed" status to "Current" status from the early years to more recent years, and it took me a minute to think about the data before I realized why this was the case. I would recommend emphasizing the trend of loan statuses across the years by using a line plot. In addition, you might want to try plotting the vertical axis as a % of loans within each year to clearly show the crossover between "Completed" loans and "Current" loans as a function of time from when the dataset was built.

<li>The third plot strikes me as being far too exploratory, I'm not sure what part of the data is being emphasized here. Make sure that it is clear what should be gained from the plot, and what makes it unique compared to the first visualization. I also noticed that the "Dollar" and "Count" buttons do not update until a different visualization parameter is changed. I like how each loan category has a different color scheme to make it clear when categories have changed.

<li>I don't really have any specific things to note about the fourth and fifth plots, but it is perhaps because I do not have a good idea of what the main story being told is. I think that the earlier suggestions for trying to focus the visualizations and to provide more directed commentary in the "Details" sidebox will be useful for helping the reader understand the significance of what is being plotted. This post is already getting long enough, so I think I'll just leave my commentary as it stands here.
</ul>
<br>
<li> sathya_67045301587081d Udacity Peer
<br>
My Feedback
<ol>
<li> Overall nice animation depicting the loans over the years for various states
<li> Animation keep continuing, i think you can stop once it reaches the last year leaving users to explore on their own
<li> Not sure why the year have different sizes.
<li> It will be great to add color to the category in legend, currently, it is only text, took some time to hover over the graph to get the details
<li> On the second visualization, y axis text is not visible
</ol>
<li> My wife
<ul>
<li>Depending on which device you use, the charts can go off the page.
<li>The text is not formatted and not presented in well-delineated blocks.
</ul>
</ol>

_______________________________________________________

### Resources

List any sources you consulted to create your visualization

The overall presentation uses: http://lab.hakim.se/reveal-js/#/ (Reveal). This allows a storyboard effect for the charts in the visualization.
<ol>
<li> The 2 main visualizations were based on the dimple storyboard visualization: http://dimplejs.org/advanced_examples_viewer.html?id=advanced_storyboard_control
<li> The alternative (geographical) visualization was based: https://github.com/CSE512-15S/a3-aljadaan-rlordon-olsufj Weather in the USA Ross Lordon, Jacob Olsufka, Ahmad Aljadaan
<li> The companion visualization for the second graphic was based on: http://dimplejs.org/examples_viewer.html?id=bars_vertical_stacked_100pct
</ol>
Some alterations to the base code in each case were:
<ol>
<li> Changing the order of items in legends, from http://stackoverflow.com/questions/23530434/in-dimple-how-do-you-change-the-order-of-the-series-ina-legend
<li> Change tooltip entries (due to scaling the circles by area): https://discussions.udacity.com/t/bubble-scaling-in-dimple-js/161941/10
</ol>