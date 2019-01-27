---
layout: post
title:      "Flexboxes and Grids"
date:       2019-01-27 15:03:05 -0500
permalink:  flexboxes_and_grids
---


While working on a code challenge, I was in need of setting up a `<div>` that contained three columns of data, each column containing multiple sections and each section having a header and two columns of data. Since a table wasn’t the right tool for the job, I decided to look into either Flexboxes or Grids. Since my application was a React app I started by trying to use reactstrap’s Containers/Grids. However, that wasn’t going to work, since you also needed to import vanilla bootstrap to use reactstrap, and that made a mess of the CSS for the rest of the app.  I didn’t want to have to fight with overriding the default bootstrap layout for the rest of the application, so I removed bootstrap and reactstrap and started building CSS from scratch.   

At first I started using CSS Grids, but I was having trouble getting the data to layout the way that I wanted so I scrapped that approach and started playing with Flexboxes instead. These were a bit easier to work with and after a lot of testing different configurations I got the results that I needed for the project. But I was still confused as to how the layout was working, so I sat down today and built out the design layout in both Flexboxes and Grids using CodePen. This made it easier to see how the design was working since the HTML and CSS were both visible on the same screen (part of the confusion with setting up the layout in my app was that each section was its own component and it was hard to wrap my brain around how all the parts came together from the CSS end of things).  After tinkering in CodePen I was able to get similar results for each approach (both Flexboxes and Grids). 

**To set up three columns in a `<div>`, with each column containing multiple sections and each section containing a header and two columns (or more if you like) of data:**

### With Flexboxes:

1. Create an outer `<div>` with a class of `“flex-container”`. The CSS for this class should be:
```
.flex-container {
      display: flex;
      flex-direction: row;
}
```
2.	Inside the outer `<div>`, create a div with a class of `“col”`. The CSS for this class can vary, but if you want three equal columns, the important part is to set the width to 33%. 
```
.col {
      width: 33%;
      margin: 10px;
      border: solid;
      padding: 0 6px;
}
```
3.	Inside this `“col”` `<div>`, add your header.
4.	Under the header, add a `<div>` that ALSO uses that `“flex-container”` class (so that we have nested Flexboxes). This `<div>` represents a row of data. 
5.	Inside each of these row `<div>`s add as many `<div>`s as you want data columns and include the data that you want to display for each.  You can add a class to these `<div>`s if you want them to have different background colors, borders, text alignments, etc. 
6.	Repeat the nested `"flex-container"` `<div>` for each row of data that you want to include in the section (under a particular header). 
7.	Repeat the `“col”` `<div>` for each of the three columns . 
8.	If you want the three columns to be different widths (maybe the first two are 40% and the last is 20%) you’ll need to create separate `“col”` classes, say one called `“col-forty”` and one for `“col-twenty”` whose widths are set accordingly. 

[See example code in CodePen](https://codepen.io/browncow371/pen/daMdVa) 

### With Grids:
1.	Create an outer `<div>`. You can add a class to this `<div>` if you want to set the background color or total width of the outer `<div>`.
2.	Inside this outer `<div>`, create a `<div>` with a class of `“grid-col-three”`.  This breaks the outer `<div>` into three columns. If you want the widths to be even, use auto for each template width. If you want the first two to be 40% wide and the last to be 20% wide, set them accordingly. The CSS for this class should be set to:
```
.grid-col-three {
     display: grid;
     grid-template-columns: auto auto auto  
}
```
3.	Inside the `“grid-col-three”` `<div>` create a `<div>` with a class of `“grid-column”`. This will represent a single column in grid. The import part of this CSS is to set the template to one column and to set the align-content to start (so that the data within the `<div>` doesn’t auto-expand to fill the whole column since each columns of the three may have different amounts of data).  The CSS for this class should be set to:
```
.grid-column {
     display: grid;
     grid-template columns: auto;
     align-content: start;
}
```
4.	Inside the first column `<div>`, add your header INSIDE a `<div>`.
5.	Next add a `<div>` after your header `<div>` that has a class of `“grid-col-two”` (in the event that you want 2 columns of data under your header). The CSS for this class should be set to:
```
.grid-col-two {
     display: grid;
     grid-template-columns: auto auto;
  }
```
6.	Inside this two column `<div>` add a `<div>` for each item you want listed keeping in mind that the items will alternate between the left and right columns. 
7.	Repeat the `“grid-column”` `<div>` format for each of the three columns of data. 

[See example code in CodePen](https://codepen.io/browncow371/pen/qgZYWN)


