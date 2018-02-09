LightTag Quick Start
===============================================

.. toctree::
   :caption: In this section:
   :maxdepth: 1

   Preparing your data <data_prep>
   Uploading your first dataset <first_dataset>
   Define your first Schema <first_schema>
   Defining Your First Task Definition <first_task>
   Annotating <annotating_basics>
   Downloading and Metrics <downloading>

A quick guide to thinking in LightTag
-------------------------------------

LightTag helps you annotate a :ref:`dataset` with a :ref:`schema`. A combination of a Datset and a Schema, together
with a specification of the desired number of annotators per :ref:`example` is called a :ref:`taskdefinition`.


To give a motivating example, consider we want to train an entity recogniser on the bible. We'd start by asking which
entities we might be interested in recognizing, and possible come up with

- God
- Person
- Nation
- Place
- Pagan God
- Action

which we will put together in a Schema and calll that Schema "BibTags"

.. ATTENTION::
   LightTag uses the more general term :ref:`tag` instead of entities (An action isn't really an entity, is it? ). A collection
   of such Tags makes up a :ref:`schema`.
   A schema's tags should be mutually exclusive, that is a particular span of text can only be tagged as only one thing.
   Sometimes we'd like to annotate the same span of text as more than one thing. For instance "David" is a Person and also
   a "Proper Noun". But those two concepts, Person and Proper Noun, exist in distinct schemas.


Being the good data scientists that we are, we split our initial dataset, the Bible, into two parts. From the first part
we will make a "training set" and from the second part we will make a "test set".

Generally we'd want to make sure that our test set was as accurate as possible even if we'd have to settle for a smaller
set. Conversely, for the training set, we might tolerate a lower confidence for the sake of getting a much larger sample
size.

To achieve this we'll create two :ref:`taskdefinition`.

Our first Task Definition would be "Annotate Dataset **Train** with Schema *BibTags*, ensuring every :ref:`example` was
annotated by at least **1** annotators.

Our second Task Definition would be "Annotate Dataset **Test** with Schema *BibTags*, ensuring every :ref:`example` was
annotated by at least **3** annotators.

Once we've defined our two Task Definitions, LightTag will automatically derive the work that needs to be done and allocate
individual :ref:`task`s to annotators.

The next section will describe how LightTag expects to ingest your data and why.
