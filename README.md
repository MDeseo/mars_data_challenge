# Assignment 12 - mars_data_challenge

This Assignment was created in conda version 4.13.0 in "PythonData" environment using Jupyter Noteboook server version 6.0.3.

This assignment consists of two parts.
 
Part 1: Scrape Titles and Preview Text from Mars News 

The Jupyter notebook file for this part is named "mars_data_challenge_part_1.ipynb." The relevant dependencies for web scraping were imported.

Mars News was scraped from an external site (https://redplanetscience.com/) using Splinter and Beautiful Soup, specifically the title and preview text, or summary text, of each article on the landing page. The scraped elements were identified using Chrome DevTools.

The scraped data were stored in a Python dictionary with each dictionary haviong two keys: (1) title; and (2) preview.  An example is the following:

{'title': "Mars Rover Begins Mission!", 
      'preview': "NASA's Mars Rover begins a multiyear mission to collect data about the little-explored planet."}
Store all the dictionaries in a Python list.

The scraped data was stored in a JSON file and saved in the same folder with the name "mars_news_summaries." 


Part 2: Scrape and analyse Mars weather data

The Jupyter notebook file for this part is named "mars_data_challenge_part_2.ipynb." The relevant dependencies for web scraping, Pandas, and Matplotlib were imported.

The weather data exists in a table in an external site with the URL: https://data-class-mars-challenge.s3.amazonaws.com/Mars/index.html.

The Mars Temperature Data were manually scraped by using Splinter and Beautiful Soup. 

To determine if teh table contianes usable classes, Chrome DevTools was used to inspect the elements.

Using Beautiful Soup <find_all> method to extract all the rows with a line of code, the extracted data from each cell in a specified row were stored in a Python list.
The data from each row was added to the Python list using <for loop>.

The scraped data was assembled into a Pandas DataFrame with the columns having the same headings as the table on the website. 

The explanation of the column headings is below:

- The 'id' heading: The identification number of a single transmission from the Curiosity rover.
- The 'terrestrial_date' heading: The date on Earth.
- The 'sol' heading: The number of elapsed sols (Martian days) since Curiosity landed on Mars.
- The 'ls' heading: The solar longitude.
- The 'month' heading: The Martian month.
- The 'min_temp' heading: The minimum temperature, in Celsius, of a single Martian day (sol).
- The 'pressure' heading: The atmospheric pressure at Curiosity's location.

The data types of all the DataFrame columns were examined and since the all data were "object" the data were converted to the appropriate datetime, int, or float data types.

The following questions were addressed: 

Q1. How many months exist on Mars?

Q2. How many Martian (and not Earth) days' worth of data exist in the scraped dataset?

Q3.  What are the coldest and the warmest months on Mars (at the location of Curiosity)? Get the answer by averaging the minimum daily temperature of all the months. Plot the results as a bar chart.

Q4. Which months have the lowest and the highest atmospheric pressure on Mars? Get the answer by averaging the daily atmospheric pressure of all the months. Plot the results as a bar chart.

Q5. About how many terrestrial (Earth) days exist in a Martian year? That is, in the time that Mars circles the Sun once, how many days elapse on Earth? Visually estimate the result by plotting the daily minimum temperature.

Finally, the DataFrame was exported to a CSV file ("mars_temp.csv").
