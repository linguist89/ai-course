Lesson 4: Using out-of-the-box models
=====================================

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