=============
Release notes
=============

WebTop release 5

Release 5.3.1 - september 5, 2018
---------------------------------

**Bug Fixes:**

- [mail] Some text/plain mails with non utf-8 charset may not display correctly [ #554 ]
- [mail] Sending or discarding a new message may sometime prompt errors [ #555 ]

Release 5.3.0 - july 27, 2018
-----------------------------

**New Features:**

- [core] WebRTC Voice / Video call on chat. See :ref:`webrtc-settings-section` [ #501 ]
- [core] Improve chat UI [ #514 ]
- [core] New header toolbar layout (icons scale, centered searchbox, etc) [ #535 ]
- [core] New SMTP setting to support starttls and user authentication. See :ref:`smtp-settings-section` [ #537 ]
- [admin] Centralized user options management from admin panel. See :ref:`core-usersettings-section` [ #497 ]
- [mail] Favorites folder and management [ #495 ]
- [mail] Autosave on drafts folder [ #517 ]
- [mail] Add support to subject and body parameters in mailto urls clicked inside mail view [ #506 ]
- [mail] New option for no mailcard on reply or forward [ #525 ]
- [mail] Reorganize UI toolbars and buttons [ #534 ]
- [mail] Paste of emails from Excel column to Message Editor recipients [ #508 ]
- [calendar] Add "receive notification on external update" option on calendars [ #502 ]
- [calendar] Enable attendees management within recurring events [ #509 ]
- [calendar] Remote calendars auto-sync. See :ref:`calendar-remote-settings-section` [ #522 ]
- [contacts] Remote categories auto-sync. See :ref:`category-remote-settings-section` [ #523 ]
- [contacts] Contacts Import LDIF format [ #505 ]
- [contacts] SMS Send (Rest API SMSHosting e Twilio). See :ref:`SMS-settings-section` [ #528 ]
- [mattermost] New Mattermost integration service [ #533 ]

**Bug Fixes:**

- [core] LDAP CertificateException error on ojdk 1.8.0.181 [ #539 ]
- [mail] Possible heavy load on inboxes with ten thousands of unseen emails [ #538 ]
- [mail] Forwarding messages with attached eml doubles final attachments [ #532 ]
- [mail] Creating a main folder with name "root" causes the folders tree go crazy [ #510 ]
- [mail] Emails that contain images become already read [ #493 ]
- [mail] Labels with space in the name are not applied [ #484 ]
- [mail] The modification of a custom label is not applied to the emails [ #483 ]
- [cloud] Duplicate folders in the connected nextcloud resource [ #519 ]
- [cloud] Webdav folders are duplicated if name contains encoded whitespaces [ #520 ]


Release 5.2.3 - july 11, 2018
-----------------------------

**Bug Fixes:**

- [dav-server] Parsing exceptions on some CentOS installations [ #516 ]
- [mail] Subject is not saved during send for later suggestions [ #515 ]
- [core] Java8 breaks mediaType guessing order in mimeutil [ #513 ]
- [core] Calls to public services override user subject associated to execution thread [ #512 ]
- [mail] Can not use the action marks as seen in the filters [ #511 ]
- [mail] Possible deadlocks when having many many folders, caused by JavaMail standard library [ #518 ]


Release 5.2.2 - june 11, 2018
-----------------------------

**Bug Fixes:**

- [mail] Fix bug attaching two times the same filename via cloud [ #496 ]
- [core] Workaround a Chrome bug while downloading links of filenames containing a comma [ #482 ]
- [core] HTMLEditor bullet/numbered list fix by change on TinyMCE editor mode and styles [ #470 ]
- [core] Fix infinite grid bug on Chrome while paging up [ #343 ]
- [core] Logging level of athmosphere client-side events is now set to 'debug' (this should limit logging in some situations)
- [contacts] Fix missing version bump in init-db scripts
- [calendar] Fix missing version bump in init-db scripts
- [calendar] Event invitation emails are now sent even if the event is synchronized using CalDAV
- [calendar] Avoid sending invitation email to the organizer himself (OpenSync on Android adds the organizer as attendee by default)
- [dav-server] Fix PHP function for dumping headers missing on NethServer


Release 5.2.0 - may 30, 2018
----------------------------

**New Features:**
- WebTop DAV Server implementation through SabreDAV. See :ref:`dav-server-section` and :ref:`dav-clients-notes-section` [ #485 ]
- NethVoice PBX integration with new specific core configuration. See :ref:`PBX-settings-section` [ #475 ]
- New rrule based calendar recurrences and new full featured GUI [ #486 ]
- Contacts feature one click on phone numbers and context menus to start the configured PBX call [ #476 ]
- Contacts feature one click on email column to start mail composition [ #474 ]
- Domain users are automatically added as a "webtop" contacts source when suggesting recipients [ #457 ]
- Completed implementation of What's New framework, showing changes for the user upon version upgrades and allowing to browse all history [ #463 ]
- A new action on the email tree context menu allows to upload an eml file to the right-clicked folder [ #462 ]
- Mail now features a breadcrumb on top of the messages grid for quick folders navigation [ #480 ]
- Invitation requests are now rendered only with WebTop internal management UI, any attached html part is ignored to avoid confusion [ #455 ]
- Firefox now correctly remembers succesful login names [ #458 ]
- On Cloud, a new "refresh" action allows to reload folders and files [ #385 ]
- Creating new emails, images attached with spaces in the name are not displayed [ #461 ]

**New Requirements:**

- This release requires Java 1.8 as the main Tomcat JVM

**Bug Fixes:**

- Using the "Neptune" theme, Persons and Mail folders can not be seen in the interactive search [ #372 ]
- The partial search in the phonebook in the mail composition does not work [ #373 ]
- New folders on google drive do not appear on the app [ #384 ]
- Scheduled emails are no more processed [ #467 ]
- Mails with wrong attachments names may have spaces at the end, causing problems [ #471 ]


Release 5.1.9 - may 04, 2018
----------------------------

**Bug Fixes:**

- Calendar reminders via email do not work [ #464 ]
- Moving an event breaks reminder notification [ #465 ]


Release 5.1.8 - april 19, 2018
------------------------------

**New Features:**

- New global mail configuration option allows to disable grid row preview as a default option for everyone. See :ref:`mail-defaults-settings-section` [ #468 ]
- Saving a draft now overwrites previous one, adding a specific action to save as new [ #453 ]
- Mail now saves layout of folders, columns positions and widths [ #452 ]
- Contacts now saves layout of columns positions and widths [ #451 ]
- Emoticon in Message Editor [ #379 ]

**Bug Fixes:**

- Contacts shouldn't allow to send contact details, when the contact is a list [ #355 ]
- BASE64Decoder Error forwarding an email [ #365 ]
- With firefox it is not possible to change the color of the text of the mailcard [ #366 ]
- Cloud folder rename function does not work [ #367 ]
- Sometimes grid preview of recent mails may fail rendering [ #367 ]
- Notification mail with unrecognized characters [ #369 ]
- Unsupported encoding error: unicode-1-1-utf-7 [ #370 ]
- Case-insensitive authentication with AD is not fully functional [ #371 ]
- Moving the window of a mail too high it is no longer possible to close it [ #374 ]
- Autosave restore message no longer displayed [ #375 ]
- With AD username with mixed case letters, account sharing does not work [ #376 ]
- With AD username with mixed case letters, account sharing does not work [ #377 ]
- Some events received as ICS attachments are not imported [ #380 ]
- Unsupported encoding error: cp-850 [ #381 ]
- Reply to emails with unencoded international characters may cause errors [ #454 ]
