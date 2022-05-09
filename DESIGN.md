# Design Document

## Process
  **Step 0:** To start I began by implementing the animation of the plane flying across the continental United States using the Mapbox Graphics Library.   The Mapbox documentation served as a helpful guide for how to implement this. I then chose the map style I most liked the look of for this project which is called [Mineral](https://api.mapbox.com/styles/v1/mapbox/cjtep62gq54l21frr1whf27ak.html?fresh=true&title=true&access_token=pk.eyJ1IjoibWFwYm94IiwiYSI6ImNpemc0YWlpNzAwcXUyd21ldDV6OWpxMGwifQ.A92RQZpwUgtGtCmdSE4-ow#5.34/48.306/6.527). By outputting the built-in basemap style for the Mineral Mapbox style on line 171 here: `style: 'mapbox://styles/jenniferhorowitz/cl2ezi8vs000u14pgj6dfcji5'`.
              
  **Step 1**: As discussed in the credits/acknowledgements portion of the documentation available in my ReadME file, this project began initially as an attempt to modify an Business Insider animation which imployed a similar type of logic in its animation. In the initial animation from Business Insider, the authors of that work used the distance between LAX Airport to JFK Airport for their timeline points. To process and modify the data, the distnace to the location of JFK needed to be changed from the latitude and longitude points associated with LA and NY to LA and Boston. This allowed me to re-route the plane from LAX-JFK to LAX-BOS for the animation. Knowing that I would need the values to be recalculated in parallel with timeline events for a distance that was not the same as the LAX to JFK flight path, I recorded all of the stopping points used in the Business Insider visualization and made the neccessary mathematical calculations for the discretization of steps in the journey from LAX to BOS instead. 
  
Below are the modfied values used to implement the project for LA to Boston instead of New York:

<img width="431" alt="Screen Shot 2022-05-08 at 7 49 23 PM" src="https://user-images.githubusercontent.com/66505479/167320807-60d2326d-218f-4bd8-8dbd-419c3c7485b6.png">

  
  **Step 2:** My next step was to create the 3 sliders to represent the to date, distances, and events associated with the flight's path so that when you move the slider the text/numbers changed for each. To do this, I made a list of entries with each entry in the form of a dictionary with three values: 1) descriptive date, 2) year, and 3) event name. I made a modification to the html responsible for the slider interface so that the shape of the rectangle would change based on the amount of text that filled up the slider shape. 
  
  **Step 3:** I then needed to link the sliders together so they would always refer to the same point in time. To do this, I set the value of slider 1, 2, and 3 equal to the index so that the movement of each along the steps used for the animation would be tied to one another thereby displaying the content pertaining to each date, event, and distance from the tarmack. 
  
  **Step 4:** To add the first layer of manipulatability to the map, I adjusted the sliders to that if one wanted to move the plane to a specific point along the flight pth the information portayed on the sliders would change with it. I  et the value of each step to link up with the stopping apoints along the flight's journey so that as the plane was manually moved to different stops the information regarding its corresponding event/date/distance would be displayed as well. 
  
  **Step 5**: I wanted to then ensure that the sliders' movement was linked to the fly-through of the plane along the US. I set the geometric coordinate of the plan along its journey to the updating steps of the index responsible for controlling the sliders' progression. I integrated the sliders depiction of points along the timeline to respond directly to the frame rate of the animation (controlled via Turf.js's animate function) so that as each point updated along the next set of coordinates, the sliders respond in turn as the speed covers each point 
  
  **Step 6:** I then provided an additional layer of functionality (and fun!) via the emoji dropdown which I then also linked to the index which controls both the geometric coordinates of the plane icon as well as the placement of all three sliders. Inspired by our final lecture in class from Jennifer Lee, I found myself having fun deciding on the appropriate emoji to use for each event along the timeline. 
  
Here is a comprehensive list of the emojis I used: 

<img width="670" alt="Screen Shot 2022-05-08 at 7 47 40 PM" src="https://user-images.githubusercontent.com/66505479/167320744-12a0a9ee-e8eb-49af-9bbb-52b88791959f.png">

  
  **Step 7:** The final layer of user functionality was added by way of a search bar. Using Algolia's autocomplete function I then implemented an autocomplete feature so that as the user looked up a date, the time would be suggested to them via a drop down bar with a set of options for a period of time ago distant from the present date. 

  **Step 8:** The last modification I made was to modify the styling of the search bar (coloration, size, spacing, placement of the magnifying glass) so that it was set with its own slider rectangle and the emoji drop down given its own respective square as well. 
  
  
## Technical

1. The main issue I ran into was the connection between between the events on the timeline and the movement of the plane icon along the map frame. At first I had initially thought to sepearte the events to an even set of intervals along the map frame. This resulted in the placement of the plane along the US in incorrect locations with respect to the events portrayed on the evolutionary timescale. Instead of pacing out the movement of the plane along the arc evenly I modified my initial calcuation to instead calculate the amount of distance between each event (not all of which were equal). By calculating the difference between each pair of event individaully the program I wrote for this project could then be modified with a different destination (ex. Chicago O'Hare's latitude/longitude coordinates) given that the ratio of distance between each event was implemented rather than spreading them out across the length of the flight path's arc). 

2. I also ran into a few snags when working to implement the autocomplete function. Alogolia's built-in functionality to choose an item from the drop down vs. being able to immmidiately implement a search query I found difficult to actualize. I realized that in order to choose a search item Algolia's autocorrect function neccesitates the use of the magnifying glass as a button. Other decisions needed to be taken into account with regar to the technical implementation of the search function in that I wasn't sure as to whether I should use substring, regular expression, or exact match to ensure the autocomplete worked effectively and with the most ease of use for the user. I ultimately decided to use regualr expression autocomplete so that users could choose from a set of different options across the evolutionary timeline. 

3. I hestiated at first to connect the movement of all three sliders together with the airplane's movement given the neccesiary technical complexity of creating a shared index function for each to tie them altogether. I ultimately decided that the user experience of the visualization would be far improved if all these elements were tied together.

  * How many emojis is too many emojis?
  * How exact should the autocomplete search? Substring, regular expression, exact match

## Ethical
With respect to the ethical concerns we are asked to describe for our project a few come to mind: 
  * While I included a selective set of major points in the history of the unvierse for this visualization this does not give credit to the major milestones of true of other cultures and ethnicities. 
  * Map projection in this case could be an ethical subject of discussion for this project given that many feel that certain map projection systems give an over-alottment of space on the map to Western geographic locations. 
  * This visualization could also be considered problematical from an ethcial perspective given that the animation is centered on the United States. In future iterations of this project, expanding the universal animation timeline to be set to other flight paths and corresponding coordinates would allow individuals across the globe to visualize the timeline and transformation of the universe along the flight path to thier own hometown. 

## Scaling
A final unlikely concern (but also important to consider from a logistical perspective) is that of scaling. If too many people attempt to log onto the website visualization all at once, they could overwhelm the number of requests associated with my acccess token for Mapbox. However, this is admittedly very unlikely. 
