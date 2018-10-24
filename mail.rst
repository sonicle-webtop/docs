====
Mail
====

WebTop Mail Service

Global Mail configuration settings
##################################

Global configuration settings can be changed using the admin interface, as explained in the :ref:`core-settings-section`

.. _mail-defaults-settings-section:

Settings (defaults)
-------------------

* | ``default.ingrid.preview`` [ true | false ]
  | Disable grid row preview for everyone, default value is false.

* | ``default.upcoming.events.show`` [ true | false ]
  | Activate a view showing all upcoming events by default.

* | ``default.upcoming.tasks.show`` [ true | false ]
  | Activate a view showing all upcoming tasks by default.

.. _mail-settings-section:

Settings
--------

* | ``attachment.maxfilesize`` [ size-in-bytes ]
  | Maximum size for file attachments. Defaults to `10485760` (10MB).

* | ``message.replyall.stripmyidentities`` [ true | false ]
  | False to disable (in reply to all) recipients removing if matching with user identities. Defaults to `true`.

.. _mail-sieve-settings-section:

Sieve settings
--------------

* | ``sieve.port`` [ port ]
  | The Sieve daemon port.
