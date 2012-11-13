.. comment out this disclaimer (by putting '.. ' in front of it) if file is uptodate with release

|updatedisclaimer|

.. index:: Field_Calculator, Calculator_Field, Derived_Fields

.. _vector_field_calculator:

Field Calculator
================

The |mActionCalculateField| :sup:`Field Calculator` button in the attribute 
table allows to perform calculations on basis of existing attribute values or 
defined functions, e.g to calculate length or area of geometry features. The 
results can be written to a new attribute column or it can be used to update 
values in an already existing column. The creation of new attribute fields is 
currently only possible in PostGIS and with OGR formats, if GDAL version is 
>= 1.6.0.

You have to bring the vector layer in editing mode, before you can click on 
the field calculator icon to open the dialog (see figure_attributes_3_). In 
the dialog you first have to select whether you want to only update selected features,
create a new attribute field where the results of the calculation will be added or update an existing 
field.

.. _figure_attributes_3:

.. only:: html
   
   **Figure Attributes 3:** 

.. figure:: /static/user_manual/working_with_vector/fieldcalculator.png
   :width: 50em
   :align: center

   Field Calculator |nix|

If you choose to add a new field, you need to enter a field name, a field type
(integer, real or string), the total field width, and the field precision (see figure_attributes_3_) .
For example, if you choose a field width of 10 and a field precision of 3 it 
means you have 6 signs before the dot, then the dot and another 3 signs for 
the precision.

The **Function List** contains functions as well as fields and values. View the help function in the **Selected Function Help**. In **Expression** you see the calculation expressions you create with the **Function List**. The most commonly used operators, see **Operators**.

In the *Function List**, click on ``>-Fields and Values`` to view all attributes of the attribute table
to be searched. To add an attribute to the Field calculator **Expression** field, 
double click its name in the Fields and Values list. Generally you can use the various 
fields, values and functions to construct the calculation expression or you 
can just type it into the box.

To display the values ​​of a field, you just right click on the appropriate field. 
You can choose between :guilabel:`Load top 10 unique values` and :guilabel:`Load all unique values`.
On the right side opens the **Field Values** list with the unique values.
To add a value to the Field calculator **Expression** box, double click its name in 
the Values list.

The :guilabel:`>-Operators`, :guilabel:`>-Math`, :guilabel:`>-Conversions`, :guilabel:`>-String`, :guilabel:`>-Geometry` and :guilabel`>-Record` menu provides several functions.
In :guilabel:`>-Operators` you find mathematical operators.
Find :guilabel:`>-Math` for mathematical functions.
The :guilabel:`>-Conversions` group contains functions that convert one data type to another.
The :guilabel:`>-String` group provides functions for data strings.
In the :guilabel:`>-Geometry` group you find functions for geometry objects.
With :guilabel`>-Record` group functions you can add a numeration to your data set. 
To add an operator to the Field calculator **Expression** box, click on the > and then double klick the function. 

A short example illustrates how the field calculator works. We want to 
calculate the length of the ``railroads`` layer from the 
:file:`QGIS_example_dataset`:



#. Load the Shapefile *railroads.shp* in |qg| and open the 
   :guilabel:`Attribute Table` dialog.
#. Click on |mActionToggleEditing| :sup:`Toggle editing mode` and open the 
   |mActionCalculateField| :sup:`Field Calculator` dialog.
#. Unselect the |checkbox| :guilabel:`Update existing field` checkbox to 
   enable the new field box.
#. Add ``length`` as output field name, ``real`` as output field type and 
   define output field width 10 and a precision of 3.
#. Now click on Operator ``length`` to add it as \$length into the field 
   calculator expression box and click **[Ok]**.



Due to limited space screen, not all the operators are available through 
the buttons. They are all listed in the following table.

.. index:: Field_Calculator_Operators

===================================  ========================================================
List of operators supported by the field calculator
---------------------------------------------------------------------------------------------
String                               Literal string value
===================================  ========================================================
NULL                                 null value
sqrt(*a*)                            square root
sin(*a*)                             sinus of *a* 
cos(*a*)                             cosinus of *b*
tan(*a*)  			     tangens of *a*
asin(*a*) 			     arcussinus of *a*
acos(*a*) 			     arcuscosinus of *a* 
atan(*a*) 			     arcustangens of *a*
to int(*a*) 			     convert string *a* to integer
to real(*a*) 			     convert string *a* to real
to string(*a*)			     convert number *a* to string
lower(*a*)    			     convert string *a* to lower case
upper(*a*)			     convert string *a* to upper case
length(*a*)			     length of string *a*
atan2(y,x)  			     arcustangens of y/x using the signs of the two arguments 
                                     to determine the quadrant of the result
replace(*a*, replacethis, withthat)  replace *replacethis* with *withthat* in string *a*
substr(*a*,from,len)                 len characters of string *a* starting from from 
                                     (first character index is 1)
*a* || *b*                           concatenate strings *a* and *b*
\$rownum    			     number current row
\$area  			     area of polygon
\$perimeter			     perimeter of polygon
\$length   			     length of line
\$id     			     feature id
\$x  				     x coordinate of point
\$y  				     y coordinate of point
*a* |wedge| *b*  		     *a* raised to the power of *b* 
*a* \* *b*        		     *a* multiplied by *b*
*a* / *b*  			     *a* divided by *b* 
*a* + *b*  			     *a* plus *b*
*a* - *b*  			     *a* minus *b*
\+ *a*     			     positive sign
\- *a*  			     negative value of *a*
===================================  ========================================================

   List of operators for the field calculator
