CodeRefinery AI course for researchers
======================================

Artificial intelligence (AI) seems to be everywhere in our modern
society, but people are still a little hesitant to get involved because
it may appear to be an overwhelming field of study. As with any field of
study, this is the case if you are delving deep and trying to understand
everything at its foundation. However, on the surface level AI is more
accessible than ever before. With the increase in interest, the
expansion of computing power and the relatively low costs, it’s possible
for researchers who aren’t AI experts to take advantage of all that this
field has to offer. There is a misconception in our current society that
you need to be an expert in mathematics and have petabytes of data to
accomplish anything worthwhile using AI, but with the tireless work of
the community at large, this is no longer the case. The AI community has
been created and fostered in recent years which has lead to the
development of libraries that make it increasingly easier to build and
deploy machine learning (ML) and deep learning (DL) models - which are
subsets of AI and the types of models that are built by practitioners.
There is still a slight gap between the use of AI in a research capacity
and the practical AI. Using AI in a research capacity is usually
centered around competitions for state-of-the-art results. These
competitions involve building models and testing new architecture in
order to achieve the best scores on a standardized test. These
architectures, their specifications and their results are then published
in various different journals across different disciplines. From these
journal articles, practitioners in the private and public sector
reproduce these results and create production-ready AI solutions.

This entire process works well, but the biggest problem is that the
ability to reproduce the results in journal articles usually requires a
substantially good understanding of the theories and practices of AI.
This creates an environment where non-experts rarely have the skills to
be able to produce state-of-the-art solutions without the need for
assistance from the community. This creates a bottleneck in providing
the tools to researchers to be able to use state-of-the-art solutions in
their research without the need for long courses in AI theory and
practice. This has led to frameworks such as
`Tensorflow <https://www.tensorflow.org/>`__ and
`PyTorch <https://pytorch.org/>`__; libraries such as
`SpaCy <https://spacy.io/>`__, `FastAI <https://www.fast.ai/>`__ and
`Huggingface Transformers <https://huggingface.co/>`__; and hundreds of
online guides and courses to make using AI easier. Even with these
solutions to simplify the process, there is still a steep learning curve
to apply these in your own research. It is for that reason that this
course has been developed i.e. make the process as easy, but as flexible
as possible. This course will be based on the FastAI course which can be
found
`here <https://www.youtube.com/watch?v=8SF_h3xF3cE&list=PLfYUBJiXbdtSvpQjSnJJ_PmDQB_VyT5iU>`__
which is a library that is built on PyTorch i.e. it’s a higher level
abstraction. As well as the The Huggingface Transformers library which
provides a repository of pretrained models that are extremely useful in
creating new models.

The basic layout of this course is focused around creating the model
first based on a certain relevant task. Assessing the model’s
performance on the measured metrics, but also on human evaluation
i.e. domain-expert evaluation. Creating solutions for practical research
tasks where developing the solutions are a means to an end provides a
different set of requirements than achieving the best scores. The
fundamental motivation behind this idea is that we need domain experts
using AI tools instead of AI experts trying to solve domain specific
problems. So the most important goal is how can you, as a domain expert,
get a model ready to use in the shortest amount of time. Using this
model to assess the results it produces can give you insight into where
the model’s strengths lie and where it needs improvement. This is a much
better assessment of the model than just looking at metrics. The plan
moving forward is to build the model using the FastAI library, create
customizations where needed using PyTorch and rely on the model’s
metrics, but more importantly your domain knowledge to assess the
performance.

What is AI?
===========

There isn’t an exact definition of artificial intelligence (AI) because
the community at large doesn’t agree upon a specific definition.
However, we will define it for this course in two ways: broadly and
specifically. The broad definition of AI is a non-biological system that
can react to the environment in which it functions. This doesn’t help
much with the practical aspect of using AI, so we need a more specific
and practical definition. AI is a collection of algorithms each of which
solves a specific task. These algorithms are fit to data to find the
most relevant configuration for a specific problem. The algorithms are
referred to as machine learning (ML) models and there is also a subset
of ML models that are more complex which are called deep learning (DL)
models. The structure of DL models are based on the way the human brain
works and they generally require a lot of data to create meaningful
algorithms. Click `here <https://www.youtube.com/watch?v=ad79nYk2keg>`__
to view a video explanation of the definition of AI.

The roadmap
===========

**What** are you doing in this course?
--------------------------------------

In the broad sense, this course is going to teach you to solve problems
using AI. Identifying problems that can be solved by AI tools and
assessing whether these problems are appropriate for AI tools to solve.
Sometimes, it may seem like a problem requires an AI solution, but in
many cases it does not. You can still solve most problems without the
need for AI, so it’s important to understand when to use it and when you
don’t need it.

