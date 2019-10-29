.. _team:

Team
==========

A team is a predefined group of annotators. When you define a :ref:`taskdefinition` you can assign one or more teams to work on it. 
This ability is commonly used to acheive one (or both) of two goals

1. You'd like to enforce access controls on groups of annotators (Team A can only work on dataset X )
2. You'd like to allocate varying skills and expertise differently. Commonly, you'd assign a team of experts to label a test set and a larger team of laypeople to label the training set 

By default, LightTag comes with a Team called "Everyone". Assigning this team to a task will assign work to all of your annotators, including ones that join after the task was defined. 
