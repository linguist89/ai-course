Lesson 2: Getting started
=========================

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

What kind of data do you need (for supervised learning)?
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