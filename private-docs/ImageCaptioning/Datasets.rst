Datasets
++++++++++++++++++++++++++++++++

.. contents:: **Table of Contents**

In this part, we introduce the datasets we used for the image-captioning task.

CLIPfa's datasets
===================================
We have included the datasets which were used for training `sajjadayobi's CLIPfa <https://github.com/sajjjadayobi/CLIPfa>`_ model.

All the datasets were gathered and created by Sajjad Ayoubi and Navid Kanaani. Each of them were translated from other image-captioning datasets into Persian and filtered to include only the proper translations. The code for translation can be found `here. <https://github.com/sajjjadayobi/CLIPfa/blob/main/clipfa/data/translation.py>`_

Flickrfa
------------------
This dataset was created by translating and filtering Flickr30k. It has 32,404 images each associated with one Persian caption.

You can view and download the dataset from `this page <https://www.kaggle.com/datasets/sajjadayobi360/flickrfa>`_ .

This dataset is saved on the public server in a zip file. (path: ~/Hashemi/clipfa_datasets/flickrfa.zip)

cc3mfa & cc3mfav2
-------------

Created by translating and filtering CC3m (Conceptual Captions) and contain 151,235 (in cc3mfa) and 90,809 (cc3mfav2) images with their captions.

Datasets on kaggle: `cc3mfa <https://www.kaggle.com/datasets/sajjadayobi360/cc3mfa>`_ and `cc3mfav2 <https://www.kaggle.com/datasets/sajjadayobi360/cc3mfav2>`_

They're downloaded on the public server. (path: ~/Hashemi/clipfa_datasets/cc3mfa.zip & ~/Hashemi/clipfa_datasets/cc3mfav2.zip)

Coco-Flickr Farsi
-------------

Created by translating and filtering COCO 2017 and Flickr30K. Contains 124,188 images with their captions.

Dataset on kaggle: https://www.kaggle.com/datasets/navidkanaani/coco-flickr-farsi

Downloaded on the public server. (path: ~/Hashemi/clipfa_datasets/coco-flickr-farsi.zip)
