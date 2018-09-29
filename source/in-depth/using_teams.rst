WORKING WITH TEAMS
==================

As your annotation projects grow in scope and complexity you'll want to manage seperate teams of annotators. Some
common use cases include

* Enforcing access control policies on restricted datasets to qualified personsel only.
* Assigning high-cost experts to work on evalutation data while assigning lower cost advisors to work on training data.
* Grouping together annotators based on skills such as language or domain familiarity.

One or more teams is assigned to a :ref:`Task<taskdefinition>`. An annotator will only be shown from a task her team is assigned
to.


Defining a Team
---------------

When you start, LightTag will autoamtically define an "Everyone" team that all annotators fall into by default.
If you'd like to create a new team Go to Manager->Projects->Add Team as shown below

   .. figure:: adding_teams.gif
      :scale: 200 %
      :alt: Defining a new team
      :align: center

      Defining a new team


Assigning a team to a task
-----------------------

Once you've defined a team, you can assign it to work on a :ref:`Task<taskdefinition>`. In the UI this is done by defining
a task definition as shown below

   .. figure:: add_team_to_task.gif
      :scale: 200 %
      :alt: Defining a new team
      :align: center

      Assigning one or more teams to a task
