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

  
  **Step 7:** Add an autocomplete that searches within dates
  * Step 8: Style the autocomplete to make it fit with my look

## Technical
  * Autocomplete: choosing the item vs clicking on the magnifying glass
  * How linked should the sliders be? More linked more work but better experience
  * Should the airplane operate independently from the sliders?
  * How many emojis is too many emojis?
  * How exact should the autocomplete search? Substring, regular expression, exact match

## Ethical
  * Evo bio? too controversial?
  * The subjectiveness of the timeline
  * Why is the map US-centered?
  * Plane-phobia .... are we driving people to suicide?

## Scaling
  * If too many people use it Mapbox blocks us
