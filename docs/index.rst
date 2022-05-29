.. Documentation documentation master file, created by
   sphinx-quickstart on Fri Apr 29 21:01:27 2022.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Documentation's documentation!
=========================================

**this is Bold text**




*italic text*



`This is Hyperlink to Google <https://Google.com>`_

``Code Word``

This Text contains **Bold \* Example \`** 


.. 
   table of contents tree
   toctree gets rendered as a list of hyperlinks, and this allows you to navigate to the new page you just created
   maxdepth option may be given to indicate the depth of the tree

   glob flag option
   All entries are then matched against the list of available documents, and matches are inserted into the list alphabetically

.. toctree::
   :maxdepth: 3
   :hidden:
   :caption: Cloud:
   :glob:

   usage
   Cloud/*

.. toctree::
   :hidden:
   :caption: Documentation:
   :glob:

   Documentation/*

.. toctree::
   :maxdepth: 3
   :caption: Application:
   :hidden:

   Application/app1


.. toctree::
   :maxdepth: 3
   :caption: Fake News:
   :hidden:

   FakeNews/TelegramBot


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
