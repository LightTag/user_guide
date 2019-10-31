.. _schema:
  
Schema
=======

When labeling data it's crtical that everyone involved uses the same concepts and calls them the same thing. LightTag helps you
enforce that by encapsulating those concepts in a Schema. 

A Schema can have :ref:`Tags<tag>` and/or :ref:`Classes<classes>`. 

Tags are used to annotate parts of an example with *span annotations*, for example to say that "Donald Trump" is a Person. 

Classes are used to classify an entire example, for example "Positive Sentiment". A Schema can be configured as either single class 
or multi class. You'll use single class schemas to annotate concepts that are mutually exclusive, such as Positive vs Negative sentiment. 

You'd use multi-class schemas when the concepts are not mutually exclusive, for example classifying documents as Funny, Interesting and Well Written. 

Schemas can have :ref:`models<models>` associated with them. Models predict span annotations and their output can be displayed 
to annotators to help them work faster, a technique called "pre-annotation" or "suggestions". Models associated with a Schema can 
only predict tags that come from that Schema. 



.. toctree::
   :maxdepth: 1
   
   Tags (Entity Annotation) <tags>
   Classes (Document Classification)  <classes>


.. admonition:: Why Schemas Can't be Modified 
   
   At the moment, Schemas in LightTag can't be changed after creation. This can cause inconvenience and we are working to resolve it. 
   There is a reason for this that you should be aware of: If you labeled data with a schema and then added a new tag or class, that tag
   will not appear in any of the previously annotated data. This can lead to poor model performance and can be hard to track down. 
   If and when we do release the ability to modify Schemas, please be careful to maintain your datas integrity 