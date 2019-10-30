Relations
=========

Sometimes you'll want to annotate relationships between various entities in your text.

How Relations work in LightTag
-------------------------------

UI
___________

LightTag's relationship interface may be different from what you are used to. Whereas most other systems allow you to draw
arcs between tokens, LightTag allows you to drag and drop tokens to form trees (The graph theory kind). You can also
drag "trees" onto each other to form more complex ones. This allows you to gradually build complex annotaitons from simple
building blocks.

   .. figure:: img/drag_relations.gif
      :alt: Drag tokens and subtrees to form complex relationships
      :align: center

      Drag tokens and subtrees to form complex relationships

Data
____
As a project manager it may be useful to think of how LightTag structures the relations data, as well as how your own
downstream models may do so. LightTag considers relationships to constitute a tree with directed edges. A node in the tree
can be any token in the original text as well as "concepts" that the user defined but don't explicitly appear in the text.

It's often necessary or convenient to specify how to nodes modify each other. For example, in the phrase "two coke's please"
the word "two" quantifies the word "coke's". If each of the words is a node in our tree, than obviously we have an edge between them.
Additionally, we can specify to particular way in which they relate by adding a label to the edge. This is the relation type.





Specifying Relation Types
-------------------------
Often you'll want to specify to type of the relationship between a parent and child. To do so, simply go to the Types
section on the left side of the screen, select the relationtype you want and double click on the relevant node.

Dependency, Phrase Structure and CoReference Annotations
--------------------------------------------------------

Relations for non-linguistic use cases
---------------------------------------

