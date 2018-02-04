What is LightTag
================

LightTag is a tool and platform to manage and execute text annotation projects. As NLP pemeates our world we need
to collect more labeled data faster. Unfortunately, we don't just need more and fast, we also need our data to be good.

Building the requisite infrastructure and processes to ensure a fast paced and high quality annotation project is a non
trivial undertaking and maintaining that infrastructure is a dedicated resource drain on your team. LightTag is a ready
to go solution that your team can consume on premise or hosted so that you can focus on getting data.

LightTag is comprised of five layers, each of which optimizes a part of the overall annotation flow.


1. UI & UX.
    We provide a user interface that is optimized for both your annotators efficiency and their stamina.
   .. figure:: basic_annotation.gif
       :scale: 50 %
       :alt: Example of annotation
       :align: right

2. Client Server:
    You want to have a team annotate. LightTag provides the infrastructure to let as many annotators as you need work concurrently.
    No installation required.
3. Quality Data by design:
    When building annotating a new dataset you have no way of knowing the quality of your annotations outside of comparing
    the work of two annotators. To achieve this you must make sure that at least two annotators annotated the same document.
    LightTag automates this process for you, ensuring that your annotators are always working on the right document to
    maximize your understanding of the data's quality.
   .. figure:: interAnnoAgg.jpeg
       :scale: 75 %
       :alt: Inter-annotator agreement
       :align: right
4. Metrics.
    LightTag provides the insights you need to know in order to manage your annotation projects. Want to know how many
    annotations a day your team generates? Which annotators tend to disagree with their colleagues? What tags in your
    schema are confusing your team ? LightTag shows you these metrics out of the box, allowing you to detect errors in
    the annotation project when they begin, instead of when you put your models into production.
5. Automation.
    LightTag allows you to upload pre trained models and dictionaries, changing your annotators work to simple decisions.
    Concurrently, you can configure LightTag to learn a custom model for your task, and supply suggestions to your
    annotators based on what LightTag has learned.
   .. figure:: suggestions_anim.gif
      :scale: 50 %
      :alt: Example of suggestions
      :align: center


Also

