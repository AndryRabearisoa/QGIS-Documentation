.. comment out this Section (by putting '|updatedisclaimer|' on top) if file is not uptodate with release

.. _`offlinedit`:

Offline Editing Plugin
======================


For data collection, it is a common situation to work with a laptop or a cell 
phone offline in the field. Upon returning to the network, the changes need to 
be synchronized with the master data source, e.g. a PostGIS database. If several 
persons are working simultaneously on the same datasets, it is difficult to 
merge the edits by hand, even if people don’t change the same features.

The |offline_editing_copy|:sup:`Offline Editing` Plugin automates the 
synchronisation by copying the content of a datasource (usually PostGIS or 
WFS-T) to a SpatiaLite database and storing the offline edits to dedicated 
tables. After being connected to the network again, it is possible to 
apply the offline edits to the master dataset.

**Using the plugin**

*  Open some vector layers, e.g. from a PostGIS or WFS-T datasource
*  Save it as a project
*  Press the |offline_editing_copy|:sup:`Convert to offline project` icon and select the layers to 
   save. The content of the layers is saved to spatialite tables.
*  Edit the layers offline.
*  After being connected again, upload the changes with the |offline_editing_sync|:sup:`Synchronize` button.

.. _figure_offline_editing_1:

.. only:: html

   **Figure Offline Editing 1:**


.. figure:: /static/user_manual/plugins/create_offline_project.png
   :align: center
   :width: 30em

   Create an offline project from PostGIS or WFS layers 

