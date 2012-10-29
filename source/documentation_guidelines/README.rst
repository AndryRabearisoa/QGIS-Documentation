
.. _QGIS-documentation-guidelines:

************************
Documentation Guidelines
************************

Introduction
============

These are guidelines to use for latex to rst conversion.

There is also information about general use of rst in QGIS documenation.

See also: http://sphinx.pocoo.org/markup/inline.html or convention.rst file.

In general, when creating rst documentation for the QGIS project, please follow 
the `Python documentation style guide lines 
<http://docs.python.org/devguide/documenting.html>`_.


Using headlines
===============

Adding new haedlines, you should use following styles for chapter, section, 
subsection and minisec.

headlines

::

   ********
   Chapter
   ********

   Section
   =======

   Subsection
   ----------

   Minisec
   .......


Inline tags
===========

* Shorcut keyboard:

  ::

     :kbd:`ctrl B`
  
  will show :kbd:`Ctrl B`

* Menu gui

  ::
  	
     :menuselection:`menu --> submenu`

* Filename

  ::
  	
     :file:`README.rst`

* Icon with popup text belonging to Icon

  ::
  	
     |icon| :sup:`popup_text` 
  	
  (see `image`_ below).

* Dialog and Tab title

  ::
  	
     :guilabel:`title`

* User text

  ::
  	
     ``label``

Footnotes
=========

This is for creating a footnote

::
	
   blabla [1]_
	
Which will point to:

   .. [1] Updates of core plugins

.. _my_anchor:

Label/reference
===============

This is used to create a reference somewhere

::
	
   .. _my_anchor:

   Label/reference
   ===============

This will call the reference in the **same page**

::
	
   see my_anchor_ for more information. Notice how it will jump to 
   the following line/thing following the 'anchor'. 
   Normally to declare this label you do not need to use apastroph's but 
   you do need to use empty lines before and after the anchor. If you use 
   :ref:`my_anchor` it will display the caption instead 
   (In this case the title of this section!)

So reference 1 (my_anchor_) and reference 2 :ref:`my_anchor`
   
Because the reference often displays a full caption, there is not really 
the need to use the word section

::

   see :ref:`my_anchor`


.. _`image`:

Figure and image
=================


Figure

::
	
   .. _figure_readme_1:

   .. only:: html

      **Figure Readme 1:**

   .. figure:: ../static/common/qgislogo.png
      :width: 20 em
      :align: center

      A caption: A logo I like


The result looks like this:

.. _figure_readme_1:

.. only:: html

   **Figure Readme 1:**

.. figure:: ../static/common/qgislogo.png
   :width: 20 em
   :align: center

   A caption: A logo I like

Use ``.. only:: html`` to make the number to the figure (**Figure Readme 1**) 
visible only in the html files.
The scripts will insert an automatical generated number before the caption of 
the figure in pdf.

To use a caption (see My caption) just insert indented text after a blank line 
in the figure block.

Referencing to the figure can be done in two ways first using the reference 
label like this

::

   (see Figure_Readme_1_). 


It will show the anchor Figure_Readme_1_. You can use uppercase if you want.
It can be used in the same :file:`.rst` document but not in other .rst 
documents.

You can not use the reference like this anymore, because in html the reference
to the caption is lost (it now refers to the place before **Figure Readme 1:** 

::

   see :ref:`figure_readme_1`, does not work due to the lost reference to 
   the caption of the figure, this is not a 'bug' but a choice we made!


Tables
------

a simple table

::

   =======  =======  =======
   x        y        z
   =======  =======  =======
   1        2        3
   2        4        
   =======  =======  =======

Use a ``\`` followed by an empty space ' ' to leave an empty space.

You can also use more complicated tables by drawing them using refences and all

::

   .. _my_drawn_table_1:

   +---------------+--------------------+
   | Windows       | Mac OSX            |
   +---------------+--------------------+
   | |win|         | |osx|              |
   +---------------+--------------------+
   | and of course not to forget |nix|  |
   +------------------------------------+

   My drawn table, mind you this is unfortunately not regarded a caption 

   You can reference to it like this my_drawn_table_1_. 

The result:

.. _my_drawn_table_1:

+---------------+--------------------+
| Windows       | Mac OSX            |
+---------------+--------------------+
| |win|         | |osx|              |
+---------------+--------------------+
| and of course not to forget |nix|  |
+------------------------------------+

My drawn table, mind you this is unfortunately not regarded a caption 

You can reference to it like this my_drawn_table_1_. 



Pictures
--------

Image

::
	
   .. image:: ../static/common/qgislogo.png
      :width: 10 em


Replacement
-----------

You can put an image inside text or add an alias to use everywhere. To use an image 
inside a paragraph, just create an alias somewhere

::
	
   .. |nice_logo| image:: ../static/common/qgislogo.png
                  :width: 2 em

and call it in your paragraph

::

   my paragraph begins here with a nice logo |nice_logo|.

Here is how this example become:

.. |nice_logo| image:: ../static/common/qgislogo.png
               :width: 2 em

my paragraph begins here with a nice logo |nice_logo|.


Index
=====
Several index tag exists in RST. Here the easiest one

::
	
   .. index:: `my index`


