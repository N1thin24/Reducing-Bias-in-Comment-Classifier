# Reducing-Bias-in-Comment-Classifier

The project here was to pick and fine-tune a model so that it performs well in classifying comments as toxic or not, but the evaluation criteria was based on it's accuracy towards the lowest scoring discriminatory category. In this dataset, we had comments which targeted specific categories such as ['black', 'male', 'female'.... etc]. However, majority of the comments were non-toxic and further, some categories had very few datapoints.

It can be quite a challenge to score a great validation accuracy on each of these classes when the distribution looks something like this. Further, pre-trained models are already biased in this challenge based on their previous trainings. For instance, the sentence 'I am a black man' will be classified as toxic just because of inherited biases of the pre-trained model.
![image](https://github.com/N1thin24/Reducing-Bias-in-Comment-Classifier/assets/107985125/0cd818ca-ea29-4a95-aa6d-59b7a092b487)

**Data Pre-processing**

We removed all special characters and changed words such as 'don't' to 'do not' and finally we fixed all irregular spaces.
We initially tried to remove all stopwords to help improve the computational efficiency but we later found out that BERT performs better with these context specific words and hence removed it from the final implementation
We also had to use NLPAugmentation techniques such as paraphrasing to create more datapoints for some of the minority categories.
Finally, we used the tokenizer to convert our text strings into tokens to feed into the model.


After extensive and exhaustive data analysis, we chose the DistilBERT transformer model for this problem.
We chose BCEwithLogitsLoss because it was seamless to implement with DistilBert and is a very good choice for Binary Classification problems.
The Model seemed to perform best at max of 1 or 2 epochs and would always overfit after.
As for the learning rate, we were able to try a variety of learning rates ranging from 2e-5 to 5e-5. We found that somewhere between 2.5 to 3 was giving us the best results.
