.. _example:

Example
----------

In LightTag, an example is a single unit to be annotated. An example could be a tweet, a message in a conversation,
an abstract from a paper or an entire document.
Conversely, an example is an isolated unit of annotation, that is an annotation can not span multiple examples, rather a
single annotation must be contained in one example.


In the annotation UI a single example would like this:

.. figure:: ./img/example.png
  :width: 600
  :alt: An example in the UI
  :align: center

Example Metadata
~~~~~~~~~~~~~~~~

Text data doesn't live in isolation, and often we have additional fields of text that we'd like to keep for further
analysis as well as display to our annotator to provide more context.

For example, you'd like to show the speaker name when annotating a conversation, or the publication name when annotating
an article.

As described in the :ref:`data_prep` section, you'll upload an individual example as a JSON object, which allows you to
upload arbitrary data in essentially arbitrary shapes. LightTag will
1. Store this metadata alongside your example
2. Display it to your annotator
3. Return it to you when you retreive annotations (to spare you a join)


Choosing what makes your own example
~~~~~~~~~~~~~~~~

As a manager of an annotation project one of the more important choices you'll make is what exactly an Example is. Sometimes
the data defines that quite clearly (for example when annotating tweets) while other times there are choices to be made
(for example when annotating long legal documents).

The key factors in choosing what exactly an example is in you project should be guided by the following factors
1. An example should be able to hold any annotation that may come up.
2. Examples should be as short as possible without interrupting your overall goals. Shorter examples are more managable
    for your annotators and tend result in higher quality annotations.
2. Your examples should reflect what you want to do with the data downstream.


Showing multiple examples together
~~~~~~~~~~~~~~~~

Occasionaly you'l want to show your annotators multiple examples at the same time without merging them into a single example.
For example, when annotating a conversation, a single example would be a message but we'd like our annotator to have the
context of the full conversation.

LightTag allows you to this by specifying an **aggregation key**, this is the name of a field that exists in your examples
metadata. When you specify an **aggregation key** LightTag will show all examples with the same value in the **aggregation key**
together.

Similarly, to maintain the order of a number of examples shown together, LightTag allows you to specofy an **order_key**.

Both **aggregation key** and the **order key** are specified on the :ref:`dataset`