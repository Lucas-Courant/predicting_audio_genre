# Predicting Genre From Audio Signal

## Contents:
- [Problem Statement](#Problem-Statement)
- [Executive Summary](#Executive-Summary)
- [Data Description](#Data-Description)
- [Data Dictionary](#Data-Dictionary)
- [Modeling](#Modeling)
- [Conclusions and Next Steps](#Conclusions-and-Next-Steps)

## Problem Statement
This project aims to predict the genre of a song based on audio signal data in order to better understand what features account for human perception of sound. It will serve as a foundation for future machine learning models that can make predictions on how a human might be percieving an audio signal.

If I can predict genre well based on audio features I can better understand what features make audio the way it does. Genre is a very subjective and human construct. If I can make a computer understand audio in a way that is similar to how humans understand audio I will be closer to building other tools that do analysis on audio. This project can then serve myself and others as a basis for building tools that take audio and make predictions on how a human might be percieving that audio.

## Executive Summary
I began by using classical machine learning models to predict genre using the precomputed audio feature statistics provided in the free music archive. Of these audio features the mel frequency cepstral coefficients (mfccs) provided the highest level of accuracy when predicting genre. The best performing model was logistic regression. Performing logistic regression on the mfccs yielded an accuracy of 52.2% which is a large improvement over the baseline of 12.5%. Based on these results I began to build neural networks using the mfccs to predict genre. Currently my highest performing model is a convolutional neural network that is trained on images of the mfcc spectrograms of the songs. These spectrograms were generated using the librosa library. This neural network in it's current state is only ~35% accurate on unseen data. I am working on tuning it and also creating a multiinput neural network.

## Limitations
The biggest limitation for this project is that genre is a subjective concept. Two people can listen to the same song and disagree on what it's genre is. This means that any machine learning models I build will inheret the perceptions of genre of whoever encoded the data I work with. With this particular data the genre for each track was encoded by the artists themselves. 

## Data Description
### Precomputed Data
Data was pulled from the [free music archive](https://github.com/mdeff/fma) github. For the audio files I pulled the 'small' subset and worked with that. This dataset came with summary statistics on audio features that were created by the authors of the free music archive.

- Audio Features
 - chroma energy normalized chroma
 - constant q transform chroma
 - short time fourier transform chroma
 - mel frequency cepstral coefficients
 - root mean squared energy
 - spectral bandwidth
 - spectral centroids
 - spectral rolloff
 - tonnetz
 - zero crossing rate

For each of these audio features the following statistics were provided

- Statistics
 - kurtosis
 - maximum value
 - mean
 - median
 - minimum value
 - skew
 - standard deviation
 

### Feature Extraction from mp3 Files
Because the mfccs gave the highest accuracy I decided to focus on extracting these first from the mp3 files. I extracted them both as they come from the librosa method and as a .png file with pixel values. Genre was taken from the metadata that was provided.

## Modeling
Numerous models were tried. Logistic regression performed the best by far on the summary statistics provided. The features I extracted were so many that a neural network was the only model that made sense.

## Next Steps
I am currently working and building a multi input neural network that can accept multiple audio feature matrices as inputs.
