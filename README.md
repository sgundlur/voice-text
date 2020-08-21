
<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![PR](https://camo.githubusercontent.com/f96261621753dacf526590825b84f87ccb1db0e6/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5052732d77656c636f6d652d627269676874677265656e2e7376673f7374796c653d666c6174)](pullreq-url)
[![MIT License][license-shield]][license-url]


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="#">
    <img src="https://i.imgur.com/f1TqviT.jpeg" alt="Logo">
  </a>

  <h3 align="center">MevonAI - Speech Emotion Recognition</h3>

  <p align="center">
    Identify the emotion of multiple speakers in a Audio Segment 
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [License](#license)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project

<img src="https://i.imgur.com/xaY8Izs.png" alt="Logo">

The main aim of the project is to Identify the emotion of multiple speakers in a call audio as a application for customer satisfaction feedback in call centres.


### Built With

* [Python 2.7](https://www.python.org/download/releases/2.7/) (Python3 dosen't support one of the project Dependency)
* [Flask](https://flask.palletsprojects.com/en/1.1.x/)
* [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
* [Tensorflow-Keras](https://www.tensorflow.org/guide/keras/functional)
* [librosa](https://github.com/librosa/librosa)

## Here's how:

#### Speaker Diarization
* Speaker diarisation (or diarization) is the process of partitioning an input audio stream into homogeneous segments according to the speaker identity. It can enhance the readability of an automatic speech transcription  by structuring the audio stream into speaker turns and, when used together with speaker recognition systems, by providing the speaker’s true identity. It is used to answer the question "who spoke when?" Speaker diarisation is a combination of speaker segmentation and speaker clustering. The first aims at finding speaker change points in an audio stream. The second aims at grouping together speech segments on the basis of speaker characteristics.

<img src="https://github.com/taylorlu/Speaker-Diarization/raw/master/resources/diarization.gif" alt="Logo">


#### Feature Extraction
* When we do Speech Recognition tasks, MFCCs is the state-of-the-art feature since it was invented in the 1980s.This shape determines what sound comes out. If we can determine the shape accurately, this should give us an accurate representation of the phoneme being produced. The shape of the vocal tract manifests itself in the envelope of the short time power spectrum, and the job of MFCCs is to accurately represent this envelope. 

<img src="https://i.imgur.com/UANHXoU.png" alt="Logo">
The Above Image represents the audio Waveform , the below image shows the converted MFCC Output on which we will Run our CNN Model.


#### CNN Model Architecture
* Use Convolutional Neural Network to recognize emotion on the MFCCs
```python
model_ravdess = Sequential()
kernel = 5
model_ravdess.add(Conv2D(32, 5,strides=2,padding='same',
                 input_shape=(13,216,1)))
model_ravdess.add(Activation('relu'))
model_ravdess.add(BatchNormalization())


model_ravdess.add(Conv2D(64, 5,strides=2,padding='same',))
model_ravdess.add(Activation('relu'))
model_ravdess.add(BatchNormalization())

model_ravdess.add(Conv2D(64, 5,strides=2,padding='same',))
model_ravdess.add(Activation('relu'))
model_ravdess.add(BatchNormalization())

model_ravdess.add(Flatten())


model_ravdess.add(Dense(7))
model_ravdess.add(Activation('softmax'))

opt = keras.optimizers.Adam(lr=0.001, beta_1=0.9, beta_2=0.999, epsilon=None, decay=0.0, amsgrad=False)
```





<!-- USAGE EXAMPLES -->
## Usage

[Download RAVDESS Emotional speech audio dataset ](https://www.kaggle.com/uwrfkaggler/ravdess-emotional-speech-audio)

* 2DConvolution(.py) file is used to training the model.

* Server(.py) will start the web server on Default Port



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [Speech Emotion Recognition from Saaket Agashe's Github](https://github.com/saa1605/speech-emotion-recognition)
* [Speech Emotion Recognition with CNN](https://towardsdatascience.com/speech-emotion-recognition-with-convolution-neural-network-1e6bb7130ce3)
* [MFCCs Tutorial](http://practicalcryptography.com/miscellaneous/machine-learning/guide-mel-frequency-cepstral-coefficients-mfccs/)
* [UIS-RNN Fully Supervised Speaker Diarization](https://github.com/google/uis-rnn)
* [uis-rnn and speaker embedding by vgg-speaker-recognition by taylorlu](https://github.com/taylorlu/Speaker-Diarization)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=flat-square
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=flat-square
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=flat-square
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=flat-square
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=flat-square
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/screenshot.png
