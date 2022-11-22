Lesson 3: The types of data that can be used as input
=====================================================

One of the most fundamental parts training a ML or DL model is to have
the correct data. There are various ways in which the data can be
processed before training the model, but first it is necessary to
understand what types of data is used for training these models. This is
important because even if you are using a pretrained model and you don’t
expect to do any fine tuning on it, you need to understand what types of
data it requires to make predictions on. The way data is divided can be
slightly different depending on the literature you read, but for the
sake of clarify, the following descriptions are the easiest to
understand.

Text
~~~~

Text data are just strings which could be as short as a word or as long
as an entire document. The data is usually converted into a numeric form
and depending on the type model you are building, this numeric form can
differ. In recent years, the most common way to work with text data is
by using word embeddings together with transformers. Although, we will
cover this in more detail later, the main characteristic of embeddings
is that they convert the text data into numeric by using complex word or
sentence embeddings. This basically replaces all the characters in a
text with arrays of numbers which represent those characters’ meanings.
Having the meaning represented in numbers means that the words and
sentences can be measured and compared with other words and sentences.

Image
~~~~~

Images are comprised of pixels and pixels are made up of colors. A
single pixel can be represented as 3 numbers in a list. The 3 number
represent 3 primary colors red, green and blue, so are thus named RGB
colors. Each of the three colors are represented by a number between 0
and 255 so that the color black is represented as [0 0 0] and white as
[255 255 255]. This is just for 1 pixel and each image is made up of
several hundred or thousand pixels. The size of an image will tell you
the number of pixels e.g. a size of (400, 200) means that the width is
400 pixels and the height is 200 pixels. This equals to a total of 80000
pixels with each one being represented by the 3 numbers.

Why is it important to know this? It’s important because a deep learning
model can tell you nothing about an image until you convert it to a
numeric form i.e. the pixel representations. Furthermore, the images
need to be the same size, so you’ll see in models that work with images,
the images themselves are all resized to the same size. When they are
the same size, they can be converted to pixel values and passed as input
data into the model. The smaller an image is, the faster the training
will be - which is logical since there will be less pixels. However,
less pixels also means less information, so it’s worth considering speed
of training and performance of the model.

Video
~~~~~

In a similar way that images are converted to pixels, videos are
converted to frames (images) when they are being preprocessed as input
for a machine learning model. After they have been converted to images,
the same process is followed as with the previous image explanations.
However there is another factor that needs to be taken into
consideration - frames per second (fps). Each video has a fps number,
the average being 24fps. This means that each second of video is
comprised of 24 frames (images), so a video that is 1 minute long with
24fps has 1440 total frames. This needs to be considered when building a
machine learning model that works with video data.

You have to decide if you have the sufficient hardware capacity to
process the video files - especially if you are working with long
videos. A technique that can can used to reduce the number of frames you
are working with is to extract a frame at specific intervals e.g. every
second. Using only one frame per second will reduce 1440 frames to 60
frames for a 1-minute video. This will give you less data to work with,
but will speed up processing. The purpose of the project will determine
if this is a plausible compromise, however you can also figure it out
through experimentation.

Audio
~~~~~

Audio files are usually convert to arrays after which they can be used
as input to machine learning models. The most common format is ``.wav``
files, so if you have ``.mp3`` or other files formats, it’s best to
convert them to ``.wav`` files. From the ``.wav`` file format, you can
open the file as an numpy object using the ``scipy.io.wavfile`` or
``wave`` library. This will produce an object that is composed of two
parts: the audio sample rate and the audio’s amplitude data.

The sample rate refers to the amount of data that makes up 1 second of
audio. The usual value for the sample rate of audio files is 44100Hz or
more commonly written as 44.1kHz. The higher this value is the better
quality the sounds will be and the lower it is, the worse quality it
will be. The amplitude data’s format depends on the type of audio you
are working with: mono or stereo. Mono audio is when the audio data is
passed through 1 channel. A channel is when sound from one point to
another e.g. from your phone to you headphones or from your TV to a
speaker. A speaker produces audio in 1 channel and a speaker can only
received audio via 1 channel. When you are using two speakers then there
are two channels and this is called stereo audio. A digital file isn’t
constrained by the traditional hardware such as speakers, so it can
contain multiple channels of audio. Why this is important to know is
that when you are working with the amplitude data, you will either get a
single array of numbers or a two-dimensional array of numbers (in the
case of stereo audio).

This data can be used in it’s numeric form as input to machine learning
models, but it can also be converted to images. Two common images are
waveforms and spectrograms. A waveform is a graph that represents the
amplitude data on the y-axis and the sample rate on the x-axis. Sample
rate can also be converted into time, so that you can have seconds or
minutes on the x-axis. Spectrograms are visualizations of the
frequencies of the amplitude data (also known as signal) which provide a
lot more details than waveforms. Spectrograms look more like images than
charts (as waveforms do) because they provide a lot more information.
They are also used in the medical field for diagnosis and research, as
well as in linguistics for visualizing speech production. Converting
audio to waveforms and/or spectrograms opens up many possibilities
because now you can leverage the power of models that work with image
data to approach the tasks from a different angle.

Time series
~~~~~~~~~~~

These types of data are sequential and is characterized by data being
collected at different intervals. Some examples of this could include
weather data, stock market data, YouTube video views over time,
population growth data, etc. Anything that has to do with recording data
at fixed intervals is called time series data. Depending on what other
type of data you have, the way in which you would use time series data
varies, but generally these types of data are used to find patterns over
time or to forecast future events such as stock market movements.

Tabular data
~~~~~~~~~~~~

As the name suggests these types of data are recorded in tables where
the values in some columns are used to predict the value in a specific
column. For example, on `Kaggle <https://www.kaggle.com/>`__ there are
two famous datasets that are used for machine learning projects:
`housing
prices <https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques/data>`__
and the `Titanic
dataset <https://www.kaggle.com/competitions/titanic/data>`__. In the
housing prices dataset you are trying to predict the price of a house
based on whatever you may deem relevant in the tabular data. Similar to
the, in the Titanic dataset, you need to predict whether a passenger
lived or died from the Titanic disaster based on the details of their
personal trip. Tabular data contains columns which can have different
data types, have different correlations to each other and have a
completely different range of values. It’s therefore, the job of the
user to determine what is relevant to predict the value that needs to be
predicted.