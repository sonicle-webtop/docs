========
Calendar
========

WebTop Calendar Service

Global calendar configuration settings
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

.. _calendar-dav-settings-section:

DAV Settings
------------------------
* | ``dav.calendar.delete.enabled`` [ true | false ]
  | Enable/Disable calendar deletions through DAV rest-api interface.
