Defining Your First Task Definition
=========================

At this point you should have defined a :ref:`dataset` and a :ref:`schema`. It's now time to specify that we'd like
to annotate our Dataset with our Schema.

   .. figure:: adding_task_definition.gif
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center

As shown to define a task we 

1. Give it a unique name
2. Select the dataset we want to label
3. Select the schema we want to label with
4. Select how many annotators we'd like to have on each example

There are also two more advanced options

1. We can define which Models we'll use to provide suggestions, if any. The default setting will use LightTag generated suggestions
2. We'll specify which :ref:`team` can work on this Task. The default value of Everyone will let everyone work on this task. 


You can read more about these features in the Managing Projects section 
As you can see, aside from specifying the Dataset and Schema, we provide two other details.
**Annotators Per Example** defines how many distinct annotators must annotate each example before we consider it complete.
LightTag will use this information to decide what :ref:`task` should be done by a given annotator.

**Use Suggestions**
We may decide to not use external or LightTag provided suggestions for a particular task. This makes sense if we
do not want to introduce any bias into our dataset.
