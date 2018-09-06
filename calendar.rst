========
Calendar
========

WebTop Calendar Service

Global Calendar configuration settings
######################################

Global configuration settings can be changed using the admin interface, as explained in the :ref:`core-settings-section`

.. _calendar-default-settings-section:

Defaults Settings
-----------------

* | ``default.view`` [ d | w5 | w | dw | m ]
  | Default synchronization status for new calendar folders.

* | ``default.workday.start`` [ hours ]
  | Default workday hours start time.

* | ``default.workday.end`` [ hours ]
  | Default workday hours end time.

* | ``default.event.reminder.delivery`` [ app | email ]
  | Default reminders delivery mode.

* | ``default.calendar.sync`` [ O | R | W ]
  | Default synchronization status for new calendar folder: off, read or write.

.. _calendar-event-settings-section:

Event Settings
--------------

* | ``event.statistic.fields.visible`` [ true | false ]
  | Show or hide statistic fields in event window. Defaults to true.

.. _calendar-remote-settings-section:

Remote Calendars Settings
-------------------------

* | ``calendar.remote.autosync.enabled`` [ true | false ]
  | Enable/Disable remote calendars auto-sync functionality. Defaults to ``false``.
  | @since: 5.3.0

* | ``calendar.remote.autosync.onlywhenonline`` [ true | false ]
  | Enable/Disable remote auto-sync only when calendar's owner is online. Defaults to ``true``.
  | @since: 5.3.0

.. _calendar-dav-settings-section:

DAV Settings
------------

* | ``dav.calendar.delete.enabled`` [ true | false ]
  | Enable/Disable calendar deletions through DAV rest-api interface. Defaults to ``false``.
  | @since: 5.2.0
