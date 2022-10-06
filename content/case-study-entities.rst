Case study: Extracting entities from a text
===========================================
When you are working from text data, you need to organize it in some way or another. Finding relevant information from the text can be difficult because since text is written by people, it is often not very well structured. However, you can use an AI pipeline to help structure the text in a way that is useful. Using a library such as SpaCy can provide the fundamental textual organization that is needed to get an idea of what important entities are in a text. Entities are words that represent a person, place, time, date, organization, etc. Extracting these entities can provide a lot of information about the text. 

Requirements
------------
- Purpose
    - Extract entities from a text
- Tools
    1. A corpus of text data to work from.
    2. Access to uCloud instance, but it can also be done on Google Colab. A GPU is not necessarily required with SpaCy, but if a very large dataset then a GPU becomes necessary.

Plan of Action
--------------
The following structure will be followed for this project (i.e. the pipeline):
    1. Data preparation
    2. Model selection
    3. Data processing
    4. Entity extraction

Data preparation
----------------
Since SpaCy is a full library, it can take text in as input without needing to preprocess it. We will thus pass our text in as a string without any changes.

Model selection
---------------
SpaCy has a wide range of models available depending on the specific task and they have also built-in support for HuggingFace models, so you can load any models from the HuggingFace repositories. 

Data processing
---------------
We simply pass the strings as input into the SpaCy pipeline then we get ``spacy.tokens.doc.Doc`` objects which contain a lot of information that has been extracted from the text through the pipeline. 

Entity extraction
-----------------
