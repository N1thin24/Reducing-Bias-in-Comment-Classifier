# Reducing-Bias-in-Comment-Classifier

The project here was to pick and fine-tune a model so that it performs well in classifying comments as toxic or not, but the evaluation criteria was based on it's accuracy towards the lowest scoring discriminatory category. In this dataset, we had comments which targeted specific categories such as ['black', 'male', 'female'.... etc]. However, majority of the comments were non-toxic and further, some categories had very few datapoints.

It can be quite a challenge to score a great validation accuracy on each of these classes when the distribution looks something like this. Further, pre-trained models are already biased in this challenge based on their previous trainings. For instance, the sentence 'I am a black man' will be classified as toxic just because of inherited biases of the pre-trained model.
![image](https://github.com/N1thin24/Reducing-Bias-in-Comment-Classifier/assets/107985125/0cd818ca-ea29-4a95-aa6d-59b7a092b487)

After extensive and exhaustive data analysis, we chose the DistilBERT transformer model for this problem, and had to use NLPAugmentation techniques such as paraphrasing to create more datapoints for some of the minority categories.
