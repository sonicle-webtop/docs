========
Contacts
========

WebTop Contacts Service

Global Contacts configuration settings
######################################

Global configuration settings can be changed using the admin interface, as explained in the :ref:`core-settings-section`

.. _contacts-default-settings-section:

Settings (defaults)
-------------------

* | ``default.anniversary.reminder.delivery`` [ none | app | email ]
  | Default anniversary reminders delivery mode.

* | ``default.category.sync`` [ O | R | W ]
  | Default synchronization status for new contacts categories: off, read or write.

.. _category-remote-settings-section:

Remote Categories Settings
--------------------------

* | ``category.remote.autosync.enabled`` [ true | false ]
  | Enable/Disable remote categories auto-sync functionality. Defaults to ``false``.
  | @since: 5.3.0

* | ``category.remote.autosync.onlywhenonline`` [ true | false ]
  | Enable/Disable remote auto-sync only when category's owner is online. Defaults to ``true``.
  | @since: 5.3.0

.. _contacts-dav-settings-section:

DAV Settings
------------

* | ``dav.addressbook.delete.enabled`` [ true | false ]
  | Enable/Disable addressbook deletions through DAV rest-api interface. Defaults to ``false``.
  | @since: 5.2.0
