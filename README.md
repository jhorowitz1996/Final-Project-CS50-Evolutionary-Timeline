# Documentation: Soaring through the Skies of Evolutionary History

## Description ##

This visualization illustrates the history of the universe within the persepctive of a flight from Los Angeles International Airport (LAX) to Boston Logan (BOS).

Youtube video submission for project [here](https://youtu.be/Aat0wP0UfRc "here"). 
## Motivation ##

I created this project as a Mother's Day gift to my mom, an Evolutionary Biology professor at UCLA. My mom has often encouraged me and her students to look beyond human exceptionalism and appreciate how small a role humankind has played within the history and evolution of the universe. Over break, she showed me a [video](https://www.businessinsider.com/animated-timeline-earth-history-2015-11 "video") infographic from Business Insider which she loved and wanted to use for her classes so I decided that I would secretly create a similar visualization for this CS course's final project. I believe this project is a fitting blend of my personal research interests in cartography and my mom's Evolutionary Biology work. 

Given that the deadline for this project falls on Mother's Day, I hope this will make for both a wonderful end to this CS course as well as a hopefully well-recieved Mother's Day gift for my mom (fingers crossed!).

## Components ##

 *The graphic that inspired this work was changed considerably for this project. To start, the flight path was changed from LAX to JFK to a flight path from LAX to BOS which more accurately reflected my own journey from Los Angeles originally to Cambridge, MA. A number of changes were added from the original infographic video which include but not limited to the manipulatability of time/event sliders, emoji-based stopping points, and functionality for other flight paths to name just a few.*

**1. Animated Flight Path**

Upon opening the index.html file in your browser one can watch the pathway of a flight from LAX to BOS set within the map frame. While the plane moves along its flight path, the corresponding labels with major events along the evolutionary timeline, date of this event, and the corresponding distance to flight destination adjust in parallel. 

**2. Event Updates** 

The events slider on the far left side of the screen provides a view of the different major events in the history of the universe with respect to the flight's movement. The timeline/flight begins at the start of the big-bang with the creation of earth and ends with the development of the world wide web. A full list of the events used for the timeline can be found in the design documentation included in this repository. 

**3. Chronological Timeleine Updates**

As the events slider above progress so in turn does the date in the history of the universe. The start of the flight path and its corresponding date on the evoluitonary timeline begins 4.54 billion years ago and ends 49 years behind 2022. The size and shape of the white box frame that holds the timeline for the animation (as with all the sliders included in this work) updates the size of square in response to the amount of text.

**4. Distance to Desitnation Updates** 

This slider, like the other two sliders included, updates in parallel with the movement of the plane and the updating text found on each slider. This distance is calculated by first giving the number of miles with respect to the scale of the timeline the flight from LAX is to Boston (approximately 2605 miles covered in air). As the flight path moves closer and closer to Boston Logan, one can come to appreciate the scale of mankind's existence across the flight path the unvierse has taken to reach the destination of our modern world in its current form. 

**5. Emoji Dropdown Selector**

A specific emoji was designated to match up with each of the events, timeline points, and distance to destination lengths along the plane's journey (ex.  "🔥" corresponds to the timeline point for "Man discovers fire" and "💻" corresponds to "Creation of the World Wide Web etc.). When an emoji from the dropdown is selected, the three sliders together with the placement of the plane along its flight path update with it. 

**6. Search Bar** 

The search bar allows the user viewing the visualization to choose a point on the timeline to see where it corresponds on the evolutionary timeline, flight path, and distance to the plane's destination. The search bar also imploys the use of an autocomplete JS library which autofills the regular expression of the date being searched into the search bar as you type. 

**7. Zoom** 

As the flight makes its way across the continental United States, zoom in/out or pan along the plane's journey to see where along the evolutionary timeline these cities fall. *Note:* This may be of interest as the flight begins to reach its final destination on the tarmack at Boston Logan. Stopping points on the timeline are closer together and therefore may be more visible when one zooms in or pans to a sideview.  


## Setup ##

**Create a Mapbox Account / Access Token** 
First, you'll need to get a Mapbox API Account token. Given that a Mapbox API token should be kept private, you as the user of the index.html file should get one for yourself in order to view this project. To do this: 
* Sign up for a Mapbox account [at this link](https://account.mapbox.com/auth/signup "at this link") (you will not be charged in any way for getting an access token) 
* After providing a username/password answer a couple of quick prompts re who you are (ex. Student, using Mapbox for data vis etc.) 
* Copy paste your Mapbox API token on line XXX in replacement of "MAPBOX ACCESS TOKEN HERE": 

Set the value of the variable `mapboxgl.accessToken` on line 168 to your Mapbox token.

Then, just open index.html in a browser. Easey peasey. :) 

## Libraries Included ## 

* **Mapbox GL JS** is a JavaScript library for immserve vector maps with real-time styling on the Web. Mapbox served as the starting point for this project to create the initial flight path animation this project made use of the Mapbox JavaScript Graphics Library to initialize the flight path from LAX to BOS. 

* **Turf.js** is an open source JavaScript library used for geospatial analysis which allows for spatial operations preformed in the browser. In the case of this project, Turf provides the JS function used to animate the plane along the line of its flight path.

* **Algolia's Autocomplete** provides a JavaScript autocomplete library for building autocomplete experiences for search. I used this JS library to build the search bar for this project and autocomplete the amount of years ago the user is searching for.  


## Credits / Acknowledgements ##

Acknowledgements to the class staff who helped me along problem sets leading up to this project especially with respect to the problem set in Week 8 which focused on web development. 

A big thanks to the original creators of this Business Insider data visualizaiton from which this project was expanded. I found the contact info for Alex Kuzoian and was able to correspond with him to better appreciate where the timeline stopping points existed to then remap those events for my project (with a number of changes made to the dataset of timeline points as well). While Alex wasn't able to provide the data for the animaiton he was kind enough to point me in the direction of the National Geographic and New Scientist resources they used to help create the visualization in 2015. 

For the Mapbox style applied in this visualization, I used [Mineral](https://www.mapbox.com/blog/designing-the-mineral-map-style "Mineral"), a specific Mapbox Studio style created by cartographer Madison Draper.

I would also like to acknowledge, the OG SOS search engine that is StackOverflow in creating this work. I owe a debt of thanks to the numerous magnanimous internet strangers who provided answers specifically those surrounding how to use template in algolia's autocomplete, JS syntax, and troubleshooting with Mapbox/Turf.js functions.

Following the final lecture on the Unicode Emoji Subcommittee, I would like to extend my thanks to Unicode's incredible work in cataloging the official Emoji charts from which I was able to retrieve the specfic emojis used in this work. 