**Why** are you doing that?
---------------------------

As has been mentioned before, AI is a complex field, so the barrier for
entry is high. This has often prevented domain experts from using the
tools because they didn’t have the time, resources or interest to learn
those complexities. Since AI tools are becoming easier to develop, we
are now in a position where only with a small amount of time can you, as
a researcher, build AI tools that can substantially help your own
research.

**How** are you going to do that?
---------------------------------

We are going to do this by building models based on real world problems
and real world data. There is a gap between problems created for
exemplary purposes and problems you face in the real world. This course
is designed to strip away all the unnecessary information, go to the
fundamental principles and explain the ways in which to reach a
solution. The solutions in real life are often not perfect and there are
usually a lot of problems that crop up when you least expect them.

Getting started
===============

Determine what you want to achieve and apply the four steps of computational thinking
-------------------------------------------------------------------------------------

There are four steps to computational thinking which is a process that
helps you solve problems in as systematic way as possible. Below is a
summary of those points, but consider —insert course link— if you want
to understand it in more detail.

Decomposition
~~~~~~~~~~~~~

This first step is to determine what the goal is that you are trying to
achieve i.e. what is the problem you are trying to solve. Break that
problem down into smaller steps each of which has a single desired
outcome.

Pattern recognition
~~~~~~~~~~~~~~~~~~~

Look for patterns in the problems that you have decomposed which
indicate if you could apply previous solutions to this new problem or
group problems together to solve them quicker.

Abstraction
~~~~~~~~~~~

Rank order the decomposed steps into levels of priority and remove any
unnecessary information from the problem in order to focus on only the
key information that will help in solving it.

Algorithmic thinking
~~~~~~~~~~~~~~~~~~~~

Convert each small problem into actionable steps as simply as possible
that can be followed by a human or a computer.

What kind of data do you (for supervised learning)?
---------------------------------------------------

Once you have figured out what problem are you going to solve, you need
to look at the data you have or you need to collect the data you need.
The data needs to have two main characteristics: features and labels. An
easy why to understand this is with the following sentence > I want to
determine **labels** from the **features**

Here are some examples: > I want to determine **the cost of a house**
from the **number of bedrooms, the size of the garden and location**

   I want to determine if a photo is **a dog or cat** from **photos of
   dogs and cats**

..

   I want to determine **a hate speech** from a list of **hate speech
   sentences and normal sentences**

   I want to determine **movie genres** from **a movie poster**

The above examples are for your data when training the model - which we
will go into detail in the next few sections. As you can see, the model
is going to use the features of as many examples as possible to predict
the labels. Let’s take the housing example and break it down further.
You need to have four pieces of information organized in rows. Each row
has four columns: 1) cost of the house, 2) number of bedrooms, 3) size
of the garden and 4) location of the house. All this information is
currently known, we are not trying to predict anything with this
information. This is data that will be passed into the model and the
model will figure out the patterns in the data which determine the
price.

So, what is the point of the model if we have all the information
already? The point of using information have already is to calibrate the
model so that when you feed new data into it, it can make a prediction
about the price. We use the features and the labels to train the model,
but when we use the model to predict something, we only need the
features. In the housing example, once you have trained a model with
that data, you can find a house that isn’t in the training data and pass
those features (number of bedrooms, the size of the garden and the
location) to find out what the likely cost is of the house. This applies
to all the above examples and what’s important to note from this
explanation is not the details, but rather the formula: > I want to
determine **labels** from the **features**

The type of deep learning problem you are solving
-------------------------------------------------

The problems above are different types of deep learning problems because
they are predicting different types of labels. Once you have determined
what your labels are then you can determine what type of deep learning
solution you need to provide.

Housing example
~~~~~~~~~~~~~~~

You are predicting a number because a price is a number.

Dog and cat example
~~~~~~~~~~~~~~~~~~~

You are predicting one of two options i.e. a dog or a cat. This may seem
simple, but there is a little detail here that might have gone
unnoticed, so let’s think logically here. We have a model that can
predict if a photo is of a dog or a cat. What happens if you show it a
photo of something else? Well, it’s going to predict either dog or cat.
So this model is good if you are trying to split photos of dogs and
cats, but not so good if you want to predict whether a photo is a dog or
cat.

Hate speech example
~~~~~~~~~~~~~~~~~~~

This is a good example of a binary classification problem which means
you could answer the question with true or false i.e. is the sentence
hate speech? False.

Movie genres example
~~~~~~~~~~~~~~~~~~~~

