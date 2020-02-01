# Audio Classification using CNN Neural Network
This is a set of experiments to understand the minimal network that is effective for identifying and classifying audio signals. 
The goal of this set of experiments is to understand the features that are mapped by hidden layers in the case of audio signals with the end goal of designing a minimal network that is effective for a given signal.  The goal is **not** to generate the highest performing network for an input at all; instead, I am preferring simpler structures that let me see the features in hidden layers better. 
A minimal network would be preferable in situations where the network would be deployed to EDGE or embedded applications, as well as being more efficient (needing much less power to train and deploy).   Adequate performance at low cost, vs. peak performance at high cost. I also used one output class at a time to keep the inner layer activations simpler to visualize; I would retrain the network from scratch for every different signal.
This experiment was first done as part of a university class, but I am continuing to expand on it as time permits. 

## Data Set
This experiment uses audio samples from the Google AudioSet dataset (https://research.google.com/audioset/).   The data in the AudioSet is available as preprocessed Tensorflow recordsets in MFCC (Mel Frequency Cepstral Coefficient) format.  These sets are already normalized and ready to use, but they only take audio samples in 1-second intervals so a single file contains an array of 128 MFCC samples across the frequency range at 6 - 10 1-second intervals (most samples are 10 seconds long but a few are shorter).   That limits their use for sounds that are mainly distinguished by a quick pattern of frequencies over time (i.e. a bird song). 
As an alternative, the raw samples can be downloaded from YouTube directly and processed manually. 
The first passes at this experiment used the preprocessed recordset, and were done for the university class.  The results of that are posted.  I have also downloaded the raw audio for additional experimentation and I intend to use this repository to store that as it becomes available.

## File Arrangement
The experiments with pre-processed audio records are in three Jupyter notebooks: Initial Audioset Data Model, Small Audioset Data Model, and Tiny Audioset Data model.  The differences are in the number of layers and depth of each layer.  The Small notebook contains hidden layer visualizations for each CNN layer. 
I also included the report that was part of the class and explains the first phase of the experiment and conclusions from that phase.
