
.. _coordcapt:

Coordinate Capture Plugin
=========================


The coordinate capture plugin is easy to use and provides the 
ability to display coordinates on the map canvas for two 
selected Coordinate Reference Systems (CRS).

.. _figure_coordinate_capture_1:
.. figure:: img/en/plugins_coordinate_capture/coordinate_capture_dialog.png
   :align: center
   :width: 20em

   Figure Coordinate Capture 1: Coordinate Capture Plugin |nix|

#. Start QGIS, select |mActionOptions| :guilabel:`Project Properties` from 
   the :guilabel:`Settings` (KDE, Windows) or :guilabel:`File` (Gnome, OSX) menu 
   and click on the :guilabel:`Projection` tab. As an alternative you 
   you can also click on the |mIconProjectionEnabled| :sup:`projector` icon in 
   the lower right-hand corner of the statusbar.
#. Click on the |checkbox| `Enable on the fly projection` checkbox and select 
   a projected coordinate system of your choice (see also :ref:`label_projections`).
#. Load the coordinate capture plugin in the Plugin Manager (see 
   :ref:`load_core_plugin`) and ensure that the dialog is visible by going 
   to :menuselection:`View --> Panels` and ensuring that 
   |checkbox| `Coordinate Capture` is enabled. 
   The cordinate capture dialog appears as shown in Figure figure_coordinate_capture_1_.
#. Click on the |geographic| :sup:`Click to the select the CRS to use for 
   coordinate display` icon and select a different CRS from the one you selected above.
#. To start capturing coordinates, click on **[Start capture]**. You can now 
   click anywhere on the map canvas and the plugin will show the coordinates for both 
   of your selected CRS.
#. To enable mouse coordinate tracking click the |tracking| :sup:`mouse tracking` icon.
#. You can also copy selected coordinates to the clipboard.

