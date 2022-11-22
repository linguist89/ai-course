Lesson 1: AI course for humanities
==================================

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
-----------

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
-----------

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