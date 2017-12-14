Finding Parkinson’s with CNN classifier
===================


As a continuation for my previous explorations in neurological de-generative disease classification, I found another interesting dataset from [PhysioNet]( https://www.physionet.org/pn3/gaitpdb/)
 with 93 patients with Parkinson’s disease and a control group of 73 healthy subjects (with 296 samples). The subjects walked for 2 minutes with 8 sensors under their foot and the force-recordings were samples at 100Hz. Based on the published paper in the [European Journal of Neuroscience]( http://www.interactivemetronome.com/imw/IMpublic/Research/Temporal%20Processing/Gait/Research_GAIT%20MATE_dual%20tasking,%20gait%20rhythmicity,%20and%20PD.pdf), the patients with Parkinson’s are more likely to struggle maintaining consistent gait when subjected to cognitive load. In this case, 25 of the subjects subtract numbers while walking. For more details, have a look at Physionet page.

I wanted to see what kind of performance I would get using a convolution neural network (CNN) to classify the subjects. Instead of feeding time series of data to a RNN, I thought build “images” out of the time series and the 16 sensors. In the notebook, I am feeding matrices of 16x240 to 2-dimensional CNN, building 24 convolution filters of size 7x7.

The data originated from 3 different studies, noted (Ga, Ju and Si) followed by the subject and a walk number 01 for normal walk, 10 for dual tasking. The train/test validation is done per file basis. With these settings, the per image classification accuracy is around 85%, majority voting on the entire sequence, 88% recall, 93% F1-score.

-Antti

