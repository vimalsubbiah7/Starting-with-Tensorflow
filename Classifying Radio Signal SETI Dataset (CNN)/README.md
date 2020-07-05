# SETI-Radio-Signal-Classification-Challenge
SETI Institute Code Challenge Machine Learning 4 the Search for Extra Terrestrial Intelligence (http://www.seti.org/ml4seti)
### https://github.com/setiQuest/ML4SETI

# SETI Institute Code Challenge
#### Machine Learning 4 the Search for Extra Terrestrial Intelligence (http://www.seti.org/ml4seti)

## Introduction 

The SETI Institute hosted a public hackathon and global, online code challenge from June 1, 2017 to July 31, 2017. The goal was for citizen scientists to find a robust signal classification algorithm for use in the mission to find E.T. radio communication. By framing the radio signal data as a spectrogram (a 2D visual representation), we can convert the problem into an image classification problem.  Participants built machine learning and deep learnng / AI techniques to construct highly accurate classification systems that very successfully classified the signals in our simulated data set. We'd like to thank everybody who participated. 

The Winning Team was `Effsubsee`. They posted a classification accuracy of 94.99%. In second place was `Signet`, which a classification accuracy of 94.67%!

You can read more about the neural-network architectures these teams employed:

  * [Effsubsee](https://github.com/sgrvinod/ml4seti-Effsubsee)
  * [Signet](https://github.com/sagelywizard/ml4seti)

Instructions for installing the necessary software to run these models [are found here](https://gist.github.com/gadamc/dc1f4aac3c637a7ab1c2542c85772d03). 

Additionally, two Jupyter notebooks (tested to work on IBM Data Science Experience) demonstrate these models:

  * [Effsubsee](results/effsubsee_seti_code_challenge_1stPlace.ipynb)
  * [Signet](results/signet_seti_code_challenge_2ndPlace.ipynb)



## Project Overview

Each night, using the Allen Telescope Array (ATA) in northern California, the SETI Institute scans the sky at 
various radio frequencies, observing star systems with known exoplanets, searching for faint but persistent signals. 
The current signal detection system is programmed to search only for particular kinds of signals: narrow-band 
carrier waves. However, the detection system sometimes triggers on signals that are not narrow-band signals 
(with unknown efficiency) and are also not explicitly-known radio frequency interference (RFI). 
There seems to be various categories of these kinds of events that have been observed in the past. 

Our goal is to classify these accurately in 
real-time. This may allow the signal detection system to make better observational decisions, 
increase the efficiency of the nightly scans, and allow for explicit detection of these other signal types. 

The standard approach to SETI signal detection and classification is to transform the observed radio signals, which
are time-series data, into a 
2-dimensional representation called a spectrogram. A spectrogram is a measure of the power of the signal across 
a range of frequencies, as a function of time. From this, the data acquisition software searches for narrowband signals. 
By displaying the spectogram as a 2D image, this transform the 
problem into a visual recognition problem. 

For example, here is a classic narrowband signal observered from the 
[ISEE3 explorer](https://en.wikipedia.org/wiki/International_Cometary_Explorer). These are the kinds of
signals the software is tuned to identify.

![ISEE3 Narrow Band Signal](img/isee3.png "ISEE3 Narrow Band Signal")

But things are usually never that pretty unless we're looking at a spacecraft. Here's another example: 
a mysterious squiggle observed in 2014 (the color scale is different because the power amplitude, coming out of the
page is on a log-scale). 


![Mystery Signal](img/mystery_squiggle.png "Mystery Signal")
 

Similar to the signal above, we often see various signal types that our software is not specifically 
designed to detect. These have various names like "squiggles", "pulsed", and 
"bright pixels".


We want to build classification models that are designed to find these "other" types of signals. 
We hope to utilize the expertise from the data science community and simultaneously allow a way for 
citizen scientists to get involved in research that is normally out of their reach.  We want to increase the number of large cups in the water, as [Dr. Jill Tarter](http://www.seti.org/users/jill-tarter) might [describe it](https://www.ted.com/talks/jill_tarter_s_call_to_join_the_seti_search). 



### The Code Challenge
 
The challenge is to build a classification system based on a large body of simulated (and labeled)
data that we have constructed. While our set of simulated data does not span the full range of types of signals observed at the ATA, or the complexity, it is a good starting point for building useful classification tools.  

