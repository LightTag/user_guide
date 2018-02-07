.. _dataset:

Dataset
=======

In LightTag a dataset is a collection of :ref:`Examples<example>`.

Structure of a Dataset
----------------------
Datasets have a few parameters for you to define.

1. **Name** each dataset has a name
2. **UniqueId Field** Is an optional parameter. This will enforce a unique constraint on your :ref:`Examples<example>`.
    You can use this to ensure that you do not add duplicate data to your datasets during the life of a project.
2. **Aggregation Field** This paramater specifies which  :ref:`Examples<example>` should be displayed to the annotator
    together. For example if we are annotating conversations and have a field such as *conversation_id*, specifying that
    field as the **Aggregation Field** will ensure LightTag displays all messages from that conversation together.
3. **Order Field** When annotating a few examples together, we need to decide in what order to display them. Continuing
    the conversation example, specifying *message_time* as the order field would ensure that the messages are displayed
    in chronological order to the annotator.

Why do we need datasets
-----------------------
At the onset of an annotation project having a single dataset may be sufficient. As projects progress it is useful
to logically seperate different groups of examples. This seperation enables more fine grained control of the work
done throughout the course of an annotation project, as well as more consistency in the consumption of our annotation results
down stream.

Data use case
~~~~~~~~~~~~~

When preparing data for machine learning, you'll usually want a training dataset as well as one for testing. Its possible
to annotate a single dataset and split it after the fact though this has a number of drawbacks. Notably,

1. Having split the dataset after the fact, it is difficult to add annotations to the desired subset.
2. Maintaining the split at a secondary system introduces the possibility of leakage between datasets, corrupting your
metrics.
3. You can not specify different requirements for the subsets of the data, resulting in extra, inefficent or wrong work.

Using LightTags seperation of datasets we can overcome these difficulties easily.
1. Adding annotations to only our test or train set becomes trivial as they are seperated.
2. Since the seperation is maintained in one place a priori there is no risk of leakage between the two datasets
3. using LightTags :ref:`taskdefinition` abstraction, we can define seperate requirements for a test and train set.

.. ATTENTION::
    **Example**
    We'd like to build an entity recognizer that recognizes company names and their stock ticker in tweets. We collected
    a corpus of 10,000 tweets to build and test our machine learning model with. We seperate the corpus into  two datasets,
    one of 8,000 tweets called "Train" and another of 2,000 tweets we call "Test".
    We want our "Train" datset to be as big as possible, and are willing to tolerate a little noise in it. On the other hand,
    our "Test" is going to be our golden source and we want to be absolutely sure every annotation is correct.

    After uploading the two datasets to LightTag, we create a  :ref:`taskdefinition` for each of them.
    Since on the train set we want to get as many annotations as possible fast, we define that only one annotator needs to
    annotate an example.  We also allow the system to provide suggestions to make the process faster.

    For the "Test" set, we define that each :ref:`example` must be annotaed by 3 distinct people. On the test set, we forbid
    suggestions to avoid introducing bias into our data.

    LightTag will derive the work to be done on each of the datasets and allocate it optimally to each annotator. Once
    the work is complete we will have two annotated datasets. Notably they will be
    1. Seperated, thus we won't worry about leakage between them
    2. Annotated optimally, each example in the "Train" set will have been annotated by a one annotator, possibly using
    suggestions while in the "Test" set, each example will have been annotated by 3 annotators without any external
    suggestions.





Data sources
~~~~~~~~~~~~



Specifying which examples to show together
------------------------------------------
