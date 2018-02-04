Getting Data Ready
===========================


LightTag expect you to upload your data as a JSON array of objects.  For example consider the following data

+-------+-------+----------------+----------------------------------------------------------------------------------+
|Conv_id|Speaker|Time            | Message                                                                          |
+=======+=======+================+==================================================================================+
|1      |    A  |      19:15:15  | Hello, I want a Flight to New York                                               |
+-------+-------+----------------+----------------------------------------------------------------------------------+
|1      |    B  |      19:15:23  | Hi. Sure where will you ne flying from ?                                         |
+-------+-------+----------------+----------------------------------------------------------------------------------+
|1      |    A  |      19:15:44  | I think Miami, but maybe New Orleans instead.                                    |
+-------+-------+----------------+----------------------------------------------------------------------------------+
|2      |    C  |      19:15:15  | Can you get me a cab to from LAX to JFK?                                         |
+-------+-------+----------------+----------------------------------------------------------------------------------+
|2      |    D  |      19:15:55  | I'm sorry, I'm not sure I understand. Can you clarify what you mean?             |
+-------+-------+----------------+----------------------------------------------------------------------------------+
|2      |    C  |      19:16:03  | Forget it. Just give me a human to speak with                                    |
+-------+-------+----------------+----------------------------------------------------------------------------------+

To get this into LightTag we'd convert the table into a JSON array of objects where each object corresponds to a row::

    [
        {   "Conv_id":1,
            "Spaker": "A",
            "Time": "19:15:15",
            "Message": "Hello, I want a Flight to New York"
        },
        {   "Conv_id":1,
            "Speaker": "B",
            "Time": "19:15:23",
            "Message": "Hi. Sure where will you ne flying from ?"
        },
        ...
    ]

To get this into LightTag we simply follow the wizard (Which you will be brought to automatically when you first login)
   .. figure:: uploading_a_dataset.gif
      :scale: 100 %
      :alt: Uploading a dataset
      :align: center

What just happened?
..................

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
we've defined a Dataset named "Example Upload", uploaded the actual data and told LightTag we want to annotate the text in
      the Message field.

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




