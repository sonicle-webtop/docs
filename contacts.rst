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
  | Default anniversary reminders delivery mode. Internally defaults to ``app``.
  | ``none``: Off.
  | ``app``: Reminers are displayed in WebTop application.
  | ``email``: Reminders are sent by email.

* | ``default.category.sync`` [ O | R | W ]
  | Default synchronization status for new contacts categories. Internally defaults to ``O``.
  | ``O``: Off, not active.
  | ``R``: Enabled, devices can only read.
  | ``W``: Enabled, devices can read and write.

* | ``default.view`` [ work | home | list ]
  | Default view mode used in main contacts list. Internally defaults to ``work``.
  | ``work``: Both contacts and contacts list are listed, displaying work related fields.
  | ``home``: Both contacts and contacts list are listed, displaying home related fields.
  | ``list``: Only contacts list are listed.
  | @since: 5.5.0

* | ``default.showby`` [ fnln | lnfn | dn ]
  | Default field used for displaying contacts. Internally defaults to ``dn``.
  | ``fnln``: Contact's first-name & last-name.
  | ``lnfn``: Contact's last-name & first-name.
  | ``dn``: Contact's display-name.
  | @since: 5.7.0

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

.. _contacts-mailchimp-settings-section:

Mailchimp Settings
------------------

* | ``mailchimp.apikey`` [ string ]
  | The global Mailchimp API Key for Mailchimp integration.
  | Requires a valid license.
  | @since: 5.11.1
