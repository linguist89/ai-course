Lesson 5: Fine tuning pretrained models
=======================================

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