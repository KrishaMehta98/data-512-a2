# data-512-a2

## About The Project

The goal of this assignment is to explore the concept of bias through data on Wikipedia articles - specifically, articles on political figures from a variety of countries. We combine a dataset of Wikipedia articles with a dataset of country populations, and use a machine learning service called ORES to estimate the quality of each article.

There are several steps involved in this project:
- Data Collection
   1. [Politicians by Country from the English-language Wikipedia](https://figshare.com/articles/dataset/Untitled_Item/5513449)
   2. [World Population Dataset](https://docs.google.com/spreadsheets/d/1CFJO2zna2No5KqNm9rPK5PCACoXKzb-nycJFhV689Iw/edit#gid=283125346)
- Clean the Data
- Collect Article Quality Predictions
   1. We use the [ORES](https://github.com/wikimedia/ores) model to make predictions for each article in the dataset
4. Combine the 2 datasets
5. Analyze and transform the data
6. Results

The following is the structure of the directory and files present:
```

├── README.md
├── data
    ├── source
        ├── WPDS_2020_data.csv
        ├── page_data.csv
│   ├── final
        ├── revids_missing.csv
        ├── wikipedia-politician-article-quality.csv
        ├── wp_wpds_countries-no_match.csv
        ├── wp_wpds_politicians_by_country.csv
└── code
│    └── hcds-a2-bias.ipynb

```

## Dataset

Once the dataset is cleaned and the predictions are obtained, we merge the 2 datasets and output a [CSV](https://github.com/sharma-apoorv/data-512-a2/blob/master/data/processed/wp_wpds_politicians_by_country.csv) file with the following schema:


| Column Name             | Description                                     |
|-------------------------|-------------------------------------------------|
| country                    | This is the country which the article belongs to |
| article_name                   | The name/title of the article  |
| revision_id     | A unique number that identifies the article |
| article_quality_est. | The ORES prediction of the quality of the article |
| population  | The population of the country |

## Results

From the analysis, we attempt to answer the following 6 questions:
1. Top 10 countries by coverage: 10 highest-ranked countries in terms of number of politician articles as a proportion of country population
2. Bottom 10 countries by coverage: 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population
3. Top 10 countries by relative quality: 10 highest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality
4. Bottom 10 countries by relative quality: 10 lowest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality
5. Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the total count of politician articles from countries in each region as a proportion of total regional population
6. Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the relative proportion of politician articles from countries in each region that are of GA and FA-quality

## Usage

The repo can be cloned using the following command:
```
git clone https://github.com/KrishaMehta98/data-512-a2.git
```

## License

Distributed under the MIT License. See `LICENSE.md` for more information.
