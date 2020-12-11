### times-100-list-diversity-analysis

# How Diverse Are Time's 100 Most Influential People?

Each year, beginning in 1999 (and digitally from 2004), TIME Magazine releases a list of the 100 most influential people in the world for that year. Chosen exclusively by Time's editors after nominations from alumnae and international staff, the list features people who are "recognized for changing the world, regardless of the consequences of their actions."

Appearing on this list is generally considered an honor, and has thus generated controversy over whom it includes as well as excludes. While the list is presented as a reflection of the current state of the world, the editorial decisions behind it are telling of the power structures that shape our worldviews.

### Here are the Jupyter notebooks behind the analysis: 
- The first scrapes Time's 100 Most Influential People from the years 2004, 2007, 2010, 2013, 2015, 2017, 2019 and 2020 using BeautifulSoup and Selenium for each (since they all have different formats and div-trees). From Time I get their names, categories, links to the blurb and year. Because there was no demographic data, I then looped them through Google's graph search to get nationality/place, age, description and profession. I extracted as many gender pronouns as possible from the description. I've exported each year's data into CSVs with some basic cleaning.

- The second notebook cleans and merges all the data from the first into one dataframe. I converted the pronouns into a 'gender' column, but 65% were null, so I manually added those in an Excel file. I then read this file in again, cleaned it some more, and made a final dataframe with all the necessary columns and as few null values as possible.

- The third notebook prepares the dataframe for mapping via Mapbox by converting data from the dataframe into properties for geojson. I used Google geocode API to find the coordinates for each of the ~800 people on the lists over the years, merged this geometry into the properties, and then exported the file as geojson to use with Mapbox.

Finally, I edited the .html map file written in JavaScript to make small style and colour changes on the map. The final map has all each of the years' 100 most influential people, mapped by their nationalities/place of birth, and color-coded by gender.

## View the map here:
[paromasoni.github.io](https://paromasoni.github.io/)
