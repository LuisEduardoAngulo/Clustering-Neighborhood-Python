# Where is the most appropriate place to set a new gym?: The case of Madrid, city.

## Background 

Due to the increasing healthcare and fitness concern to avoid or reduce problems like obesity, sedentarism, depression, and anxiety, among others. Many industries and companies have been developing products or services to address these problems. A clear example is the growing number of gyms that have been established in recent years. 

Madrid is not far from this reality, and many different types of gyms like TRX, Crossfit, and Traditional have been opened. Every establishment has its target and objectives, in most cases, they overlap in those. Exposing a lack of preparation or planning regarding the business start-up decisions that were not made based on data.

Regarding the above, the main goal of this exercise is to provide the best location to establish a gym aimed at people with middle-high income in Madrid. Using data about the neighborhoods like average income, average age, unemployment, and similar venues placed, among others. 

## Data description

### Sources

To address and achieve the main objective of this exercise it was used the following data sources:

- **Open data portal of the _Ayuntamiento de Madrid_**. Here, was found information regarding average income, average age, and unemployment rate, among others, per neighborhood. The information is available in CSV format. 
- **Foursquare API.** Here, was found the most common venues of given a Borough or neighborhood of Madrid.  

### Data wrangling

In this phase, the data downloaded from the "Ayuntamiento de Madrid" were in three files with CSV formats. Some transformations were needed due to the type of variable that Python read. The relevant features came as objects, and I needed them as integers or floats. Also, the irrelevant features were dropped. Later, the three files were merged into a single one to ease the analysis and modeling. Finally, through the FourSquare API, I retrieved the data related to the latitude and longitude of each neighborhood of Madrid. 

## Methodology

Once the data was clean and ready to use, some summary statistics and visualization were conducted to get a better understanding of it. For instance:

Summary statistics

![Summary statistics](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/estad%C3%ADsticas.png) 

Features distributions

![Features distributions](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/distribuciones.png) 

Later, I used the FOLIUM library to create a map of Madrid with neighborhoods superimposed on top of it. Before this, the latitude and longitude of Madrid were retrieved through the geocoder function. All this process was done following the example of the hands-on material.

Madrid Map

![Madrid Map](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/Madrid.png) 

The exercise continued with the analysis and exploration of each neighborhood. Using the FourSquare API venues placed on each one of the before-mentioned were recovered. The limit of places to be reached was set to 100, and the radius to 500. A total of 3680 venues and 264 uniques venues´ categories were identified.

Considering that the main interest of this exercise was to identify potential spots to place a gym, I performed a feature engineering step and grouped some columns (venues) related to gyms to avoid duplicity or sparse information. Subsequently, the analysis continued like the hands-on exercise, namely: grouping the retrieved venues by neighborhood and taking the mean of the frequency of occurrence of each category. And then it was observed each neighborhood along with the top 5 most common venues. Finally, a new data set was created, as a previous step to the clustering, where the 10 most common places for each neighborhood were exhibited.

The mentioned table looked as follows:

![table](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/tabla.png) 

## Results

As mentioned before, my principal interest was to identify potential spots in Madrid to place a gym. So, I created a new data frame with the venues that were related to gyms or similars, I also included the information about average income, average age, and unemployment rate per neighborhood. The final dataset that was cluster was the following:

![cluster table](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/cluster_table.png) 

At first, the K-means algorithm was deployed with 5 clusters. Later I tried with 3, 4, and 7 clusters. But, 5 achieved more stables results. Meaning that the neighborhoods dispersed better among the clusters, avoiding agglomerations in only one of them. 

The map of Madrid with the clustered neighborhoods looks as follows, where each color depicts one cluster.

![cluster](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/cluster.png)

## Discusion

As can be seen in the below image, I recommend the neighborhoods in clusters 2 and 5 as potentials spots to establish a new gym (details in the Jupyter notebook). 

In both, there is a market niche that is not being served. For example, cluster 2 does not have any gym aimed at the general public. It only has a university gym. Besides, the population that inhabits this neighborhood is high-income and with low unemployment rates, so they have the resources to pay for exclusive services. A similar situation is observed in cluster 5. Although there is a greater presence of gyms here, it is a high-income segment, where value-added services could be offered with the objective of attracting these potential clients.

![cluster_results](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/Images/resultados.png)

## Conclusion

As mentioned in the introduction to this report, the number of gyms and similar options available for the customers has been growing over the years. However, the results of this exercise showed that there is still a market niche to be exploited in the city of Madrid. Highlighting, the importance of making business decisions based on data.