This one may seem similar to the dog and cat example, but it’s slightly
different. We show the model a movie poster and it tells us the genre of
the movie. But, let’s think about this logically again - what if the
movie can be described as two genres e.g. romantic comedy? This is not a
problem, but we need to know that we are potentially predicting multiple
labels for a single poster. This is called multilabel classification.

What do you do with the data now?
---------------------------------

Now that you have potential solutions to your problem and you have your
data, you need to make a decision whether or not a deep learning model
is appropriate for your problem and/or data. The general categorization
for deep learning models are three different levels of customization:
out-of-the-box models, pretrained models and building a model from
scratch.

Out-of-the-box models
~~~~~~~~~~~~~~~~~~~~~

These are models that have been built by someone else and can be used
without the need to train anything. In theory these models would be
perfect for someone who doesn’t know a lot about this field, but there
are many downsides to these models. Usually they are nearly impossible
to find for your specific tasks. Deep learning models are designed to
solve a specific task, so unless you have the exact same task to solve
as someone else, the chances of finding a deep learning model that
perfectly solves your problem is very low. You can, however, use these
models nonetheless, but the results won’t be as good as you they could
be. An exception to this is going to a company that build models and
paying for a model to be built. This will provide you with the ideal
solution, but it will be very expensive and you will be buying a
product, so you won’t learn anything from the process.

Pretrained models
~~~~~~~~~~~~~~~~~

Pretrained models are part of a specific type of deep learning called
“transfer learning”. The easiest explanation of this is using a model
trained for a general task on a task that it wasn’t trained on by fine
tuning it. For example, if you have a model that can detect objects in
photographs, you can fine tune that model by making it specifically
detect different types of dog breeds. What it will do is use the
information it has already learned (detecting the objects) as the
foundation to make the specific task (detecting dog breeds) easier to do
with less data required. To illustrate this concept further, you can
think of pretrained models as vacuum cleaners. A vacuum cleaner is a
device that has a motor, a bag and a long pipe. The function of the
vacuum cleaner is to suck up dust from the floor (general task).
However, you can also add different extras to the nozzle if you have
different areas to clean (specific task) such as a thin extension for
cleaning in small spaces, a brush extension for cleaning carpets, and
various others. You don’t need to get a new vacuum cleaner each time you
have a different area to clean, you only need to change the extra piece
on the nozzle.

In line with this analogy, when you use a pretrained model, the
equivalent of changing the extra piece is called “fine tuning” the
model. Although it’s a bit more complicated then simple changing the
piece on the nozzle, the concept is the same. You still need data for
your specific task and a plan on developing the code to fine tune the
model. This is a very good way to get state-of-the-art results in a
short amount of time with limited data. You are essentially using the
power of the base model, so the heavy lifting has been done for you. It
is important to note, that pretrained models are trained for different
general tasks, so you still need to find a pretrained model that is in
the domain of what you are doing.

Training a model from scratch
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The most customizable option for deep learning models is training a
model from scratch. This is the best way to get the most specific
results for your problem, but it’s also the method that is the the most
difficult. This is due to the fact that you need a lot more data than
when you fine tune a model and you need to build everything from the
ground up. Although, it shares many similarities with fine tuning a
model with the biggest exception is that you aren’t leveraging the work
done by a pretrained model. Since there are so many people working on
deep learning projects today, there are plenty of pretrained models
available, but people using train from scratch when there is a new paper
published on a novel solution. In these cases, people will try to
replicate the results from the paper, so they will have to train models
from scratch. However, in most practical cases, it is usually sufficient
to use pretrained models and fine tune them to specific tasks. If you
need to train a model from scratch, the best way to do that is to find
an academic article that has the type of model you are looking for.
Usually they will have a code repository linked which you can use as a
blueprint to train your own model based on that. It’s always good to
start with some idea notion that the model has been proven to work,
otherwise you are taking a stab in the dark - unless you are an expert
in the field and you’re confident about your abilities.

What is the best choice
~~~~~~~~~~~~~~~~~~~~~~~

Choosing which of these options is the best solution depends on the
specific problem that you need to solve, so there is not ideal solution.
However, a pretrained model is usually a good choice because there are
plenty to choose from, they don’t cost anything to use (except GPU
costs) and they are customizable enough to produce good results for
novel problems. The main focus of this course will be how to leverage
the power of pretrained models, but we will also cover the other methods
to get a good understanding of how they can be used as well.

The types of data that can be used as input
===========================================

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

Using out-of-the-box models
===========================

