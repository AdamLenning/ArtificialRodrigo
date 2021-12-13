# Artificial Rodrigo -- A Music Generator turned Natural Disaster Predictor

## Introduction
Initially we had set out to answer the question, "Can a generative model create good sounding keyboard solos?" Though it sounds complicated, this is really a pretty simple task if you treat music as a sequence of notes. Then the task becomes, "can you predict the next note based on the previous notes?" In which case you have the model feed its generated predictions into itself and you are able to create some sort of musical sequence. The set-up and prep work for this project was going successfully, but we encountered an issue in training our model that caused us to pivot Artificial Rodrigo to a different NLP task, where we knew we could succeed.

Artificial Rodrigo would take on the case of tweet classification, and try predicting whether a tweet is about a real natural disaster or not. The source for this inspiration can be found at this [Kaggle competition](https://www.kaggle.com/c/nlp-getting-started). The format of this project will discuss the parts of each project that we have done, the combination of which is Artificial Rodrigo. And who knows, one day maybe we will build a monolithic NLP model that will be able to handle both tasks.

## Collecting the Data
The data collection for the music generation was pretty simple. We paid a musician on fiver to record an hour of midi solos for us to use. The data processing for a midi file has relatively few pieces of information as shown here:

![midi data image](/images/midi.png)

There was a small issue with our input data such that the model did not like have different tempos, so we had to adjust the data points where the tempo was different so that the model could accurately predict. Other than that there were no issues with the data, which shows that even though we paid to get out data, it paid to have clean data.

The data collection for the disaster prediction kaggle competition was even simpler, as the competition provided both a training and test set already for us to use. There were few if any null values in this dataset and it came clean and ready to use which was extremely nice.


## EDA(s)

### Music Generation
More EDA was performed on the music than on the tweets. For that reason we can see a couple of interesting features about our soloist on fiver.

![pitch plot](/images/pitch.png)

From this we can see that his pitches (or notes) centered around the middle of the pitch range, or near the center of the keyboard. Translating this into notes we can see:

![note distribution](/images/notes.png)

The distribution of these notes likely indicates that he was playing in E major (where there are 4 sharps, on F#, C#, G# and D# indicated by the higher frequency of these notes as opposed to their natural counter-parts), though perhaps a classifier to predict key signature would be an interesting project for future work. 

The means and standard deviations of the key features is presented here but the information is less relevant in this context:

![means and standard devs](/images/features.png)

Lastly, one of the most interesting features that we can use for predictions is the bigrams of the pitches. Which two notes are most commonly played.

![note bigrams](/images/bigrams.png)

### Tweet Analysis
Taking a look at the twitter data, we can see that about 42% of the tweets are actually about a natural disaster, which is good for our model because we don't have skewed classes.

Also looking at the rules we made for experimentation the following features have strong correlation to our target prediction.

>[('I_LOWERCASE', 0.1724137931034483, 116), ('PROFANITY', 0.21893491124260356, 169), ('GONNA', 0.23076923076923078, 39), ('COMMA_COMPOUND_SENTENCE', 0.24064171122994651, 187), ('UPPERCASE_SENTENCE_START', 0.266384778012685, 473), ('EN_CONTRACTION_SPELLING', 0.23148148148148148, 108)]

Exploring a little bit more we can see some of the locations that are most common for natural disasters are:

>[('Worldwide', 0.631578947368421, 19), ('Washington, DC', 0.7142857142857143, 21), ('London', 0.35555555555555557, 45), ('Mumbai', 0.8636363636363636, 22), ('Los Angeles, CA', 0.3076923076923077, 26), ('Kenya', 0.25, 20), ('USA', 0.6442307692307693, 104), ('Nigeria', 0.7857142857142857, 28), ('India', 0.8333333333333334, 24), ('New York', 0.22535211267605634, 71)]


## Model(s)


## Results