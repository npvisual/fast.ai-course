# Practical Deep Learning for Coders : My Journey

Collection of notebooks and other documents generated as a result of following the [fast.ai class](http://course.fast.ai) : Practical Deep Learning for Coders.

##### Table of contents

* [Lesson 2 - Reusing VGG](#lesson2-reusingvgg) : notebook showing how to avoid importing all images to run predictions.
* [Lesson 2 - Linear model]()

<a name="lesson2-reusingvgg"/>

## Lesson 2 Homework : Reusing VGG

### Introduction

[Lesson 2 Homework - Training VGG](Lesson2/Lesson%202%20-%20Training%20VGG.ipynb) is a [Jupyter Notebook](https://jupyter.org) that I created as a hands-on approach to the [fast.ai class](http://course.fast.ai) Lesson 2.  Specifically, the [last part of that lesson](https://youtu.be/e3aM6XTekJc?t=1h29m41s) was somewhat problematic for me.

### Reason for `get_data()` ?

Part of the problem was my lack of understanding for using `get_data()` defined in `utils.py`. The more I read and discovered about it, the more I thought it was completely redundant to the use of batches that's done in that same notebook.

In addition there was a huge amount of memory being taken while running that notebook, regardless of whether or not prediction and training were performed.

### Using batches

So after looking at some of the comments in the [Lesson 2 forum](http://forums.fast.ai/t/lesson-2-discussion/161) I decided to *re-write* the section of the notebook that uses predictions from the VGG model to feed to a single layer linear model. I used `predict_generator()` to run predictions on the batches we already defined and completely dropped the in-memory import of all the images done via `get_data()`.

This worked out pretty well as memory was kept in check and the original intent of the lesson was, in my mind, still preserved.

Have fun going over it ! 

## References and Licenses

As far as my comments and not-so-original code, feel free to use [at will](COPYING.WTFPL). If you want to add attributions, it's always appreciated.

For the original content, please see below for attributions :

* [Lesson 2 Notes](http://wiki.fast.ai/index.php/Lesson_2_Notes) : © fast.ai 2017. All rights reserved.
* [Lesson 2 Video](https://youtu.be/e3aM6XTekJc) : [Creative Commons](https://creativecommons.org/)

Note that I have had a hard time finding license information on the course notes, so I used the copyright show by the fast.ai web site. Please let me know if you know otherwise.