The easiest type of AI solution is an out-of-the-box model which can be
used as is and doesn’t require any further training.
`SpaCy <https://spacy.io/>`__ is a good example of this for natural
language processing because it is a library that provides different
tools for processing language data, but it also has support for
`Huggingface Transformers <https://huggingface.co/>`__ which means you
can mix and match different models depending on your specific task.
These are great solutions for general tasks or to create a baseline from
which you can measure the performance improvements of your own trained
models. Since SpaCy is a library there is a lot of support for it, a
forum dedicated to customer questions and also comprehensive
documentation. However, this is a best case scenario situation because
most state-of-the-art models do not have a robust documentation base or
huge corporate support and those that do are usually not free to use.

Models out-of-the-box solutions require some configuration to get them
working. If you take a look at the `Huggingface
models <https://huggingface.co/models>`__, there are various different
types of models available. Some of these models are well documented and
others have no documentation at all. When using these models, there are
a few general guidelines that you can use to understand how they work.
These guidelines are similar to what we have spoken about previously in
this course, so it shouldn’t be that new to you. The first goal should
be to get the model running in its default state. Usually when
developers publish a model, they will include an example of how to use
it. Replicate that example on your local machine or on a virtual machine
in the cloud (such as `uCloud <https://cloud.sdu.dk/app/login>`__) and
make sure that it works. The problem with not doing this is that if you
jump in with your own data right at the beginning and it doesn’t work
then you can’t be sure whether it’s the model that has problems or your
own data. Getting the example to work is a sure way to make sure all the
default configurations work correctly and that your coding environment
is correctly set up for that model.

In cases where there aren’t any examples provided with the model
repository, you can search the name of the model online to find external
articles that might have used the model as an example. Good places to
look for these articles are `Medium <https://medium.com/>`__, `Towards
Data Science <https://towardsdatascience.com/>`__, `Analystic
Vidhya <https://www.analyticsvidhya.com/blog/?utm_source=feed>`__, etc.
Sometimes there are also people who create YouTube videos walking
through the setup of a particular model. Wherever you find the
information, you need to first replicate it and then you can use it on
your own data. If you still cannot find any examples, then read through
the source code and look for ways in which you can make predictions or
inferences with the model. If the main repository is on Github or
Huggingface then you can also look through the issues tabs to find out
if other people are asking the developers for examples. If you still
don’t get much success with that, then you can find contact details for
the developers and reach out to them directly asking them how you can
use the model on your own data.

Models that can usually be used out of the box are usually models that
are designed for broad general purpose tasks that don’t need specific
data to train them. Language models are some examples of this: audio
transcription, automatic translation, inference, coreference resolution,
etc. These models are usually very large and require a lot of time and
hardware to train, so they are often used as is. However, they can also
be fine tuned which is the topic of the next section.

Fine tuning pretrained models
=============================

In cases where using an out-of-the-box model won’t be sufficient for
your specific problem, you need to fine tune a model on your own data.
The concept of fine tuning is quite simple, but doing it in practice can
be really simple or it can be a little tricky. Similar to using
out-of-the-box models, it all depends on what type of documentation is
available to explain how to use the models. As for the concept of fine
tuning, the basic idea is that you are using a base model that has been
trained for a general task as your foundation. You then train the last
layer on your specific data. This process leverages the information the
model has from its pretraining, so that you can get state-of-the-art
results even if you have very little data. The process of fine tuning is
called transfer learning because you are using a model which has been
trained on pne task to perform predictions on a different task. This has
proven to be very powerful because of the fact that you can use very
little data to achieve really good results.

The process of fine tuning a model start of similar to using a model
out-of-the-box, with the main difference being that you will train the
model further before doing predictions. You, therefore, need to convert
your data into the same form that the model was trained on. If you are
using a model that has been well documented, it should explain in the
repository how to convert the data and in some cases there are scripts
in the repository that preprocess the data for you. If you are having
trouble finding out how to fine tune the model then follow the steps in
the previous section (using out-of-the-box models) to look for
documentation or examples that explain how to do it. You might be
wondering why there isn’t just explanations of how to fine tune these
models in this course. There are examples of some models, but for the
most part, models are being trained and published on a daily basis, so
it’s not practically possible to keep up with all them. The best way to
get around this issue is an explanation of a strategy to find out how to
fine tune them. After all the developers know the details of their own
models, so they are in the best position to explain how to use them.
This also prevents problems that may arise with updates to the models or
changes that the developers make because learning from an outdated
example could result in the fine tuning not working at all.

Practical example 1 - fine tuning a resnet model for emotion detection
----------------------------------------------------------------------

