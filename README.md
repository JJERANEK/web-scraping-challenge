# web-scraping-challenge
This is an assignment for the University of Minnesota Data Analytics and Visualization Boot Camp.

# Mission to Mars
This new assignment consists of two technical products. You will submit the following deliverables:
    - Deliverable 1: Scrape titles and preview text from Mars news articles. Optionally export the data into a JSON file or a MongoDB database.
    - Deliverable 2: Scrape and analyze Mars weather data, which exists in a table.

## Instructions
### Deliverable 1: Scrape titles and preview text from Mars news articles. Optionally export the data into a JSON file or a MongoDB database.
1. Use automated browsing to visit the Mars NASA news site Links to an external site.. Inspect the page to identify which elements to scrape.
2. Create a Beautiful Soup object and use it to extract text elements from the website.
3. Extract the titles and preview text of the news articles that you scraped. Store the scraping results in Python data structures as follows:
    - Store each title-and-preview pair in a Python dictionary. And, give each dictionary two keys: title and preview.
    - Store all the dictionaries in a Python list.
    - Print the list in your notebook.
4. Optionally, store the scraped data in a file or database (to ease sharing the data with others). To do so, export the scraped data to either a JSON file or a MongoDB database.

### Deliverable 2: Scrape and analyze Mars weather data, which exists in a table.
1. Use automated browsing to visit the Mars Temperature Data Site Links to an external site.. Inspect the page to identify which elements to scrape. Note that the URL is https://data-class-mars-challenge.s3.amazonaws.com/Mars/index.html.
2. Create a Beautiful Soup object and use it to scrape the data in the HTML table.
3. Assemble the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website. Here’s an explanation of the column headings:
    - id: the identification number of a single transmission from the Curiosity rover
    - terrestrial_date: the date on Earth
    - sol: the number of elapsed sols (Martian days) since Curiosity landed on Mars
    - ls: the solar longitude
    - month: the Martian month
    - min_temp: the minimum temperature, in Celsius, of a single Martian day (sol)
    - pressure: The atmospheric pressure at Curiosity's location
4. Examine the data types that are currently associated with each column. If necessary, cast (or convert) the data to the appropriate datetime, int, or float data types.
5. Analyze your dataset by using Pandas functions to answer the following questions:
    1. How many months exist on Mars?
    2. How many Martian (and not Earth) days worth of data exist in the scraped dataset?
    3. What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
        - Find the average the minimum daily temperature for all of the months.
        - Plot the results as a bar chart.
    4. Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
        - Find the average the daily atmospheric pressure of all the months.
        - Plot the results as a bar chart.
    5. About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
        - Consider how many days elapse on Earth in the time that Mars circles the Sun once.
        - Visually estimate the result by plotting the daily minimum temperature.
    6. Export the DataFrame to a CSV file.

## Completing the Analysis
Deliverable 1: Scraping the web data from the Mars NASA site is pretty straight-forward. Using Splinter, the HTML code was extracted with Beautiful Soup, and the titles and preview text of the articles were placed into a list of dictionaries to eventually be placed into a MongoDB database and a JSON file for storage. (See part_1_mars_news.ipynb in Starter Code for the notebook.)

Deliverable 2: After data was scraped, Python and Pandas functions were used to find the appropriate data and plot relevant results. Some data types had to be changed in order to use them appropriately. (See part_2_mars_weather.ipynb in Starter Code for the notebook.)

# Results
The following pieces existed in the starter code at the start of the assignment:
    - On average, the third month has the coldest minimum temperature on Mars, and the eighth month is the warmest. But it is always very cold there in human terms!
    - Atmospheric pressure is, on average, lowest in the sixth month and highest in the ninth.
    - The distance from peak to peak is roughly 1425-750, or 675 days. A year on Mars appears to be about 675 days from the plot. Internet search confirms that a Mars year is equivalent to 687 earth days.

I was able to confirm that the third month has the coldest minimum temperature, and the eighth month is the warmest. I was also able to confirm that atmospheric pressure is lowest in the sixth month and highest in the ninth. 

However, when calculating Earth days in a year on Mars, I came up with a different number than the one given in the starter code. The number I was able to find was 690, which is actually more accurate to the stated 687 days that the internet search confirmed. I don't believe using temperature data is that accurate of a way to find the length of a year, since temperature can fluctuate for many reasons.