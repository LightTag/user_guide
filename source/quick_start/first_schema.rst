.. _first_schema:
Uploading Your First Schema
===========================

After you've defined your first dataset, LightTag's onboarding guide will ask you to define a :ref:`schema`.

   .. figure:: defining_schema.gif
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center

A :ref:`schema` is the holds all of the :ref:`Tags<tag>` and :ref:`Classifications<classification>` that you annotors
can use. You can choose to define only tags, only classifications or both. Downstream, any :ref:`taskdefinition` that uses
the Schema will display the tags and/or Classifications you defined.

Multi Class Classification
---------------------------

Sometimes you'll want to have annotators assign more than one class label to an example. In that case, specify the schema
as a MultiClass classificaiton schema by checking the checkbox.





