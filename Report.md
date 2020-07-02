## Introduction :
For this Capstone project, I am creating a hypothetical scenario for a concept Burmese
restaurateur who wants to explore opening an authentic Burmese restaurant in Toronto area.
The idea behind this project is that there may not be enough Burmese restaurants in Toronto
and it might present a great opportunity for this entrepreneur who is based in Canada. As
Burmese food is very similar to other Asian cuisines, this entrepreneur is thinking of opening
this restaurant in locations where Asian food is popular (aka many Asian restaurants in the
neighborhood). With the purpose in mind, finding the location to open such a restaurant is
one of the most important decisions for this entrepreneur and I am designing this project to
help him find the most suitable location.



## Business Problem :
The objective of this capstone project is to find the most suitable location for the entrepreneur
to open a new Burmese restaurant in Toronto, Canada. By using data science methods and
machine learning methods such as clustering, this project aims to provide solutions to ansIr
the business question: In Toronto, if an entrepreneur wants to open a Burmese restaurant,
where should they consider opening it?



## Data :
To solve this problem, I will need below data:
● List of neighborhoods in Toronto, Canada.
● Latitude and Longitude of these neighborhoods.
● Venue data related to Asian restaurants. This will help us find the neighborhoods that
are most suitable to open a Burmese restaurant.


## Methodology :
First, I need to get the list of neighborhoods in Toronto, Canada. This is possible by
extracting the list of neighborhoods from wikipedia page
(“ https://en.wikipedia.org/wiki/List_of_postal_codes_of_Canada:_M ”) I did the web
scraping by utilizing pandas html table scraping method as it is easier and more
convenient to pull tabular data directly from a web page into dataframe.
However, it is only a list of neighborhood names and postal codes. I will need to get their
coordinates to utilize Foursquare to pull the list of venues near these neighborhoods. To get
the coordinates, I tried using Geocoder package but it was not working so I used the csv file
provided by IBM team to match the coordinates of Toronto neighborhoods. After gathering
all these coordinates, I visualized the map of Toronto using Folium package to verify whether
these are correct coordinates.

Next, I use Foursquare API to pull the list of top 100 venues within 500 meters radius. I have
created a Foursquare developer account in order to obtain account ID and API key to pull the
data. From Foursquare, I am able to pull the names, categories, latitude and longitude of the
venues. With this data, I can also check how many unique categories that I can get from these
venues. Then, I analyze each neighborhood by grouping the rows by neighborhood and
taking the mean on the frequency of occurrence of each venue category. This is to prepare
clustering to be done later.

## Results

The results from k-means clustering show that we can categorize Toronto neighborhoods into
3 clusters based on how many Thai restaurants are in each neighborhood:
● Cluster 0: Neighborhoods with little or no Thai restaurants
● Cluster 1: Neighborhoods with no Thai restaurants
● Cluster 2: Neighborhoods with high number of Thai restaurants
