.. _data_prep:

Supported Dataset Formats
===========================

LightTag Datasets are lists of Examples. Each example has the text you want to annotate as well as additional metadata

.. admonition:: What Your Data Might Look Like

    Your data can come from various places such as a database, exported from a CRM or as the output from an OCR process. 
    Usually it will look something like the table below, where one column has the text to label and the rest are metadata

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

The table above shows a (small) dataset. You can upload a dataset like this as either a JSON or CSV. We recomend using JSON where possible

JSON Data Format
~~~~~~~~~~~~

To upload data to LightTag in JSON format, prepare a JSON file that has a single array of objects, where each object corresponds to one eaxmple 
(one row in the table above) 

.. code-block:: json
    
    //my_data.json
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

CSV Data Format
~~~~~~~~~~~~~~~~

You can also upload data as a CSV or TSV file. That would look just like the table above. 

.. DANGER::
   Some systems output CSVs that are subtely malformed. While rare, this can lead to malformed data. 
   If you do use a CSV format, preview your data during dataset upload 

   .. figure:: ./img/previewDatasetButton.png
      :scale: 50%

   .. figure:: ./img/previewDataset.png
      :scale: 50%



That's it. You can upload any JSON object with any fields and structures. Coming up next, we'll see what that upload
step looks like