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

In this phase, the data downloaded from the "Ayuntamiento de Madrid" were in three files with CSV formats. Some transformations were needed due to the type of variable that Python read. The relevant features came as objects, and we needed them as integers or floats. Also, the irrelevant features were dropped. Later, the three files were merged into a single one to ease the analysis and modeling. Finally, through the FourSquare API, we retrieved the data related to the latitude and longitude of each neighborhood of Madrid. 

## Methodology

Once the data was clean and ready to use, some summary statistics and visualization were conducted to get a better understanding of it. For instance:

Summary statistics
![Summary statistics](https://github.com/LuisEduardoAngulo/Coursera_Capstone/blob/main/Exercise%202%20-%20Location%20in%20Madrid/estad%C3%ADsticas.png) 

