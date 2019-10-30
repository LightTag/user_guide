======================
Understanding LightTag
======================

.. toctree::
   :maxdepth: 1
   
   Datasets <dataset/index>
   Schemas <schema/index>
   Task Definitions <taskdefinition/index>
   Teams <team/index>
   Relations <relations/index>


How Can LightTag Help Me ? 
---------------------------

1. LightTag's Annotation Interface makes entity annotation, document classification and relationship annotation easy and fast.
2. LightTag's workforce management features automatically assign labeling tasks to you and your teams, so you don't have to manage them.
3. LightTag's review mode and analytics give you insights on the quantity and quality of your labeled data and models 
4. LightTag's support for external models let's you speed up your annotators and review your production models. 



A Typical Use Case
--------------------

.. admonition:: A Quick Example

    **What Needs To Be Done**
    
    Bob has a dataset of 1000 tweets. He'd like to annotate the entities in them as either Person or Location. Bob's friend,
    Alice, is going to label with him. Bob wants to get through the data as fast as possible, so he wants each tweet to be labeld
    by either Alice or Bob, but not both. 
    
    **Setting It Up in LightTag**
    

    To Implement this in LightTag, Bob 

    1. uploads his tweets as a new Dataset 
    2. defines a Schema with the Tags Person and Location. 
    3. creates a new Task Definition, that says " Label my tweets Dataset with my Schema. I want each tweet to be labeled exactly once" 
    
    **Labeling Data**

    After creating the Task Definition, whenever Alice or Bob log-in to LightTag, LightTag will serve them data to label. Once they complete
    annotating an example and submit it, LightTag will give them the next example to annotate, until the task is complete. 


The above example introduced a few core concepts in LightTag

.. tip::     Click on any of the links for details on each of these concepts


- A :ref:`Dataset<dataset>` is a collection of data you want to label, such as Bob's 1000 tweets.
- An :ref:`Example<example>`. is one unit of data from the dataset, such as a single tweet from Bob's dataset
- A :ref:`Schema<schema>` is a collection of the concepts you want to apply to your text. A Schema is comprised of Tags and Classes
- A :ref:`Tag<tag>` is a concept applied to a span of Text. For example, *"Donald Trump"* is a *Person* and *America* is a Place
- A :ref:`Class<classes>` is a concept applied to an entire Example. For example, *"Positive sentiment"*. 
- A :ref:`Task Definition<taskdefinition>` defines the work that needs to be done and how it should be done. For example "Label my tweets Dataset with the concepts from my schema so that each example is labeled one".
