Managing Work
=====================
As your project progresses you'll want to add new datasets, schemas tasks and teams to work on them. 
You can do this through the :doc:`./api` or via the administrative GUI which is described here. 

   .. figure:: manager_screen.gif
      :scale: 200 %
      :alt: Manager overview
      :align: center

      Manager overview

Accessing the management screen
-------------------------------
To reach the management screen go to Manager in the top menu 
project

   .. figure:: accessing_management_screen.gif
      :scale: 200 %
      :alt: Manager overview
      :align: center

      Accessing

You'll see a 

* list of the :ref:`taskdefinition` you've already defined
* Buttons to add a :ref:`taskdefinition`, :ref:`dataset` or :ref:`schema`
* Buttons to activate or deactivate a :ref:`taskdefinition`
* Buttons to adjust the priority of :ref:`taskdefinition`

Disabling a Task
------------------

Sometimes we want to stop work on a particular task. To achieve this set that tasks
status to deactivate by pressing the button as shown below. To reactivate the task simply click again. 

Deactivating a task will prevent LightTag from issuing further work for that task until you reactivate it.

   .. figure:: disabling.gif
      :scale: 200 %
      :alt: Disabling a task
      :align: center

      Disabling a task

Adjusting Priorities
--------------------
Instead of disabling tasks, you can also adjust their priority. LightTag will always issue the highest priority work first
so you can use this feature to set a queue or to make sure that rush work will be done immediately. 
To adjust a tasks priority press the send to top button  as shown below


   .. figure:: setting_priority.gif
      :scale: 200 %
      :alt: Adjusting Priorities
      :align: center

      Adjusting Priorities

.. DANGER::
   LightTag will not remove work you have on going when you change a task's status or priority. That means that if you loaded a task for annotation it will
   not be removed and if you go to the Annotation screen it will still be there. 
   To switch to a task with the current highest priority you will have to refresh your screen. We are working on a more convenient solution. 

Adding Datasets, Schemas and Tasks
-----------------------------------

The management screen allows you to add new datasets, schemas and tasks just like in the  :ref:`onboarding process<first_schema>`. 

   .. figure:: adding_new_stuff.gif
      :scale: 200 %
      :alt: Adding new Stuff
      :align: center

      Adding things
