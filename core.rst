====
Core
====

WebTop Core Services

|

.. _core-settings-section:

Global core configuration settings
##################################

|

Global and per-domain configuration settings can be setup using the admin interface, using the admin user. Click on properties to show the current settings, grouped by service. You may directly edit the settings and/or add new ones as specified in the documentation. Missing settings will default to a specified value.

|

.. _PBX-settings-section:

PBX Settings
------------

``pbx.provider`` [ nethvoice ]

PBX provider name. Currently only NethVoice is supported.


``pbx.provider.nethvoice.webrest.url`` [ nethvoice-base-url-to-webrest ]

Specifies the NethVoice base url to access its webrest APIs