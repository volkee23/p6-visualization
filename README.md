# Udacity Project Visualization

## Summary
This is a visualization project that uses the Flights data from RITA database. I downloaded raw data from January 1, 2010 to January 1, 2017 and used D3.js to display the data. I used the delay data for each month that was reported and roll-them-all-up to display the trend of total minutes delay over the years (from 2010 to 2017).

Which delay category caused the most number of delay minutes for each airline? How about for all airlines combined? These are some of the questions that I thought users would like to know when they look at this type of data from the airlines. I initially thought before looking at the data that the majority of flight delays are caused by weather-related conditions. The data as presented by the line charts proved me wrong and shows that late-arriving aircraft and carrier delay are the top 2 causes of flight delays. There are some airlines where either carrier delay or NAS delay are the top category like for Comair Inc (carrier delay is 1st) and Continental Air (NAS delay is 1st) but for most of them, late-arriving aircraft is at the top or near the top of the chart. I thought the line charts clearly answered those questions for me and by allowing the user to stop animation and choose which airline they want to see, that clearly covers what most users wanted to know about this data.
### Other Observations
1. You'll find some airlines with different name but have the same carrier code (example: Pinnacle and Endeavor) - I did some research and found that after exiting the bankruptcy protection, Pinnacle was renamed to Endeavor on August 1, 2013. 
2. There are some airlines that are listed as one of the providers of data but we found no data for them during processing. Carriers include Aloha Airlines, America West Airlines, Atlantic Coast Airlines, to name a few. After doing more research, I found that the data exists for these carriers but for different date ranges.
## Design
I follow the Martini Glass Structure approach and starts with an author-driven approach to show the percentage of total delay (minutes) for each year for all carriers and then iterate through all the carriers one-by-one. By doing this, I was able to show the users the trend of delay data as a whole and then show them the difference between carriers as it iterates through them one-by-one. At the end, I gave total freedom to the users by giving them a button to click and choose which carrier they want to see. 

At first, I used Tableau to do a prototype of what I'm trying to do. I considered using a map chart where I'll put the delay categories (sum) for each carrier in the state where they are based/located but after trying to do it in Tableau to see how it will look like, I scrapped that idea. Not only was it harder to do but also, it would not convey the story I wanted to tell.

Using Tableau once again, I load my sample data and start experimenting with different type of charts. I chose the line chart as my final design due to the following:
- a continuous field (year and month) which can be my columns. This will allow us to display the trend of the flight delays (by category) using the range of data selected from the source. 
- have more than 2 measure fields (i.e. sum(weather_delay), sum(carrier_delay), etc) which can be depicted as one line for each using different color. By creating a section that will show the legend for these measure fields, I thought I'll be able to cleary distinguish one from the other

Using the chart from Tableau as a prototype, I then used D3.js to build the visualization component of this project. I used the following color for delay categories:
- Carrier Delay (Red)
- Weather Delay (Lime)
- NAS Delay (Blue)
- Security Delay (Aqua)
- Late Aircraft Delay (Orange)

Also, I added a tooltip for each of them. I copied the description from the RITA website and use them as the tooltip text. I also added a button to toggle from animate (author telling the story) to non-animate (give control to the user) - I thought this is a nice feature to allow them to skip the story-telling if they find it too long or to go and check the delay information for a particular airline.


## Feedback
1. The display looks so bare. I don't understand what story you're trying to tell and is not very clear to me what the lines stand for. (Action: As a result of this feedback, I added labels to the X and Y axis and added the "legend" section to indicate which line is for what cause of delay.
2. The display is too slow and is does not have anything that indicates what data they represent.(Action: In addition to the steps I did in the first feedback, I change the duration of the transition from 5 seconds to 3 seconds.)
3. During initial load or when it's loading data, I don't really know what it's doing and all I see are blank screen. I could not tell if it's stuck or if it's doing something. (Action: I added a message section where to show what stage in the process its in. It can be found at the bottom section and I thought it gives it a more dynamic feel as the message changes as the screen changes)
4. Animation takes too long and I wanted to take control and navigate myself. Also, I don't really understand what "NAS" stands for - do you have an explanation. (Action: I decided to add a toggle button to allow the user to skip through and give them freedom to navigate the screen. Also, I decided to add a tooltip in the legends section to provide a brief description of each category)
## Resources
1. Data Source - https://docs.google.com/document/d/1w7KhqotVi5eoKE3I_AZHbsxdr-NmcWsLTIiZrpxWx4w/pub?embedded=true
2. Design Strategies - http://infosthetics.com/archives/2011/01/research_telling_stories_with_data.html
3. Git Hub Commands - https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
4. D3 Examples:
- http://bl.ocks.org/phoebebright/raw/3176159/
- http://stackoverflow.com/questions/22452112/nvd3-clear-svg-before-loading-new-chart
- http://stackoverflow.com/questions/42437908/d3-javascript-function-scope-with-setinterval-and-clearinterval-and-event-handl
5. Markdown Cheat Sheet - https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
6. Code Formatter - http://www.cleancss.com/html-beautify/
  
