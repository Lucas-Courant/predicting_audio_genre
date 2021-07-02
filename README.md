# Predicting Genre From Audio Signal

## Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Description](#Data-Description)
- [Data Dictionary](#Data-Dictionary)
- [Modeling](#Modeling)
- [Conclusions and Next Steps](#Conclusions-and-Next-Steps)

## Problem Statement
If I can predict genre well based on audio features I can better understand what features make audio the way it does. Genre is a very subjective and human construct. If I can make a computer understand audio in a way that is similar to how humans understand audio I will be closer to building other tools that do analysis on audio. This project can then serve myself and others as a basis for building tools that take audio and make predictions on how a human might be percieving that audio.

## Executive Summary


## Data Description
Data was pulled from the [free music archive](https://github.com/mdeff/fma) github. For the audio files I pulled the 'small' subset and worked with that. Ultimately I extracted the mel frequency cepstral coefficients for each file and tried to predict the genre. Genre was taken from the metadata that was provided. One of the limitation is that assesment of genre is subjective. Many songs don't fit fully into one genre and two people might predict the same song as being of different genres. To get around this I used the most broad definitions of genre provided. Still though the models I build will inherit the perception of genre of whoever encoded this data.
(want two subsections here, one for summary statistics provided and one describing my own extracted features)

## Data Dictionary

## Modeling
Numerous models were tried. Logistic regression performed the best by far on the summary statistics provided. The features I extracted were so many that a neural network was the only model that made sense.

## Conclusions and Next Steps
Figure out how to make the neural network better. Extract other audio components besides mfccs. Make a model that can listen to a song and update it's prediction of genre as it listens.
