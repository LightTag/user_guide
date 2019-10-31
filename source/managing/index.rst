
Configuration and Project Management
=====================================

.. toctree::
   :maxdepth: 1
   :caption: Core Management Concepts

   Datasets <dataset/index>
   Schemas <schema/index>
   Task Definitions <taskdefinition/index>
   Teams <team/index>
   Relations <relations/index>

Every annotation project is different and needs to be managed accorgdingly. This section introduces the core concepts that make up an annotation
project in LightTag and how you can configure them. This section gives a detailed explanation of each concept, if you want to find how to 
do something fast take a look at the :ref:`recipes<recipes>` section.

The hard part of labeling data is keeping track of who did what and what each person should do next. LightTag makes that easy, we automate it for you.
The core concepts shown below are the tools you'll use to tell LightTag *what you want to do* and *how you want it done*. 

What Needs To Be Done
---------------------------

Whenever you or your annotators log in, you'll be assigned a Task - a unit of work that needs to be done. As a manager, you'll tell LightTag what
work needs to be done by making a :ref:`Task Definition<taskdefinition>`. A Task Definition specifies what data to label (a Dataset), which concepts 
to label it with (A Schema) and who should be doing the labeling (A Team). 

How it Should Be Done
---------------------------


You'll want to configure your annotation project to be done in a particular way for example.
- We want three people to annotate each example to ensure quality.
- We want one person to label each example to maximize throughput.
- We want to show multiple examples together so that annotators can see the broader context.
- We want to provide suggestions to our annotators from our existing models and dictionaries. 
- We want to specify guidelines that annotators can access 

These options and many more, are configured in the Task Definition, Dataset and Schema objects described below. Again, if you're looking for a 
specific way to do something, take a look at the :ref:`recipes<recipes>` section as well.


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

