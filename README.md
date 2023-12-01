# Celebrity_recognition_project

## Introduction
In the era of rapidly advancing technology, facial recognition has emerged as a powerful tool, but its potential for bias has raised serious concerns. A study by the National Institute of Standards and Technology (NIST) revealed alarming disparities in the accuracy of facial recognition algorithms across different ethnicities. Notably, Amazon's facial recognition model, Rekognition, was absent from the NIST evaluation, leading to skepticism about its performance. This blog delves into the nuanced issue of racial bias in AI, focusing on AWS's Recognition and its ability to distinguish Asian celebrities compared to their Western counterparts.

## The Racial Bias Conundrum

The NIST study uncovered a troubling pattern – facial recognition algorithms exhibited significantly higher error rates for African-American and Asian faces in one-to-one matching scenarios. Astonishingly, some algorithms misidentified faces of these ethnicities 10 to 100 times more frequently than Caucasian faces. Amazon's absence from the NIST evaluation leaves a critical gap in understanding the accuracy of its facial recognition model.

## The ACLU's Earlier Assessment

Adding to the concerns, an assessment by the American Civil Liberties Union (ACLU) revealed the flaws in Rekognition's face-matching capabilities. In a distressing revelation, 28 members of Congress, predominantly people of color, were incorrectly matched with mugshot images. This highlights the real-world implications of biased facial recognition technology and underscores the urgency of addressing these issues (source: https://sitn.hms.harvard.edu/flash/2020/racial-discrimination-in-face-recognition-technology/).

## Training Set Limitations

Facial recognition AI's bias may stem from the limitations of its training set. With Amazon being an American company, the possibility arises that AWS's recognition model was trained on a dataset where Asian faces are a minority. This geographical bias in training data can significantly impact the algorithm's performance and accuracy.

## The Developer's Location Matters

The NIST's findings also shed light on the impact of a developer's location on the algorithm's accuracy. Algorithms developed in China exhibited lower false positive rates on East Asian faces, emphasizing the role of the developer's location as a proxy for the race demographics in the training data. This revelation, dating back to 2011, underscores the importance of considering the geographical origin of developers in reducing demographic differentials (source: NIST).

## Exploring AWS's Recognition Bias

### Experiment Part 1

To investigate AWS's Recognition bias further, we designed an experiment focusing on the recognition of Chinese celebrities compared to their Western counterparts.

#### Hypothesis
We hypothesized that AWS's celebrity recognition would exhibit a lower accuracy rate on top Chinese celebrities compared to top Western celebrities.

#### Experiment Design
We selected six pairs of Chinese celebrity lookalikes, both male and female, and gathered five images of each individual. These images were then fed into AWS's celebrity recognition model, as well as the compare faces model for additional analysis within each doppelganger pair.

#### Preliminary Results

The initial findings are intriguing. Out of the twelve celebrities tested, only three were correctly identified. Moreover, several celebrities were not merely unrecognized but were misidentified, with some Chinese celebrities even being confused with Japanese counterparts. Surprisingly, AWS's Recognition had no difficulty differentiating between members of each doppelganger pair.

#### Conclusion
As we navigate the complex landscape of facial recognition technology, it is evident that biases persist, raising ethical and societal concerns. Our preliminary experiment sheds light on potential shortcomings in AWS's Recognition, particularly in accurately identifying Asian celebrities. Addressing these issues is crucial to ensure fairness and equity in the deployment of facial recognition technology. Stay tuned for the next part of our experiment, where we delve deeper into the intricacies of bias in AWS's Recognition.

### Experiment Part 2: Testing Celebrity Recognition Using Forbes Lists

#### Data Collection and Focus Narrowing

In the second phase of our experiment, we sought to delve deeper into the celebrity recognition capabilities of AWS. To refine our focus, we decided to use Forbes lists, relying on the 2017 celebrity rankings from both Forbes China and Forbes US.

#### Forbes China's Celebrity Top 100

Forbes China annually publishes a celebrity top 100 list, ranking Chinese celebrities based on factors like income, search engine hits, and media exposure. To ensure an apples-to-apples comparison, we chose to examine the Forbes 2017 top 100 lists for both China and the US. Recognizing that the Forbes US list predominantly features Western celebrities, we carefully curated the data. Specifically, we excluded foreign celebrities and music groups, amounting to 20 items. Additionally, to maintain parity, we removed the bottom 20 celebrities from the China list.

#### Data Processing
To facilitate our analysis, we converted the curated lists into CSV files, labeling them 'Chinese Celebs' and 'Western Celebs.' Utilizing the Jupyter notebook environment, we employed pandas to read each CSV file, extracting the names of celebrities from both lists.

#### Image Collection and Quality Assurance

Our next step involved downloading 50 images of each celebrity's face using the simple_image_download Python library. These images were then transferred to our S3 bucket for efficient storage. To ensure the quality of our dataset, we developed a function leveraging AWS Rekognition's recognize_faces API. This function evaluated key factors such as yaw, sunglasses, closed eyes, and resolution, ultimately retaining 10 high-quality images per celebrity.

#### AWS Rekognition Analysis

With our curated dataset in place, we proceeded to feed the images of each celebrity's face into AWS's celebrity recognition model. The objective was to gauge the model's overall accuracy in identifying Chinese celebrities vs Western celebrities.

#### Comparative Analysis
The final stage involved a comprehensive comparison of the model's accuracy on Chinese and Western celebrities. By assessing the results, we aimed to draw insights into potential discrepancies and biases in AWS's celebrity recognition capabilities.

This is the link to [our analysis]([https://github.com/sophiaxxiao/Celebrity_recognition_project/blob/main/Result%20and%20Analysis.ipynb](https://github.com/sophiaxxiao/Celebrity_recognition_project/blob/main/Results%20and%20Analysis.ipynb)).
 

#### Conclusion
As we navigate the intricacies of this experiment, the use of Forbes lists adds a valuable dimension to our investigation. By focusing on influential celebrities from both China and the US, we anticipate gaining deeper insights into how AWS's recognition model performs across different cultural and ethnic contexts. Stay tuned for the results and implications uncovered in the subsequent analysis of this experiment.




