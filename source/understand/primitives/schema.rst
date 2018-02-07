.. _schema:

Schema
=======

In LightTag a Schema is a list of :ref:`Tags<tag>` as well as classification types. The fundamental work done in LightTag is applying a Schema
to a :ref:`dataset`.

.. ATTENTION::
    A schema is your model of the world, it defines what your annotators can and can not express. Some schemas are very clear,
    such as "person", "city", "company" while others can be quite vauge such as "negative sentiment", "expression of happyness".

    As a manager of an annotation project, it is your job to define a schema that both captures the phenomena that you want
    to capture while also being easy for you annotators to understand and recognize.

    When starting an annotation project with a newly defined schema, it is worthwile to do a test run and test for tag
    agreement with LightTags :ref:`analytics` module. A good schema will show that your annotators consistently agree on
    a tag. That is when one annotator said "A" the others also said "A".

       .. figure:: typeHeatmap.jpeg
          :scale: 100 %
          :alt: comparing agreement
          :align: center

          Comparing annotators agreement on type. The red line means something is not clear with "Positive Regulation"

    Capturing these mistakes early on in an annotation project gives you the opportunity to correct early rather than
        collect a large set of inconsistent or imprecise annotations.




Schema Attributes
-----------------
A schema has just one attribute, it's name. If you have multiple schemas the names must be unique.

Tags in a Schema are mutually exclusive
---------------------------------------

An important point in LightTag is that tags in a schema are mutually exclusive. Said simply, an annotation can only have
one tag, and tags can not overlap or be nested. This design decision was introduced to both keep the annotators job
simple and allow stricter enforcment of  the integrity of the data. We are open to relaxing these restrictions if the
community requires it.

.. ATTENTION::
    Sometimes you will want to annotate the same thing with two different tags. As a contrived example, consider "
    "Bill eats chocolate". We might want to annotate "Bill" as both a *Person* and a *Proper Noun*. Fundamentally, these
    are concepts from two distinct schemas. Thus to allow the "double annotation" and keep your annotators job simple
    define a "Parts of Speech" schema and a "Named Entity" schema and run seperate annotation jobs.

