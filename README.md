# I310D | DATA BIAS EVALUATION OF PERSPECTIVE API

## PROJECT OVERVIEW
In this project, potential data bias was investigated through querying the Prospective API natural language processing model by Google
Jigsaw. To evaluate potential data bias in the model, two hypotheses were fromulated. Appropriate tests were constructed and executed in
a Google Colab Python environment. The discovery and json libraries were imported to complete analysis.

#### DUAL TEST EVALUATION
This project conducts two tests to investigate potential data bias in the model.

#### PERSPECTIVE API DOCUMENTATION
https://developers.perspectiveapi.com/s/?language=en_US

## DATA BIAS TESTING
### TEST 1: TOXICITY VARIANCE BETWEEN UPPERCASE AND LOWERCASE COMMENTS
#### HYPOTHESIS
It is hypothesized that the Perspective API may detect higher toxicity scores in uppercase comments when compared to lowercase comments, despite their content. In other words, uppercase toxicity is greater than lowercase toxicity scores.
#### METHOD
To examine whether uppercase toxicity is greater than lowercase toxicity, a simple comparison test is constructed. Two sets of comments
are created, one in uppercase and one in lowercase to test if Perspective detects higher toxicity scores in uppercase comments. Each set
contains 12 comments for testing. Then generate toxicity scores for uppercase and lowercase comments, taking the mean of each category
and comparing their magnitude.
#### RESULTS
Uppercase Comments Results: [0.026499467, 0.11129999, 0.027913637, 0.147767, 0.027206551, 0.13041082, 0.081625134,
0.042657252, 0.13908891, 0.081625134, 0.19314334, 0.1100022]

Lowercase Comments Results: [0.019477395, 0.10609736, 0.0201057, 0.13561769, 0.021903414, 0.09525062, 0.049831573,
0.048099842, 0.10175867, 0.04834723, 0.19029272, 0.150481221

Average Toxicity for Uppercase Comments: 0.09326995291666668

Average Toxicity for Lowercase Comments: 0.08227195283333333

Uppercase comments have a higher average toxicity.
