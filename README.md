# Artificial Rodrigo -- A Music Generator turned Natural Disaster Predictor

### Introduction
Initially we had set out to answer the question, "Can a generative model create good sounding keyboard solos?" Though it sounds complicated, this is really a pretty simple task if you treat music as a sequence of notes. Then the task becomes, "can you predict the next note based on the previous notes?" In which case you have the model feed its generated predictions into itself and you are able to create some sort of musical sequence. The set-up and prep work for this project was going successfully, but we encountered an issue in training our model that caused us to pivot Artificial Rodrigo to a different NLP task, where we knew we could succeed.

Artificial Rodrigo would take on the case of tweet classification, and try predicting whether a tweet is about a real natural disaster or not. The source for this inspiration can be found at this [Kaggle competition](https://www.kaggle.com/c/nlp-getting-started). The format of this project will discuss the parts of each project that we have done, the combination of which is Artificial Rodrigo. And who knows, one day maybe we will build a monolithic NLP model that will be able to handle both tasks.

### Collecting the Data
The data collection for the music generation was pretty simple. We paid a musician on fiver to record an hour of midi solos for us to use. The data processing for a midi file has relatively few pieces of information as shown here:

![midi image](/images/midi.png)

There was a small issue with our input data such that the model did not like have different tempos, so we had to adjust the data points where the tempo was different so that the model could accurately predict. Other than that there were no issues with the data, which shows that even though we paid to get out data, it paid to have clean data.

The data collection for the disaster prediction kaggle competition was even simpler, as the competition provided both a training and test set already for us to use. There were few if any null values in this dataset and it came clean and ready to use which was extremely nice.


### EDA(s)


### Model(s)


### Results