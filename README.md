# Local News Social Media Dataset
This github contains the largest dataset of local news outlets in the U.S. and their social media handles. This dataset includes a total of 10,257 news outlets. We map 7,859 of them to a location and county, 9,231 to a Facebook account and 5,645 to a Twitter account. For the outlets that have a Twitter or a Facebook account, we provide the IDs that can be used to retrieve their content from Facebook through the CrowdTangle API and from Twitter using the Twitter API V2. The FIPS county code makes it easy to retrieve data at the county-level, including census data or voter records. We constructed this dataset through expanding a seed directory of local news outlets with Facebook’s “Related Pages” feature. Based on our validation, we expect this dataset to cover approximately 60% of local news outlets in the U.S.

We additionally expanded this dataset with two implicitly-constructed metrics. The first, *population reach*, is a measure of how local or national an outlet is. Based on a method first proposed by Hagar et al. (2020), we use Twitter audience location data normalized with logged state density to produce our measure of outlet population reach. Secondly, we also provide our *content network neighbors* metric, which is the number of other outlets that a given outlet reposts content with. This allows the identification of outlets that are part of a larger network.

This dataset can be used to analyze content of local news outlets in the U.S. at large scales. We encourage researchers to make use of Twitter and Facebook APIs to retrieve local news social media content.

# Interact with the Data
For an interactive look at the dataset, please go to our [interactive website](https://share.streamlit.io/stechlab/local-news-website/main/app.py?page=Explore+The+Dataset).

# Methodology
The full methodology for how this dataset was constructed and validated, and a use case for analysis around COVID-19, is detailed in our original paper [Understanding Local News Social Coverage and Engagement at Scale during the COVID-19 Pandemic](https://mariannealq.com/wp-content/uploads/2022/05/Local_News_ICWSM_Camera_Ready.pdf).

# What do the columns mean?
| Field                   | Description                                                                                                                                                                                                   | N Unique Values |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------|
| OutletId                | Unique local news outlet ID of this dataset (from 0 to 10256)                                                                                                                                                 | 10257           |
| Name                    | Name of the local news outlet                                                                                                                                                                                 | 10257           |
| WebsiteUrl              | Website URL of the local news outlet                                                                                                                                                                          | 9935            |
| State                   | Official United States Postal Service (USPS) Code for the States and District of Columbia, listed as “non-US” if outlet location is not in the US and “NA” if location not found                              | 8648            |
| City                    | Name of the city where the outlet is located, listed as “non-US” if outlet location is not in the US and “NA” if location not found                                                                           | 8648            |
| StateId                 | 2-digit Federal Information Processing Series (FIPS) Codes for States and Congressional Districts (Census Bureau geographic summary level 040)                                                                | 7859            |
| CountyId                | 3-digit FIPS Codes for Counties and County Equivalent Entities (Census Bureau geographic summary level 050)                                                                                                   | 7859            |
| CountyFIPS              | 5-digit FIPS Code with StateId and CountyId combined                                                                                                                                                          | 7859            |
| TwitterId               | Unique identifier of Twitter account                                                                                                                                                                          | 5645            |
| TwitterHandle           | Twitter screen name, username, handle, or alias that the user identifies themselves with, unique but subject to change                                                                                        | 5645            |
| TwitterFollowersCount   | Number of Twitter followers at the time of TwitterRetrievedDate                                                                                                                                               | 5645            |
| TwitterDescription      | Text of this user's profile description, also known as bio                                                                                                                                                    | 5323            |
| TwitterRetrievedDate    | Datetime of Twitter fields retrieval (from 2020-10-19 to 2022-05-24)                                                                                                                                          | 5645            |
| FacebookId              | Unique identifier of Facebook account, also known as platformId on CrowdTangle (Facebook's API). Any Facebook Page can be accessed through the url www.facebook.com/FacebookId                                                                                                                                | 9231            |
| FacebookSubscriberCount | Number of followers the Facebook account has                                                                                                                                                                  | 9231            |
| FacebookCategories      | List of Facebook page categories, including Newspaper, News Media Website, Media/News Company, Broadcasting Media Production Company, or Magazine.                                                            | 6900            |
| FacebookPageDescription | Description of the Facebook page                                                                                                                                                                              | 9189            |
| FacebookAdditionalInfo  | Additional information of the Facebook page                                                                                                                                                                   | 4082            |
| FacebookRetrievedDate   | Date of Facebook fields retrieval (from 2020-09-29 to 2020-10-19)                                                                                                                                             | 9231            |
| PopulationReach         | A metric we calculated based on the geographic dispersion of its Twitter followers, available if a Twitter account is found                                                                                   | 2780            |
| ContentNetworkNeighbors | A metric we calculated based on how many other Facebook pages the outlet is sharing posts with, available if a Facebook page is found and has posted at least once between January 1st 2020 and July 1st 2021 | 8751            |

# Contact
If there's anything you'd like to discuss, if there are any issues with the dataset, or if you have any questions, please contact Marianne Aubin Le Quere on [Twitter](https://twitter.com/marianneaubin). We're also always looking for additional collaborators on projects -- feel free to reach out!

# Citation
To cite this dataset, please refer to the original paper:
> [Understanding Local News Social Coverage and Engagement at Scale during the COVID-19 Pandemic](https://mariannealq.com/wp-content/uploads/2022/05/Local_News_ICWSM_Camera_Ready.pdf), Marianne Aubin Le Quéré, Ting-Wei Chiang, Mor Naaman, Sixteenth International AAAI Conference on Web and Social Media, 2022.

