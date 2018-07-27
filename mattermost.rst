==========
Mattermost
==========

WebTop Mattermost service module

Prerequisites
#############

Mattermost Web application is embedded using iframe mode, so you need a little configuration in order to circumvent some security features.

Mainly you need to strip out the security policy settings in the HTTP headers that can be found in any response coming from the Mattermost server.
This is the way you could achieve this point using Apache HTTP Server::

  <VirtualHost *:*>
    # Strip security headers
    Header unset Content-Security-Policy
    Header unset X-Frame-Options
  </VirtualHost>

In some cases you need also to edit the main HTML template to remove the anti-Clickjacking security feature.
Please refer to the official Integration Guide `section <https://docs.mattermost.com/integrations/embedding.html#embedding-mattermost-in-web-applications-using-an-iframe>`_ for any further info.

Mattermost Web application is embedded using the iframe mode, so you must fulfill the instructions
described `here <https://docs.mattermost.com/integrations/embedding.html#embedding-mattermost-in-web-applications-using-an-iframe>`_ in the official Integration Guide.

Global Mattermost configuration settings
########################################

Global configuration settings can be changed using the admin interface, as explained in the :ref:`core-settings-section`

.. _mattermost-embedding-settings-section:

Embedding settings
------------------

* | ``url``
  | URL that targets mattermost Web application on your server.
