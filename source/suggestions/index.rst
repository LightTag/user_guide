.. _suggestions:
Suggestions, Pre-annotations and Model Analytics
################################################
.. raw:: html

    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
        <iframe src="https://www.youtube.com/embed/M0dxYiEmkk0" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>


With LightTag you can upload existing annotations, the output of your models and dictionaries. You can use these in two ways either 



1. As Pre-annotations to help your team work faster
2. To review and compare multiple models and refine their outputs. 


.. toctree::
   :caption: Guides:
   :maxdepth: 1

   Suggestion Basics <suggestions> 
   Suggestion At Scale <advanced> 


Key Concepts
*************
Suggestions Belong to a SuggestionModel
========================================
Suggestions are associated with a SuggestionModel that you register in LightTag. Each model can suggest concepts from the Schema it is associated with. 

SuggestionModels Belong to a Schema
====================================
For example, if you have a Schema with the Tags Person,Place and Org, you can register a Model to that Schema and it can suggest any of those tags. 

Testaments - Saying that a model has nothing to say 
===================================================
Sometimes your models will have no output about a peice of text (an example). To provide accurate analytics, LightTag let's you record ocourences where a model had not outputs. 
We call these records a Testament, that is the model attests to having viewed the example. 


Restrictions
============
You can add as many suggestions as you wish, and as many SuggestionModels as you'd like. The only constraints are that 
1. A model may only suggest tags from the Schema it is associated with 
2. A model can't output overlapping suggestions. 




