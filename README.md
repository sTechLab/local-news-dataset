# Local News Social Media Dataset
This github contains the largest dataset of local news outlets in the U.S. and their social media handles. This dataset includes a total of 10,258 news outlets. We map 7,849 of them to a location and county, 9,332 to a Facebook account and 2,908 to a Twitter account. For the outlets that have a Twitter or a Facebook account, we provide the IDs that can be used to retrieve their content from Facebook through the CrowdTangle API and from Twitter using the Twitter API V2. The FIPS county code makes it easy to retrieve data at the county-level, including census data or voter records. We constructed this dataset through expanding a seed directory of local news outlets with Facebook’s “Related Pages” feature. Based on our validation, we expect this dataset to cover approximately 60% of local news outlets in the U.S. The full methodology for how this dataset was constructed and validated, and a use case for analysis around COVID-19, is detailed in our paper “Understanding Social Local Coverage and Engagement at Scale During the COVID-19 Pandemic,” forthcoming at ICWSM.

We additionally expanded this dataset with two implicitly-constructed metrics. The first,*population reach*, is a measure of how local or national an outlet is. Based on a method first proposed by Hagar et al. (2020), we use Twitter audience location data normalized with logged state density to produce our measure of outlet population reach. Secondly, we also provide our content network neighbors metric, which is the number of other outlets that a given outlet reposts content with. This allows the identification of outlets that are part of a larger network.

This dataset can be used to analyze content of local news outlets in the U.S. at large scales. We encourage researchers to make use of Twitter and Facebook APIs to retrieve local news social media content.