An interesting field of study has always been facial recognition in
which you can identify people using an image of their face. In a
similar, but more generic way, we can also do emotion detection which
involves detecting the emotion on someone’s face from an image. Video
can be done too, but it would essentially be the same process as images,
only you would divide the video into frames (see the explanation of
video data under the **the types of data that can be used as input**
section). When thinking about this problem, we first need to understand
what we are trying to do. If we think about how we as humans detect
emotion on someone else’s face, we usually match an expression with a
label in our head e.g. happy, sad, angry, etc. However, because humans
are very complex organisms, we are able to adapt very quickly and use
our surroundings as context. For example, if we have an image of a
person, we can ask someone if they are happy, angry or sad. This is a
simple answer except if they are neither of the options. In that case,
we can say that the person doesn’t look like any of those options or
maybe we can say they look more like a fourth option e.g. disgusted.
This is because we can use contextual and previous knowledge to
understand the reasoning behind the task.

A machine learning model cannot do this, so the way these models work is
a little different. You need to train the model on a collection of
images and corresponding labels. The labels you train the machine
learning model on are the only labels it knows how to predict i.e. if
you give it 3 labels (happy, sad and angry) then it will predict every
image you pass as input into 1 of those categories. It will try match it
to the closest among those three labels. It is therefore important to
understand that in the case of emotion detection, it is more accurately
described as emotion detection from a list of predefined emotions. You
won’t get a “neither” category or a “disgusted” category if you don’t
clearly have that as a label with photos in the dataset of that emotion.
In this practical exercise, we are going to use 6 emotions: happy, sad,
surprised, angry, confused and disgusted. You can use whatever you like,
just as long as you have images that correspond to the labels.

   An interesting question that you can think about is why we don’t
   include a category “neither” for images that aren’t any of those
   labels? This may seem like a good idea, but it’s actually a more
   difficult problem than it seems to be. As with a lot of AI problems,
   the general rule of thumb is that problems that are easy for humans
   are difficult for AI and problem that are difficult for AI are easy
   for humans.

Loading the data (DataBlock)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The first step to any machine learning model is to get the data in the
appropriate format, so that it can be passed into the model. Using
FastAI we can do this by means of a DataBlock which is not the only way
to do this, but is a very easy and simple way to get started. We will
also be going through other ways to load data, but as was mentioned
before, it’s best to get something working, understand how it works and
then customize it. FastAI provides a very easy way to reference your
data by giving the path to the folder where it is stored. So, you should
have a folder called **emotions** in which you create new folders for
each emotion you want to detect i.e. **happy**, **sad**, **surprised**,
**angry**, **confused** and **disgusted**. Inside each of those folders
you put images of people’s faces that correspond to those emotions. We
will specify the path to the folder emotions and use the sub folder
names (happy, sad, etc.) as the label names. This makes it very easy and
intuitive to load the data into the DataBlock which gives us a lot of
flexibility because everything is standardized now.

The following code shows how the DataBlock will load the data

::

   from fastai.vision.all import *
   path = Path("./emotion_images")
   emotions = DataBlock(
       blocks=(ImageBlock, CategoryBlock), 
       get_items=get_image_files, 
       splitter=RandomSplitter(valid_pct=0.2, seed=42),
       get_y=parent_label,
       item_tfms=Resize(128)
       )

The first line ``path = Path("./emotion_images")`` specifies the
directory wherein your data are located. In this case, the folder is
located in the current directory, but if it’s not then you would need to
specify that. You only need to specify the main folder, so you don’t
have to include all the subfolders which should be labeled with the
emotion.

The next block of code creates the variable ``emotions`` which is a
FastAI DataBlock and there are 5 parameters in this example. 1.
``blocks`` - this specifies what type of data will be created for each
unit of data in the DataBlock. In this case it’s the image and it’s
category. 2. ``get_items`` - this refers to the manner in which the
DataBlock will find the data you are passing in. ``get_image_files`` is
a FastAI function which gets all the images from a path that we will
pass in after declaring the function ``emotions``. 3. ``splitter`` -
this refers to the manner in which the data will be split into training
data and testing data. ``RandomSplitter`` is a FastAI function whereby
you can specify the percentage of the data you want to use as test data
(20% in this case which is written as a decimal 0.2). We can also
specify the seed which is 42. A seed is a number that you can provide
which ensures reproducibility of the models results. 4. ``get_y`` - this
tells the DataBlock where to find your label data. In this example the
FastAI function ``parent_label`` takes the string of the folder in which
the image is located. For example, if you have an image called
``happy_person.jpg`` in the folder ``happy`` in the main folder
``emotions`` then the path would be ``emotions/happy/happy_person.jpg``.
The parent_label takes the name of the parent folder which in this case
is ``happy`` as the label name. 5. ``item_tfms`` - this parameter
resizes each image to be the same size. This isn’t necessary to create
the DataBlock, but in the case of images, it is necessary to resize them
to be the same size otherwise they won’t be able to be passed as input
into the model. The images need to be the same size, so that the model
can process them.

