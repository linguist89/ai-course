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
The Python code below is simply loading arbitrary text, using it as input in a Spacy pipeline and outputting all the entities. In addition, it is only outputting the entities that are listed as ``PERSON`` which, as the name suggests, are names of people. Looking through the tabs, you can see that there are three different variations of the same code i.e. Spacy small (en_core_web_sm), Spacy medium (en_core_web_md) and Spacy large (en_core_web_sm). These three variations illustrate how the results differ when using different pretrained models. The sizes refer to the sizes of the models themselves, so smaller models are small in size, but also less accurate while the larger the model becomes, the more accurate it becomes. 

The best way to choose the appropriate model is to decide what is the best outcome for your project based on the results you want and the hardware (such as storage space, processing ability and time) you have available to you. There is not correct answer, but everything is dependent on the requirements of your project. Also present in the results is the fact that not all entities detected are valid names. Sometimes there are mistakes present, so it beneficial to decide what level of error can you accept in your project.

.. tabs::

    .. tab:: Spacy small

        .. code-block::

            import spacy
            nlp = spacy.load("en_core_web_sm")
            text = "The top three finishers in the 2021 elite women's race – winner Joyciline Jepkosgei and runners-up Degitu Azimeraw and Ashete Bekere – all competed in 2022.[10] Yalemzerf Yehualaw, the world record holder in the 10 kilometres event, competed in her first London Marathon - her time of 2:17:23 at the 2022 Hamburg Marathon was the fastest by a marathon debutant ever.[10] Other competitors with a personal best of under 2:20:00 included Joan Chelimo Melly, Sutume Asefa Kebede, Alemu Megertu and Hiwot Gebrekidan.[10] Judith Korir was a late addition to the field; she had originally intended to be a pacemaker at the event.[11] 2019 and 2020 winner Brigid Kosgei, who finished fourth in 2021, was also scheduled to race,[10][12] but withdrew due to an injury.[13] Briton Eilish McColgan, whose mother Liz won the 1996 London Marathon, was scheduled to race in what would have been her first marathon competition,[10][14] but she withdrew for medical reasons.[15] British runner Charlotte Purdue, who finished tenth in the 2021 race, was scheduled to compete,[10] but withdrew on the day due to illness.[16] The elite men's race featured 2021 winner Sisay Lemma, as well as Kenenisa Bekele, Birhanu Legese and Mosinet Geremew, the second, third and fifth-fastest marathon runners in history respectively.[17][18] Legese had won the Tokyo Marathon twice.[3] Bashir Abdi, who came third in the marathon event at the 2020 Summer Olympics raced in his first London Marathon,[19] and Phil Sesemann, the best British finisher at the 2021 race, also competed in 2022.[13] Vincent Kipchumba, who finished second in 2020 and 2021 was scheduled to compete, but later withdrew.[11] Briton Mo Farah, who came third at the 2018 London Marathon and who was a pacemaker for the 2020 race,[20] withdrew prior to the race due to a hip injury.[21] The women's wheelchair race included 2020 winner Nikita den Boer, Merle Menje, who finished second in the 2021 event at the age of 17, four-time London Marathon winner Tatyana McFadden, and Susannah Scaroni, the record holder in the 5,000 metres event.[4] Catherine Debrunner, who won the 2022 Berlin Marathon on her marathon debut also competed.[22] 2021 winner Manuela Schär, as well as Madison de Rozario, who won the marathon event at the delayed 2020 Summer Paralympics and the 2018 London Marathon, both planned to compete but withdrew due to illness.[23] The men's wheelchair competition featured 2021 winner Marcel Hug, as well as 2019 winner Daniel Romanchuk, who also won the 2022 Boston Marathon. Eight-time winner David Weir also competed.[4][24]"
            spacy_text = nlp(text)
            entities = [e for e in list(spacy_text.ents) if e.label_ == "PERSON"]
            for entity in entities:
                print(entity)

            >>  Joyciline Jepkosgei
                Joan Chelimo Melly
                Asefa Kebede
                Brigid Kosgei
                Liz
                Charlotte Purdue
                Sisay Lemma
                Kenenisa Bekele
                Birhanu Legese
                Mosinet Geremew
                Phil Sesemann
                Vincent Kipchumba
                Merle Menje
                Tatyana McFadden
                Susannah Scaroni
                Manuela Schär
                Madison de Rozario
                Daniel Romanchuk
                David Weir

    .. tab:: Spacy medium

        .. code-block::

            import spacy
            nlp = spacy.load("en_core_web_md")
            text = "The top three finishers in the 2021 elite women's race – winner Joyciline Jepkosgei and runners-up Degitu Azimeraw and Ashete Bekere – all competed in 2022.[10] Yalemzerf Yehualaw, the world record holder in the 10 kilometres event, competed in her first London Marathon - her time of 2:17:23 at the 2022 Hamburg Marathon was the fastest by a marathon debutant ever.[10] Other competitors with a personal best of under 2:20:00 included Joan Chelimo Melly, Sutume Asefa Kebede, Alemu Megertu and Hiwot Gebrekidan.[10] Judith Korir was a late addition to the field; she had originally intended to be a pacemaker at the event.[11] 2019 and 2020 winner Brigid Kosgei, who finished fourth in 2021, was also scheduled to race,[10][12] but withdrew due to an injury.[13] Briton Eilish McColgan, whose mother Liz won the 1996 London Marathon, was scheduled to race in what would have been her first marathon competition,[10][14] but she withdrew for medical reasons.[15] British runner Charlotte Purdue, who finished tenth in the 2021 race, was scheduled to compete,[10] but withdrew on the day due to illness.[16] The elite men's race featured 2021 winner Sisay Lemma, as well as Kenenisa Bekele, Birhanu Legese and Mosinet Geremew, the second, third and fifth-fastest marathon runners in history respectively.[17][18] Legese had won the Tokyo Marathon twice.[3] Bashir Abdi, who came third in the marathon event at the 2020 Summer Olympics raced in his first London Marathon,[19] and Phil Sesemann, the best British finisher at the 2021 race, also competed in 2022.[13] Vincent Kipchumba, who finished second in 2020 and 2021 was scheduled to compete, but later withdrew.[11] Briton Mo Farah, who came third at the 2018 London Marathon and who was a pacemaker for the 2020 race,[20] withdrew prior to the race due to a hip injury.[21] The women's wheelchair race included 2020 winner Nikita den Boer, Merle Menje, who finished second in the 2021 event at the age of 17, four-time London Marathon winner Tatyana McFadden, and Susannah Scaroni, the record holder in the 5,000 metres event.[4] Catherine Debrunner, who won the 2022 Berlin Marathon on her marathon debut also competed.[22] 2021 winner Manuela Schär, as well as Madison de Rozario, who won the marathon event at the delayed 2020 Summer Paralympics and the 2018 London Marathon, both planned to compete but withdrew due to illness.[23] The men's wheelchair competition featured 2021 winner Marcel Hug, as well as 2019 winner Daniel Romanchuk, who also won the 2022 Boston Marathon. Eight-time winner David Weir also competed.[4][24]"
            spacy_text = nlp(text)
            entities = [e for e in list(spacy_text.ents) if e.label_ == "PERSON"]
            for entity in entities:
                print(entity)

            >>  Joyciline
                Ashete Bekere
                Joan Chelimo Melly
                Asefa Kebede
                Hiwot Gebrekidan.[10]
                Brigid Kosgei
                Liz
                Charlotte Purdue
                Sisay Lemma
                Kenenisa Bekele
                Birhanu Legese
                Mosinet Geremew
                Phil Sesemann
                Vincent Kipchumba
                Nikita den Boer
                Merle Menje
                Tatyana McFadden
                Susannah Scaroni
                event.[4] Catherine Debrunner
                Manuela Schär
                Madison de Rozario
                Marcel Hug
                Daniel Romanchuk
                David Weir
    .. tab:: Spacy large

        .. code-block::

            import spacy
            nlp = spacy.load("en_core_web_lg")
            text = "The top three finishers in the 2021 elite women's race – winner Joyciline Jepkosgei and runners-up Degitu Azimeraw and Ashete Bekere – all competed in 2022.[10] Yalemzerf Yehualaw, the world record holder in the 10 kilometres event, competed in her first London Marathon - her time of 2:17:23 at the 2022 Hamburg Marathon was the fastest by a marathon debutant ever.[10] Other competitors with a personal best of under 2:20:00 included Joan Chelimo Melly, Sutume Asefa Kebede, Alemu Megertu and Hiwot Gebrekidan.[10] Judith Korir was a late addition to the field; she had originally intended to be a pacemaker at the event.[11] 2019 and 2020 winner Brigid Kosgei, who finished fourth in 2021, was also scheduled to race,[10][12] but withdrew due to an injury.[13] Briton Eilish McColgan, whose mother Liz won the 1996 London Marathon, was scheduled to race in what would have been her first marathon competition,[10][14] but she withdrew for medical reasons.[15] British runner Charlotte Purdue, who finished tenth in the 2021 race, was scheduled to compete,[10] but withdrew on the day due to illness.[16] The elite men's race featured 2021 winner Sisay Lemma, as well as Kenenisa Bekele, Birhanu Legese and Mosinet Geremew, the second, third and fifth-fastest marathon runners in history respectively.[17][18] Legese had won the Tokyo Marathon twice.[3] Bashir Abdi, who came third in the marathon event at the 2020 Summer Olympics raced in his first London Marathon,[19] and Phil Sesemann, the best British finisher at the 2021 race, also competed in 2022.[13] Vincent Kipchumba, who finished second in 2020 and 2021 was scheduled to compete, but later withdrew.[11] Briton Mo Farah, who came third at the 2018 London Marathon and who was a pacemaker for the 2020 race,[20] withdrew prior to the race due to a hip injury.[21] The women's wheelchair race included 2020 winner Nikita den Boer, Merle Menje, who finished second in the 2021 event at the age of 17, four-time London Marathon winner Tatyana McFadden, and Susannah Scaroni, the record holder in the 5,000 metres event.[4] Catherine Debrunner, who won the 2022 Berlin Marathon on her marathon debut also competed.[22] 2021 winner Manuela Schär, as well as Madison de Rozario, who won the marathon event at the delayed 2020 Summer Paralympics and the 2018 London Marathon, both planned to compete but withdrew due to illness.[23] The men's wheelchair competition featured 2021 winner Marcel Hug, as well as 2019 winner Daniel Romanchuk, who also won the 2022 Boston Marathon. Eight-time winner David Weir also competed.[4][24]"
            spacy_text = nlp(text)
            entities = [e for e in list(spacy_text.ents) if e.label_ == "PERSON"]
            for entity in entities:
                print(entity)

            >>  Joyciline Jepkosgei
                Ashete Bekere
                2:20:00
                Joan Chelimo Melly
                Asefa Kebede
                Alemu Megertu
                Hiwot
                Judith Korir
                Brigid Kosgei
                Eilish McColgan
                Liz
                Charlotte Purdue
                Sisay Lemma
                Kenenisa Bekele
                Birhanu Legese
                Mosinet Geremew
                Bashir Abdi
                Phil Sesemann
                Vincent Kipchumba
                Briton Mo Farah
                Nikita den Boer
                Merle Menje
                Tatyana McFadden
                Susannah Scaroni
                Catherine Debrunner
                Manuela Schär
                Daniel Romanchuk
                David Weir