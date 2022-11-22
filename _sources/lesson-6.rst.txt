Lesson 6: Training a model from scratch
=======================================

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
--------------------

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