Loading the data (Dataloader)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We have our data now nicely packaged in a datablock, but before we can
pass the data as input to train the model we need to create a
dataloader. A dataloader creates a way for the data in the datablock to
be iterated over while providing additional customizations such as
batching, shuffling and a few others. Iterators in Python are objects
that you by whose values can be counted in a sequence such as you would
do in a for loop. When passing input into a machine learning model, it
gets passed in an iterative manner, but this can be slow if you pass
each data item one by one. By using batching, we can pass multiple data
items at a time which makes the whole process a lot faster. This is also
possible because Graphics Processing Units (GPUs) allow for multiple
data to be processed at a time. This is one of the reasons we need to
use a dataloader because we can specify these batch sizes. Shuffling is
also something that the dataloader can do before passing the data into
the model for training. Shuffling helps to prevent overfitting a model
because it means that with every batch there is a different combination
of data together. This prevents any patterns being learned by the model
that would involve data items being grouped together. Ultimately helping
to improve the overall performance of the model and produce better
results.

Dataloaders in FastAI are very simple to implement in a single line of
code because they are a method of the datablock class. Once you have
your datablock variable instantiated then you can execute the following
line of code:

``dls = emotions.dataloaders(path)``

``emotions`` is our datablock variable from before and we are calling
its dataloaders method passing in ``path`` as a parameter. This is the
path that refers to the folder in which all the emotions subfolders are
located. ``dls`` is the typical variable name that is commonly used in
FastAI examples, but you can use any name that suits your code. One we
have the dataloader ready, we can move on to training the model.

Train the model
~~~~~~~~~~~~~~~

Using FastAI, training a model is very simple and can be done in two
lines of code. Using the above-named variables, we can train the model
as follows:

::

   learn = vision_learner(dls=dls, arch=resnet18, metrics=error_rate)
   learn.fine_tune()

``vision_learner`` is a module that provides everything needed to train
a model. There are two parameters that need to be passed to the
vision_learner: ``dls`` and ``arch``. As we have covered before, ``dls``
refers to the dataloader we created earlier. If there have been no
errors in the data and the dataloader has been created correctly, then
there shouldn’t be any problems passing it to the vision_learner. The
second parameter is the ``arch`` which is a shortening of architecture.
This refers to the collection of layers and activation functions that
make up the points through which each piece of data will pass through in
order to produce the output from the input. In this case we are using an
architecure called ``resnet18`` which is the implementation from `He,
K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for
image recognition. In Proceedings of the IEEE conference on computer
vision and pattern recognition
(pp. 770-778). <https://openaccess.thecvf.com/content_cvpr_2016/papers/He_Deep_Residual_Learning_CVPR_2016_paper.pdf>`__.
The number 18 in the name is the number of layers that the architecture
has, so there are different versions of resnet models which all have
different layers. Resnet-50 and Resnet-152 are models that perform very
well, but keep in mind that a higher number of layers means that the
model will train slower since it has more layers for the input to pass
through before producing the output.

Since ``dls`` and ``arch`` are the only two obligatory parameters that
need to be passed into vision_leaner, you can fine tune the model at
this point with the command ``learn.fine_tune()``, however, it’s always
a good idea to pass in a metric (or multiple metrics) which will output
the performance of your model accordingly. The metrics you use depend on
the type of problem you are trying to solve, so in this case where we
are trying to label an image with the correct emotion, ``error_rate`` is
the most appropriate metric to use. Depending on the type of hardware
you are using and the architecture you have chosen, this could take
anywhere from a few seconds to a few minutes. FastAI has been designed
in such a way that it’s extremely efficient, so you usually could run it
on a CPU and it still wouldn’t take that long to finish. However,
running it on a GPU will make it considerably faster and usually only
take a few seconds to run.

If everything has gone according to plan without any errors then you
should get a Pandas data frame as output with five columns: ``epoch``,
``train_loss``,\ ``valid_lost``,\ ``error_rate`` and ``time``. In the
next section, we are going to go through these results and describe what
everything means as well as how to optimize the results.

Understanding the results
~~~~~~~~~~~~~~~~~~~~~~~~~

