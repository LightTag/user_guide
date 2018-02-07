Uploading Your First Dataset
=============================

The first time you log in to LightTag you'll arrive at the OnBoarding section which begins with defining a :ref:`dataset`.

A Dataset is a collection of :ref:`Examples<example>` with some specifications about how we'd like to show them to our annotators.

When you first start with LightTag we'll ask you to specify a Dataset and upload examples. Here is what that process looks
like


   .. figure:: uploading_a_dataset.gif
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center




Naming Our Datset
-----------------
We gave our dataset a name "Example Upload" then selected the JSON file with our data.

Then LightTag read the JSON and saw what fields exist on the individual JSON objects.

Defining what to annotate
-------------------------
LightTag asked us "What field in the objects contains the text you want to annotate?" and we said Message

   .. figure:: selecting_content_field.png
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center

      Specifying the Message is the field that contains the data to be annotated
If you look at the animation above, it goes through a few other options that we will come back to in a moment. For now
we've defined a Dataset named "Example Upload", uploaded the actual data and told LightTag we want to annotate the text in the Message field.

Adding a Unique Constraint
--------------------------
LightTag wants to maintain the integrity of your data. If your data has a field on it that should be unique in the dataset
you can specify as much and LightTag will enforce that unique constraint for you.
This can be useful if you plan to update your datasets and want to ensure you don't add duplicates.
In our simple example we don't have a field for this and so left that option blank.

   .. figure:: choose_unique_id.png
      :scale: 100 %
      :alt: Selecting a unique id
      :align: center

      Selecting (or in this case, leaving blank) a Unique id




Showing multiple examples together
----------------------------------

The way we defined our Dataset, LightTag will show an annotator exactly one message at a time. When we are dealing with
independent texts (like distinct articles) this might make sense. But when dealing with a conversation we might want to
have the annotator go through all of the messages in the conversation so that they can be aware of the context.

To facilitate this, LightTag lets you specify an optional *aggregation_key*. This tells LightTag that we should show all
Examples with the a shared value of that key together. In our example, **"Conv_id"** is a good aggregation key

   .. figure:: choose_aggregation_key.png
      :scale: 100 %
      :alt: Selecting an aggregation key
      :align: center

      Choosing **Conv_id** as the field to aggregate Examples by

Of course, we'd like to show the messages in a conversation in the order in which they came. LightTag allows us
to specify an *order key* which does exactly that. In our case, a natural choice for sorting would be **Time**

.. DANGER::
   Since JSON has no native representation of time, LightTag can't sort by your date and time strings correctly.
   To get over this problem, either convert your dates to epoch time or add a field with the sequential order.




