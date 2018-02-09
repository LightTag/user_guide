
Downloading and Metrics
============================

Downloading Your Annotation
---------------------------
LightTag's UI provides easy download of all annotations in a :ref:`taskdefinition`, that is the application
of a :ref:`schema` onto a :ref:`dataset`.

Downloading your annotations is easy.

Simply go to the analytics page and click on Download Annotations.
The analytics page can be found at YOUR_DOMAIN.lighttag.io/manager/analytics.
Alternatively, click on Manager ==> Analytics in the Navigation Bar on top

   .. figure:: downloading_annotations.gif
      :scale: 200 %
      :alt: Basic Annotating
      :align: center

      Downloading annotations

Consuming Results
-----------------

LightTag will return not only the annotatiions but also the entire :ref:`dataset` and :ref:`schema` that were used for
annotating. We provide this extra information to save you the effort of joining between a list of annotations and a
dataset stored somewhere else. With that in mind,  LightTag will return a JSON object with that looks like this::

      {'dataset': {'examples': [{'annotations': [{'annotator': 'lighttag',
                                                  'end': 64,
                                                  'example_id': 'fb503d56ab2c457f96361ee306e39eb1',
                                                  'id': '77f4fd6056534e098179b9b03e6a27fc',
                                                  'start': 60,
                                                  'tag': 'God',
                                                  'value': 'LORD'},
                                                 {'annotator': 'lighttag',
                                                  'end': 40,
                                                  'example_id': 'fb503d56ab2c457f96361ee306e39eb1',
                                                  'id': 'e21955d99d5a425c8d6e9c55768b355c',
                                                  'start': 34,
                                                  'tag': 'Pagan God',
                                                  'value': 'Belial'},
                                                 {'annotator': 'lighttag',
                                                  'end': 20,
                                                  'example_id': 'fb503d56ab2c457f96361ee306e39eb1',
                                                  'id': 'eddb43b35fa8419296c6cc715a743e50',
                                                  'start': 17,
                                                  'tag': 'Person',
                                                  'value': 'Eli'}],
                                 'content': ' Now the sons of Eli were sons of '
                                            'Belial; they knew not the LORD.  ',
                                 'id': 'fb503d56ab2c457f96361ee306e39eb1',
                                 'metadata': {'book': 'The First Book of the Kings',
                                              'chapter': 2.14,
                                              'verse': 12}}],
                   'id': '2a6e0c06017d473cb3d5bbb24c28b71c',
                   'name': 'Bible'},
       'id': 'a4b83e46e1b045fca9742c5878715aea',
       'schema': {'id': 'a8e1ba68-ca6e-479b-95b6-98678681ae03',
                  'name': 'Bible',
                  'project': '2753ca38-69d9-4c96-9d31-df6d4069b027',
                  'tags': [{'id': '76f33848-dcbe-42ce-8587-185d1a722234',
                            'name': 'God',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '6c818c42-7901-4b39-9183-8e27764bd89b',
                            'name': 'Pagan God',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '22bc9390-ea2d-4b88-9745-a2f4e65a4699',
                            'name': 'Person',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '06432717-53d5-416f-9181-7420666573c5',
                            'name': 'Nation',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '1650c780-26e2-44f9-af3c-6b1e06cb95ed',
                            'name': 'Place',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '97b4540d-ebd8-447c-ab51-b41ebe5fd606',
                            'name': 'Object',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '16638acf-bc1b-471c-a535-3378913ab872',
                            'name': 'Action',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'},
                           {'id': '01428033-dc8b-4dcc-8929-2622fde2e4bb',
                            'name': 'Emotion',
                            'schema': 'a8e1ba68-ca6e-479b-95b6-98678681ae03'}]}}

The main JSOn object has three keys

1. **id** The id of the :ref:`taskdefinition`
2. **dataset** The :ref:`dataset` that has been annotated. This is the part that contains the annotations
3. **schema** The :ref:`schema` that was used to annotate. The Schema contains a list of all of the :ref:`Tags<tag>`

Easy access to your annotations with Pandas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The wonderful pandas library makes parsing and analyzing your annotations particularly easy. We've prepared an
`example notebook
<https://gist.github.com/talolard/307fa35d7c7e1863ea161cc3d4e22d3d>`_ with examples.