We’ll start with the first column called ``epoch`` which means how many
times the entire dataset is passed through the algorithm. We previously
discussed batches which is the number of items of data passed as input
to train the model. However, this may seem confusing because when 1
batch is processed this doesn’t mean 1 epoch instead we call that 1
step. A single epoch is made up of many steps, so to make this clearer
consider the following example. Imagine we have 1000 images that we want
to pass as input data. We set the batch size to 10 which means 10 images
will be passed in as input data at a time. If we set the ``epoch`` as 1
then it means there are 10 steps.

   1000 images divided by 10 batches (10 images per batch) = 100 steps.
   This is still 1 epoch.

If we increase the batch size to 20 images per batch then we have the
following

   1000 images divided by 10 batches (20 images per batch) = 50 steps.
   This is still 1 epoch.

If we now increase the epoch we get the following results:

   1000 images divided by 10 batches (20 images per batch) = 50 steps.
   Since ``epoch`` has been changed to 2 when do this process twice, so
   50 steps x 2 = 100 steps. Notice that nothing changes in the number
   images or the number of batches, so the steps remain 50. The number
   of steps only increases to 100 because we run the process twice.

This is important to know because an increase in ``epoch`` doesn’t have
an effect on the batch size of the input data, but only on the number of
times the whole dataset is processed as input. ``epoch`` is a parameter
that can be set when fine tuning the model by specifying it as follows:

``learn.fine_tune()`` # This will train 1 epoch

``learn.fine_tune(2)`` # This will train 2 epochs

``learn.fine_tune(5)`` # This will train 5 epochs

``learn.fine_tune(10)`` # This will train 10 epochs

The number of epochs trained will be displayed in the first column of
the results much like a regular Python list, indexing begins at 0, so
epoch 1 is actually listed as 0 and so forth. You can see an example of
the results below

.. figure:: ./fastai_results_dataframe.PNG
   :alt: FastAI Results

   FastAI Results

However many epochs you choose, your results will start out looking a
little strange i.e. there are two rows of column headings and it looks
like two different dataframes because there are 2 epoch columns with the
number 0. This is a feature of the ``learn.fine_tune()`` function
because it actually trains the model for 1 epoch to find better starting
weights i.e. a better starting point. If you want to know more about
this, you can read the informal `forum
discussion <https://forums.fast.ai/t/understanding-fine-tuning/54142/5>`__,
but the FastAI developers haven’t written an official explanation of it.
For the sake of simplicity, you don’t need to understand it to that
level at this point, but rather just understand that it is designed like
that to increase performance of the model’s training.

The next column is called the ``train_loss`` which is a column
indicating the loss of the training data. Now, this is probably
confusing so I’ll break it down further. Simply put, the loss is the
different between the expected output and the predicted output. The
purpose of training a model is to reduce this loss to be as close to 0
as possible. A loss of 0 would indicate that the expected output is
exactly the same as the predicted output which is never the case, but we
try to train the model as close to 0 as possible.

The column after ``train_loss`` is called ``valid_loss`` and is also
describing loss, but for the validation set (or development set) it is a
percentage of the total data that isn’t in the training set. If we go
back to the section on creating the Datablock, we have indicated the
validation set percentage there, but here it is again for clarification

::

   from fastai.vision.all import *
   path = Path("./emotion_images")
   emotions = DataBlock(
       blocks=(ImageBlock, CategoryBlock), 
       get_items=get_image_files, 
       splitter=RandomSplitter(valid_pct=0.2, seed=42),
       get_y=parent_label,
       item_tfms=Resize(128)
       )

As you can see where from the line
``splitter=RandomSplitter(valid_pct=0.2, seed=42)``, the
``valid_pct=0.2`` is taking 20% of the total data as the validation set
and the rest (80%) as the training set. So, what exactly is a validation
set? When training a model, we can get a loss value and with more epochs
we can decrease that loss value. However, if we keep training and
checking it on the same data then we cannot be sure it will perform well
on new data. We thus use a validation set to train the model, check the
loss results on the training set and check the results on the validation
set. This gives us a better indication of how the model would perform on
new data (which is essentially why we are training the model). Usually
there are 3 dataset splits: training set, validation set and test set.
The test set is usually used at the end when the model is trained to
check the final loss value. However, you can use two sets which can be
confusing sometimes because different developers use different terms, so
the following will show the most common ways data is split for training
a model.

Two data splits (they all refer to the same two datasets)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``Train and dev`` # Dev is short for development

``Train and valid`` # Valid is short for validation

``Train and test``

Three data splits
^^^^^^^^^^^^^^^^^

``Train, dev and test``

``Train, valid and test``

