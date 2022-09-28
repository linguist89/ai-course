Case study: Classifying film posters into different genres
==========================================================
When you have a bunch of movie posters and you want to classify them into specific genres e.g. comedy, romance, action, etc., you need to understand how the process works. A classification task using a deep learning model isn't exactly the same as how a human would make classifications. When a person looks at a movie poster, they can give their opinion of what the movie's genre is and they can even come up with a new genre. However, when you use a deep learning model to classfiy movie posters' genres then you need to provide a list from which it chooses a genre and it cannot generate new genres, so it will classify everything into one of the genres on the list. In essence, the question then becomes "from this list of genres, which genre best fits the movie poster?" which means that we need a genre for each movie poster in our data. 

Requirements
------------
- Purpose
    - Classify new posters into genres
- Tools
    1. Dataset containing poster images and their corresponding genre(s).
    2. Access to a GPU instance which is available on UCloud, but it can also be done on Google Colab.

Plan of Action
--------------
The following structure will be followed for this project (i.e. the pipeline):
    1. Data preparation
    2. Model selection
    3. Finetuning
    4. Inference (also known as prediction)

The above steps will be taken as many times as is necessary, but at least twice. The first time is without any major changes to the pipeline to establish baseline model results. This is important because we need to be able to determine if the results are getting better or not and this can only be done by comparing subsequent results with a baseline.

Data Preparation
----------------
When working with image data the most important data preparation you need to do is to resize all images. This is because images can vary in size, but they cannot be fed into the model as input while they are different sizes. Resizing an image is therefore done when creating the baseline model and will apply for all subsequent moels as well. 