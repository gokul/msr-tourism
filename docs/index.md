# Multistakeholder Recommender Systems in Tourism

This site contains additional resources related to the research "Multistakeholder Recommender Systems in Tourism", untertaken in the Chair of Connected Mobility in the TUM Department of Informatics.

In a nutshell, we defined a set of criteria relevant in stakeholder-aware recommendation in touristic scenarios, and conducted a user study in the form of an online questionnaire to gauge end-users' views on these criteria.

More information may be found in our paper. 

### Contents

1. The Dataset
2. Constructing Recommendations

## The Dataset

The dataset used to construct the synthetic recommendations for the survey respondents is comprised of Airbnb rentals in the city of Amsterdam, The Netherlands. The following is an overview of this dataset.

Number of records prior to pre-processing: 494954.

Number of fields prior to pre-processing: 89.

| Field category | Number of fields | 
| --------------- | --------------- |
| Identifiers | 3 | 
| Scrape metadata | 3 | 
| Listing metadata | 39 |
| Host data | 16 |
| Property data | 11 | 
| Location data | 17 |
| **Total** | **89** |

#### Pre-processing

The following 3 fields weer created from existing data to better match the needs of the use-case:

- Distance from the city centre
- Price per head
- Size of the property

Once the cleaning and pre-processing steps have taken place, the following fields were left, which were then used to create artificial recommendations for each use-case dentified in section 4.1 of the paper.

| Field category | Number of fields | 
| --------------- | --------------- |
| Identifiers | 1 | 
| Scrape metadata | 0 | 
| Listing metadata | 9 + 2 new |
| Host data | 2 |
| Property data | 7 | 
| Location data | 4 + 1 new |
| **Total** | **23 + 3 new** |


## Constructing Recommendations

Synthetic recommendations were constructed for 4 cases, prioritising a different facet of data in each case.

#### No constraints

The respondents were instructed to prioritise the distance from the city centre, price per head and overall ratings first, which reflected a focus on user utility.

![Results for Case 1](/docs/images/TQ1.png|width=500px)

#### Reranking for Increased Provider Utility

In the second case, the utility gain of the providers was prioritised, by sorting the initial data by the price per square foot.

![Results for Case 1](/docs/images/TQ2.png|width=500px)

#### Reranking for Increased City Utility

Next, the utility gain of the society (city) was prioritised by eliminating the following neighbourhoods from the data, which limits tourist hotspots:

- Centrum-West
- Centrum-Oost
- Westerpark
- De Baarsjes - Oud-West
- Oud-Noord

![Results for Case 1](/docs/images/TQ3.png|width=500px)

#### Reranking for Increased System Utility

Finally, the utility gain of the system (simulated irbnb recommender system) was prioritised by sorting the data by the total number of reviews (thereby picking out frequently booked listings).

![Results for Case 1](/docs/images/TQ4.png|width=500px)


-

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/gokul/msr-tourism/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
