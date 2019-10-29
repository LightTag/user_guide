ADDING SUGGESTIONS
==================

.. contents:: Table of Contents


Introduction
------------
It's often the case that you'll want your annotators to validate machine generated annotations. In LightTags parlance
we call machine generated annotations suggestions and say the an annotator accepted or rejected a particular suggestion.

   .. figure:: suggestion2.gif
      :alt: Accepting or Rejecting a suggestion
      :align: center

      Accepting or Rejecting a suggestion

This section deals with the theory of suggestions.  See the example (from the menu on the right) for the technical details

.. DANGER::
   While the concepts presented here are final, your interface to them via the API is subject to change. LightTag 
   is in the process of rewriting and documenting a more consistent REST API which will change the endpoints
   described herein. 
   Furthermore, we are aware of a few use cases for which the current suggestion interface is unintuitive. We 
   are working to resolve these issues promptly


What are suggestions good for
-------------------------------
From our own experience and customer feedback, suggestions can be used for either of two overlapping purposes. 
The first is to quickly validate an existing model. The second is to quickly increase the size of a labeled data set. 

We say these are overlapping because every accepted or reject suggestion used to validate a model is also an annotation that 
increases the size of a training set. Conversely, any annotation or rejection of a suggestion will remain in the system and implicitly validates
any future suggestion. Said differently, an annotation made today determines the truthyness of a model made tomorrow. 

.. DANGER::
   Providing suggestions is not a panacea. Suggestions introduce bias into your dataset from a number of sources. The most obvious one being the 
   bias of the model that generated the suggestion. 
   Annotators tend to get complacent when shown suggestions which introduces further bias. While LightTag provides metrics that can make
   these phenomena visible, it is important that you as a manager are aware of them and  test for them.

Validating a model with the Suggestions interface
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
One common use case for suggestions is to quickly validate the accuracy of a model by having annotators accept or reject
each of it's outputs. This is straightforward in LightTag, simply upload a set of suggestions and continue work as before. 

.. WARNING::
   LightTag currently associates a Suggestion Model with a :ref:`schema`. Defining the work of validating a particular
   model should fall under a ref:`taskdefinition`. Until this transition is implemented, LightTag will display suggestions
   from all Suggestion Models associated with a particular Schema. This means that 

   1. Your annotators may see suggestions from multiple models at the same time

   2. In the case where two Suggestion Models output partial overlapping annotations, only one suggestion will 
   be displayed to the annotator. 

   3. If two (or more) models output an equivalent suggestion, an annotators response to one of them will be recorded
   for all of them 

   In the coming release of LightTag these issues will be resolved by allowing you to designate a task as either a model validation task or a data gathering task. 
   In the case of the former, you will specify a single model to be validated and only its suggestions will be shown



Where suggestions come from
----------------------------

Suggestions come from a Suggestion Model, which is some machine that takes an :ref:`example` and assigns :ref:`tag` from a :ref:`schema`. 
Suggestions can come from two places

LightTag Generated Suggestions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Unless disabled, LightTag will continuously learn from your annotations and provide new suggestions. This mode is active by default
alongside any other model. 


User submitted Suggestions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Often you will have a model that you would like to validate or use to help your annotators work faster. 
As an example of the latter, you may be interested in labeling peoples names, and can provide a dictionary of names to 
help your annotators go faster. 

In this case LightTag offers the ability to upload your own suggestions via our REST API. 


Restrictions on suggestions
----------------------------------
There are a few restrictions on the suggestions you can upload 

1. A single model can not have overlapping suggestions. That is for any substring of an example, a single model 
will associate at most one suggestion to it. 



