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
contains 12 comments for testing. Then toxicity scores are generated for uppercase and lowercase comments. The mean of each category
is calculated and their magnitudes are compared.
#### OUTPUT
Uppercase Comments Results: [0.026499467, 0.11129999, 0.027913637, 0.147767, 0.027206551, 0.13041082, 0.081625134,
0.042657252, 0.13908891, 0.081625134, 0.19314334, 0.1100022]

Lowercase Comments Results: [0.019477395, 0.10609736, 0.0201057, 0.13561769, 0.021903414, 0.09525062, 0.049831573,
0.048099842, 0.10175867, 0.04834723, 0.19029272, 0.150481221

Average Toxicity for Uppercase Comments: 0.09326995291666668

Average Toxicity for Lowercase Comments: 0.08227195283333333

Uppercase comments have a higher average toxicity.
#### CONCLUSION
As uppercase comments have a higher average toxicity score than lowercase comments (0.093 vs. 0.082), the hypothesis is correct.

### TEST 2: TOXICITY VARIANCE BETWEEN ANTI-MALE AND ANTI-FEMALE COMMENTS
#### HYPOTHESIS
It is hypothesized that Perspective API's performance may vary based on the target gender of a comment, indicating potential gender bias in the model. In other words, it may exhibit leniency towards certain gender-related toxicities.
#### METHOD
To examine whether there is variance in Perspective API's toxicity score between the genders, a simple comparison test is performed. Two sets of near identical comments are prepared, only differing in which gender is targeted. Each set contains 12 comments for testing. Then toxicity scores are generated for anti-male and anti-female comments. The mean of each category is calculated and their magnitudes are compared.
#### OUTPUT
Toxicity Scores for Anti-Male Comments: [0.509388, 0.24282593, 0.4014846, 0.85173553, 0.46982017, 0.7570315, 0.5140397, 0.5140397, 0.8115627, 0.36095104, 0.46982017, 0.52272606]

Toxicity Scores for Anti-Female Comments: [0.6289369, 0.4014846, 0.50789946, 0.9029226, 0.5885171, 0.8460273, 0.65996873, 0.64447093, 0.85333383, 0.39987978, 0.57271194, 0.6407703]

Average Toxicity for Anti-Male Comments: 0.5354520916666666

Average Toxicity for Anti-Female Comments: 0.6372436225000001

Anti-female comments have a higher average toxicity.
#### CONCLUSION
The Perspective API model generates different toxicity scores for anti-male and anti-female comments with identical content, with anti-female comments receiving a higher average toxicity score. Therefore, the hypothesis is correct.

## RESULTS
### TEST 1: TOXICITY VARIANCE BETWEEN UPPERCASE AND LOWERCASE COMMENTS
The results of Test 1 indicated that there is a noticeable difference in toxicity scores between uppercase and lowercase comments. Uppercase comments tended to receive higher toxicity scores compared to their lowercase counterparts, even when the content was similar. This suggests that the model might be sensitive to the use of uppercase letters, potentially interpreting them as more aggressive or confrontational. However, not all uppercase comments were aggressive.
### TEST 2: TOXICITY VARIANCE BETWEEN ANTI-MALE AND ANTI-FEMALE COMMENTS
In Test 2, the results showed variations in toxicity scores for comments expressing anti-male and anti-female sentiments. Despite their identical contents, anti-female comments received a higher average toxicity than anti-male comments. This could be indicative of bias in the model, where there is more leniency towards anti-male comments than anti-female comments.

## REFLECTION
The findings prompt reflection on potential biases that might exist in the model. Intuitively, biases could stem from imbalances in the training data, reflecting societal biases and stereotypes. Additionally, the model may struggle with nuanced language and context, leading to variations in toxicity scores.

From Test 1, the discovery that the model assigns higher toxicity scores to uppercase comments compared to their lowercase counterparts suggests the Perspective API might be biased against certain formatting; this observation raises questions about the underlying mechanisms the model employs to interpret and assess the tone of text. One hypothesis is that the use of uppercase letters might be interpreted as more confrontational or aggressive, leading to elevated toxicity scores. This finding underscores the importance of understanding how language nuances, such as capitalization, impact the performance of natural language processing models. Based on the findings that anti-female comments receive a higher average toxicity score from Test 2, the model may be biased in its assessment of anti-male and anti-female comments. This bias could possibly be explained by societal stereotypes surrounding the genders. Natural language processing models can unintentionally learn and perpetuate societal stereotypes present in the training data, and possibly could contribute to the concept that anti-male speech is not as dangerous/toxic as anti-female speech. If the training data contains biased language or reflects existing stereotypes, the model may reproduce these biases in its predictions.

However, drawing concrete conclusions about biases requires further investigation and a more extensive dataset. Natural language processing is an evolving field, and future studies could investigate potential biases in other areas.





