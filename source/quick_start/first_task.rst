Uploading Your First Task
=========================

At this point you should have defined a :ref:`dataset` and a :ref:`schema`. It's now time to specify that we'd like
to annotate our Dataset with our Schema.

   .. figure:: adding_task_definition.gif
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center

As you can see, aside from specifying the Dataset and Schema, we provide two other details.
**Annotators Per Example** defines how many distinct annotators must annotate each example before we consider it complete.
LightTag will use this information to decide what :ref:`task` should be done by a given annotator.

**Use Suggestions**
We may decide to not use external or LightTag provided suggestions for a particular task. This makes sense if we
do not want to introduce any bias into our dataset.
