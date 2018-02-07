.. _data_prep:

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


That's it. You can upload any JSON object with any fields and structures. Coming up next, we'll see what that upload
step looks like