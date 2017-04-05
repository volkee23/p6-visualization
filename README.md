# Udacity Project Visualization

## Summary
This is a visualization project that uses the Flights data from RITA database. I downloaded raw data from January 1, 2010 to January 1, 2017 and used D3.js to display the data. I used the delay data for each month that was reported and roll-them-all-up to display the trend of total minutes delay over the years (from 2010 to 2017).
## Design
I follow the Martini Glass Structure approach and starts with an author-driven approach to show the percentage of total delay (minutes) for each year for all carriers and then iterate through all the carriers one-by-one. By doing this, I was able to show the users the trend of delay data as a whole and then show them the difference between carriers as it iterates through them one-by-one. At the end, I gave total freedom to the users by giving them a button to click and choose which carrier they want to see.

## Feedback
1. The display looks so bare. I don't understand what story you're trying to tell and is not very clear to me what the lines stand for. (Action: As a result of this feedback, I added labels to the X and Y axis and added the "legend" section to indicate which line is for what cause of delay.
2. The display is too slow and is does not have anything that indicates what data they represent.(Action: In addition to the steps I did in the first feedback, I change the duration of the transition from 5 seconds to 3 seconds.)
3. During initial load or when it's loading data, I don't really know what it's doing and all I see are blank screen. I could not tell if it's stuck or if it's doing something. (Action: I added a message section where to show what stage in the process its in. It can be found at the bottom section and I thought it gives it a more dynamic feel as the message changes as the screen changes)
## Resources
1. Data Source - https://docs.google.com/document/d/1w7KhqotVi5eoKE3I_AZHbsxdr-NmcWsLTIiZrpxWx4w/pub?embedded=true
2. Design Strategies - http://infosthetics.com/archives/2011/01/research_telling_stories_with_data.html
3. Git Hub Commands - https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
4. D3 Examples:
..* http://bl.ocks.org/phoebebright/raw/3176159/
..* http://stackoverflow.com/questions/22452112/nvd3-clear-svg-before-loading-new-chart
5. Markdown Cheat Sheet - https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
  