Datasets can be split in different ways, so these can also be changed to
see if performance increases, but there are some common default values.
For two data splits, it’s often the case that you use a 80% train and
20% valid or 75% train and 25% valid. For three data splits, you can use
70% train, 20% valid and 10% test. However, starting with the default
values as a baseline then changing them while checking the performance
is the best way to find the optimal values.

.. _training-a-model-from-scratch-1:

Training a model from scratch
=============================

While it is best for practical purposes to use models developed by other
people, sometimes this is not a possibility. In those cases, you need to
train your own model. When you are training a model from scratch, it is
more complex than using an out-of-the-box model or fine tuning a
pretrained model, but it follows similar principles. There are, however,
more factors to consider, so it’s important to understand what kind of
data you have and which architecture you plan to use. One way to make
the process easier is to find already-made architecture from someone
else’s repository. This is similar to the pretrained model scenario, but
instead of using a base transformer, you are only using the
architecture, so your model is training from scratch. This might also
not be possible, so if there is not anything available then you can look
for publications in the field you are building the model. You can
replicate the architecture of the articles, but train it on your own
data. This is by far the most complicated solution because papers on
deep learning architectures usually involved complex mathematical
notations and assume a good understanding of deep learning principles.
However, they do often have a repository that contains the model they
built for the paper, but this is not always the case.

Whichever strategy you choose, the general rule of thumb is that there
is always at least some or other code base which you can use to get
ideas for your own model. It would be very unlikely that you need to a
build a completely new types of architecture because there are so many
people around the coming up with new architectures, that whatever you
are looking for is usually available somewhere. You just need to find it
and customize it to your own needs. With that in mind, even if you are
using the architecture from someone else’s repository, you still need to
understand what is going so that you can make changes or troubleshoot
when there are problems. It is therefore a good idea to build a few
models from scratch just to understand how they work and what kind of
output you get from the changes to the input and/or hyperparameters.
Learning by doing is the best way to get familiar with not only how the
models work, but also how your coding environment needs to be setup for
everything to work.

In the next part of the course we are going to look at practical
examples of real world problems that are solvable by AI solutions. Using
the information we have learned thus far, we are going to take plausible
tasks and show how they are converted into a broken down and converted
into smaller tasks that are solvable with machine learning models.
Various different types of data will be used, and the difficulties and
limitations for each problem will also be looked at.

Code reproducibility
====================

Without a doubt, you are going to run into problems when working with
machine learning models. This is all part of the process and at some
point you will reach out to someone else to help you solve those
problems. In these cases, the most important thing to do is to be able
to reproduce the results you are getting i.e. reproduce the problem. In
order for someone to help you, they need to know what exactly is the
problem and sharing your screen over a video chat isn’t a good way to do
this. The best way to do this is to save your code as a repository on
`Github <https://github.com/>`__,
`Huggingface <https://huggingface.co/>`__ or any other such platform.
This will make sure you project has version control, and that it can be
viewed and cloned by other people. For those unfamiliar with Git and
Github, there are free courses available from
`CodeRefinery <https://coderefinery.org/lessons/>`__ such `introduction
to version control <https://coderefinery.github.io/git-intro/>`__ and
`collaborating and sharing using GitHub without command
line <https://coderefinery.github.io/github-without-command-line/>`__
which you can work through if you want to know more. Having your work on
Github offers many advantages, but one of the biggest advantages is that
other people can clone your repository and run your work as it is meant
to be run. All the files will be there and you can add instructions,
explanations and environment setups as well.

A part of setting up the environment for running a repository is to
install all the dependencies required for that repository. These
dependencies are specified in the ``requirements.txt`` file and you need
to install them before running anything from the repository. In this
file, you specify all the packages by their name and optionally you can
include which version of the package you want installed. Including this
file is extremely important because without it, it’s much more difficult
to run the repository because if there is a reference to a package that
isn’t installed, it isn’t always clear which package needs to be
installed. This could lead a to a lot of waster time looking for the
correct package. For reproducibility it’s crucial to have the
``requirements.txt`` file, but moreover, it’s also important to include
the version of each package. For example, if you are installing the
transformers library instead of specifying only the library, you can add
the version as well.

``transformers`` # Without version specified

``transformers==4.21.1`` # With version specified

The reason for this is that software packages are regularly updated and
when this happens there can often be conflicts with other packages or
deprecated functions within the package. This can lead to a similar
problem as mentioned before in which you will then need to figure out
where the problems lie. This can lead to a lot of wasted time on
unnecessary tasks. However, if you include the package versions then you
are sure to run the code in the same way as the developer who created
it. This makes asking for help and collaborating with other people much
easier. Therefore, if you aren’t yet familiar with Github it is highly
recommended that you at least take a day or two to learn the basics so
that your code can be stored safely.