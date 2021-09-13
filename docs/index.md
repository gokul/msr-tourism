# Multistakeholder Recommender Systems in Tourism

This site contains additional resources related to the research "Multistakeholder Recommender Systems in Tourism", untertaken in the Chair of Connected Mobility in the TUM Department of Informatics.

In this research, we defined a set of criteria relevant in stakeholder-aware recommendation in touristic scenarios, and conducted a user study in the form of an online questionnaire to gauge end-users' views on these criteria.

More information may be found in our paper. For questions and comments, please contact the authors at `gokul.balakrishnan AT tum.de`

\- Gokul Balakrishnan and Wolfgang Wörndl, Technical University of Munich, Germany.

### Contents

1. The Dataset
2. Constructing Recommendations
3. Opinion Survey
4. Results

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

Synthetic recommendations were constructed for 4 cases, prioritising a different facet of data in each case. Respondents were asked to rate the applicability of each recommendation based on how helpful/unhelpful they found it (1-5 scale, 1 being most satisfied and 5 being least satisfied).

#### Case 1: No Constraints

The respondents were instructed to prioritise the distance from the city centre, price per head and overall ratings first, which reflected a focus on user utility.

![Recommendations for Case 1](/images/TQ1.png)

#### Case 2: Reranking for Increased Provider Utility

In the second case, the utility gain of the providers was prioritised, by sorting the initial data by the price per square foot.

![Recommendations for Case 2](/images/TQ2.png)

#### Case 3: Reranking for Increased City Utility

Next, the utility gain of the society (city) was prioritised by eliminating the following neighbourhoods from the data, which limits tourist hotspots:

- Centrum-West
- Centrum-Oost
- Westerpark
- De Baarsjes - Oud-West
- Oud-Noord

![Recommendations for Case 3](/images/TQ3.png)

#### Case 4: Reranking for Increased System Utility

Finally, the utility gain of the system (simulated irbnb recommender system) was prioritised by sorting the data by the total number of reviews (thereby picking out frequently booked listings).

![Recommendations for Case 4](/images/TQ4.png)

## Opinion Survey

The following is a list of questions posed to the respondents of the survey in addition to rating the reranked recommendations.

#### Nature of rerankings

* The first recommendation you saw before was the best fit for your needs.
* The second set was reranked to the rental providers' benefit.
* The third set was made to fit the needs of the City of Amsterdam (avoiding tourist hotspots).
* The fourth set was done to show you the most frequented AirBnBs.

**If you had known the reasons for these rerankings, would it have affected your choices in any way?**

#### User Experience 

This section presented the respondents with yes/no questions, as fllows:

- Have you ever considered a computer-based recommender system when planning travel (e.g. TripAdvisor)?
- Have you ever considered a computer-based system when looking for MULTI-PARTICIPANT travel (e.g. group travel) recommendations ?
- Do you trust travel recommender systems to give accurate results in a group travel scenario?
- Are you aware that in many recommender systems, interest of other parties (e.g. hotel companies) affect the recommendations displayed as "Top Results" or "Recommended"?

#### Users' Views on Multistakeholder Recommender Systems

In this section, users were asked to rate the statements on a 1-5 scale, with 1 being full agreement and 5 being full disagreement.

- I prefer to use interactive recommender systems for tourism use-cases rather than other sources (friends/family, adverts)
- As a user, I accept that sometimes other factors will cause the recommender system to show me results that don't perfectly match my requirements.
- As a user, I believe that a recommender system should prioritise *my* needs over other parties such as rental providers etc.
- I believe that a recommender system should tell me when interests of other parties are taken into account when giving me choices.
- I am OK with the data I provide for recommendation being used for improving the recommendations of other users like me, as well as benefit other parties.

#### Non-functional influences

Similar to the previous section, respondents were offered a 1-5 scale to rate their agreement/disagreement with the following statements:

- I want recommender systems to take care of local restrictions when planning travel (e.g. if local law prohibits stays longer than 5 days, such options must not be shown).
- I am comfortable with tourist recommender systems taking care of changes coming from seasonal factors (like price drops), rather than do it manually myself.
- I want tourist recommender systems to warn me when there are unforeseen events happening in my destination (e.g. pandemic, war).

## Results

This section contains the results from the user study. For a full discourse on the nature of the results, please see our paper.

### Reranking Airbnb Listings
#### Case 1: No Constraints
Results

![Results for Case 1](/images/res_case1.png)

Word cloud

![Word Cloud for Case 1](/images/WC1.png)
#### Case 2: Reranking for Increased Provider Utility
Results

![Results for Case 2](/images/res_case2.png)

Word cloud

![Word Cloud for Case 2](/images/WC2.png)
#### Case 3: Reranking for Increased City Utility
Results

![Results for Case 3](/images/res_case3.png)

Word cloud

![Word Cloud for Case 3](/images/WC3.png)
#### Case 4: Reranking for Increased System Utility
Results

![Results for Case 4](/images/res_case4.png)

Word cloud

![Word Cloud for Case 4](/images/WC4.png)

#### Summary: Reranking Recommendations

![Overall Results for Reranking](/images/res_full.png)

### Opinion Survey
#### User Experience 
Results

![Results for User Experience](/images/res_exp.png)
#### Users' Views on Multistakeholder Recommender Systems


| Question (abridged) | Agreement | Neutral | Disagreement | 
| --------------- | --------------- |--------------- |--------------- |
| I prefer to use recommender systems for tourism. | 58 |  26 | 17 |
| Sometimes my results can be affected by other factors. | 74 | 18 | 9 |
| Recommender systems should prioritise my needs. | 76 | 13 | 12 |
| I prefer to use recommender sysI should know when other parties’ interests are affecting my results. | 82 | 14 | 5 |
| My data can be used to benefit other parties. | 84 | 9 | 9 |


#### Non-functional influences

![Non-functional](/images/res_nonfunc.png)