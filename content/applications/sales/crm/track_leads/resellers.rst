=========
Resellers
=========

Within Odoo's *CRM* app, leads can be forwarded to resellers (or partners). Leads can be manually
assigned, or can be automatically assigned based on the resellers designated *level*, and location.

Configuration
=============

To utilize the reseller features, the *Resellers* module first needs to be installed. Navigate to
the :menuselection:`Apps` application, and remove the :guilabel:`Apps` filter from the
:guilabel:`Search...` bar. Then search for `Resellers`.

.. image:: resellers/resellers-module.png
   :align: center
   :alt: The resellers module in Odoo.

After the module is installed, navigate to the :menuselection:`CRM app`. Under the
:menuselection:`Configuration` menu is a new section, titled *Resellers*.

Partner levels
==============

Partner *levels* are used to differentiate between various resellers. To view the partner levels,
navigate to :menuselection:`CRM app --> Configuration --> Partner Levels`.
Three levels are created by default in the *CRM* app:

- :guilabel:`Gold`
- :guilabel:`Silver`
- :guilabel:`Bronze`

New levels can be added, as needed, and the existing levels can be edited and renamed, if desired.

Level weight
------------

Level weight is used to decide the probability a partner to be assigned a lead or opportunity. The
level weight should be a numerical value, greater than zero. If the weight is zero, no leads are
assigned.

.. tip::
   Level weight can be assigned on an individual contact record. The weight assigned on the
   individual record overwrites the default weight assigned on the level configuration form.

Partner activations
===================

After partner levels and partner activations have been configured, individual partner records can be
activated.


