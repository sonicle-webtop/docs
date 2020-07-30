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

* | ``default.viewmode`` [ columns | compact ]
  | Default view mode used in main messages list. Internally defaults to ``compact``.
  | ``columns``: Classic view with columns.
  | ``compact``: Modern and single column that aggregates all info.
  | @since: 5.6.2

.. _mail-settings-section:

Settings
--------

* | ``attachment.maxfilesize`` [ size-in-bytes ]
  | Maximum size for file attachments. Defaults to `10485760` (10MB).

* | ``message.replyall.stripmyidentities`` [ true | false ]
  | False to disable (in reply to all) recipients removing if matching with user identities. Defaults to `true`.

* | ``message.edit.subject`` [ true | false ]
  | Enable or disable the feature to edit subject of received emails. Defaults to `false`.
  | @since: 5.5.1

* | ``auth.user.strip.domain`` [ true | false ]
  | Do not append domain on mail user, even on schemes like ldap and AD. Defaults to `false`.
  | @since: 5.7.8

.. _mail-sieve-settings-section:

Sieve settings
--------------

* | ``sieve.port`` [ port ]
  | The Sieve daemon port.

.. _mail-external-archiving-settings-section:

External Archiving
------------------

* | ``archiving.external`` [ true | false ]
  | Enable or disable external archiving feature, both on the client and the server scripts. Defaults to false.

* | ``archiving.external.host`` [ hostname ]
  | The hostname of the server hosting the external archive.

* | ``archiving.external.port`` [ port ]
  | The port of the server hosting the external archive.

* | ``archiving.external.protocol`` [ imap | imaps ]
  | The protocol of the server hosting the external archive.

* | ``archiving.external.username`` [ username ]
  | The username of the external archive account

* | ``archiving.external.password`` [ password ]
  | The password of the external archive account

* | ``archiving.external.minage`` [ number-of-days ]
  | The minimum age in days of mails to be considered for archiving. Defaults to 365*5.
