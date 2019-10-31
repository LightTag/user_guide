.. _taskdefinition:

TaskDefinition
==============

The beuty of LightTag is that it manages the work to be done, that is the individual task. You don't need
to define them or assign them. Instead you only need to define what you want, LightTag will make that happen.

The definition of an annotation project can be said in one sentance
"I want *n* annotators to annotate :ref:`dataset` A with :ref:`tags<tag>` from :ref:`schema` B"


Task Definition parameters
--------------------------

* **Dataset**
      The Dataset we want to annotate
* **Schema**
      The schema that we want to apply to annotate the dataset with
* **Annotators Per Example**
      The number of distinct annotators that should annotate each example in the dataset
* **Use Suggestions**
      Do you want your annotators to be shown suggestions of possible annotations

