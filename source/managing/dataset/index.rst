.. _dataset:


Dataset
=======

A Dataset contains a set of data that you want to annotate and specifies details about how that data should be displayed. 
Datasets serve another important role, they track and isolate the pedigree of your data. This means different things to different
people but you will likely want to split your data along an axis such as Test/Train, Language, Source or Date.

LightTag won't split the data for you, but it will make ensure that you will always know which dataset an example and an annotation came from. 

The text data you'll be annotating has a context and typically metadata. LightTag will store this data for you, so that you will always have
it available in proximity to the annotations you produce. 

Some datasets are contextual and need to be annotated as such. Dialog data is an example, in which annotators annotate messages separately but need
to have the conversations context and thus see all examples from a conversation together and in order. This can be achieved with 
aggregation and order fields


.. toctree::
   :maxdepth: 1
   
   data_formats
   add_dataset
   contextual_display
   example

