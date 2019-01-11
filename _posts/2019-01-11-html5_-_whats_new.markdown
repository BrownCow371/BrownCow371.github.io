---
layout: post
title:      "HTML5 - What's new?"
date:       2019-01-11 11:14:18 -0500
permalink:  html5_-_whats_new
---


I was recently asked in a technical interview to list a few new input types included in HTML5. Since it was released in October of 2014 and I just started coding web applications in 2018, I’ve been working with it from the get-go and never worked with the “old” version of HTML for comparison. So here is a quick overview of some of the new bling you can find in HTML5. 

Per MDN, HTML5 is both a major release of HTML with new features, and also a set of new technologies (hence it is sometimes referred to as HTML5 & friends).  There is quite a large gambit of new elements, attributes and behaviors as described on [MDN](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5). 

If you are looking for a quick cheat sheet in the subject you can check out [WPKube's](https://www.wpkube.com/html5-cheat-sheet/).

### Some new structure element tags include: 
* [`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) 
* [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
* [`<figure>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/figure)
* [`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
* [`<header>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header)
* [`<nav>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nav)
* [`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
* [`<time>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/time)
* [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

### New form types include:
* [`<datalist>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/datalist) - used to provide a drop-down list that filters (auto-complete) as users input data. 
* [`<output>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/output) - used to output the result of a calculation. 

### New input types include:
* ***color*** - provides a color picker in supporting browsers
* ***date*** - provides a date picker in supporting browsers
* ***datetime-local*** - provides a date and time picker without a time-zone in supporting browsers
* ***email*** - input can be validated as a valid email address in supporting browsers
* ***file*** - provides a button for uploading a file in supporting browsers
* ***month*** - provides a date picker for month and year in supporting browsers
* ***number*** - provides a number input field - you can also add restrictions on min and max with the min and max attributes. 
* ***range*** - provides a slider with the provided range (min and max). You can also set the step attribute. 
* ***search*** - provides a search field - acts like a text field. 
* ***tel*** - provides an input field that validates for a phone number. 
* ***time*** - provides a time slection box (not including time-zone)
* ***url*** - provides a field that validated url format
* ***week*** - provides a week.year picker in supporting browsers

See more details [here](https://www.w3schools.com/html/html_form_input_types.asp).

### And new input attributes include:
* ***autocomplete*** - specifies if an input field should have autocomplete on or off
* ***autofocus*** - specifies if the input field should have focus when the page is loaded.
* ***form*** - specified which form(s) (by id) an input field belogs to. 
* ***formaction*** - specifies the file that will be processed when the form is submitted. This overrides the action specified on the `<form>` element. 
* ***formenctype*** - specifies how the form data should be encoded (post requests only) - overrides the encoding specified on the `<form>` element.
* ***formmethod*** - specifies the HTTP method to be used to submit the form data - overrides the method specified on the `<form>` element. 
* ***formnovalidate*** - overrides the novalidate attribute of the `<form>` element.
* ***height and width*** - specifies the dimensions of an imput of type image.  
* ***list*** - used for `<datalist>` elements.
* ***min and max*** -specifies the min and max values for an input element. 
* ***multiple*** - specifies if the user is allowed to enter more than one value in the input field. Works with email and file input types. 
* ***pattern***  - specifies a regular expression that the <input> element's value is checked against - works with text, search, url, tel, email, and password input types. 
* ***placeholder*** - used to provide a hint that describes the expected value of an input field. 
* ***required*** - specifies that the input field is required before the form can be submitted. 
* ***step*** - specifies the intervals allowed for an input. For example if you list 5, then -5, 0, 5, 10 are all allowable input values. 

See details [here](https://www.w3schools.com/html/html_form_attributes.asp).

For a full list see [W3School](https://www.w3schools.com/html/html5_new_elements.asp).

