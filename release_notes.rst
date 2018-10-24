=============
Release notes
=============

WebTop release 5

Release 5.4.2 - october 24, 2018
---------------------------------

**New Features:**

- [mail] Avoid removing recipients equal to my identities during ReplyToAll [ #603 ]

**Bug Fixes:**

- [contacts] Contacts list virtual address is not expanded anymore [ #602 ]
- [contacts] The search result is not updated by deleting the key [ #591 ]

Release 5.4.1 - october 12, 2018
---------------------------------

**New Features:**

- [calendar] Add support to reminder for recurring events [ #590 ]

**Bug Fixes:**

- [mail] Alternate root doesn't work correctly [ #597 ]
- [calendar] Sometimes recurring modification is applied on wrong target[ #594 ]
- [core] The account email settings can not be changed from the admin panel [ #593 ]
- [core] Error in identity management via admin panel [ #592 ]
- [mail] No message list when quota command is not supported by imap server [ #587 ]
- [calendar] DB integrity error when inserting an event from CalDAV server [ #586 ]

Release 5.4.0 - october 2, 2018
-------------------------------

**New Features:**

- [mail] Show quota for mailbox [ #574 ]
- [core] Optimized layout for tablet experience. See :ref:`other-tablet-section` [ #571 ]
- [calendar] Add attachments support on Events [ #558 ]
- [contacts] Add attachments support on Contacts [ #557 ]
- [tasks] Add attachments support on Tasks [ #556 ]
- [core] OnlyOffice integration. See :ref:`doc-server-section` [ #550 ]
- [mail] OnlyOffice integration support on attachments [ #552 ]
- [cloud] OnlyOffice integration support on office files [ #551 ]
- [mail] Manual seen with option to set seen on open [ #546 ]
- [calendar] Global setting to disable statistic fields on event window. See :ref:`calendar-event-settings-section` [ #545 ]
- [contacts] Contact list link to contacts [ #542 ]
- [contacts] Add contacts to existing list [ #540 ]
- [core] Add setting for ajax special timeout [ #581 ]
- [mail] Use core setting "ajax.specialtimeout" for message grid listing [ #582 ]
- [mail] Multi search filter on column attachment [ #575 ]
- [mail] Mantain multiple filter visibility upon folder change [ #572 ]
- [mail] Show hour instead of date in list when grouped by date [ #527 ]
- [calendar] Highlight the current time on the calendar with a line [ #320 ]

**Bug Fixes:**

- [core] Possible rare deadlock during attachment content-type recognition [ #583 ]
- [mail] TinyMCE editor does not select image on click [ #580 ]
- [mail] Public images can not be placed on the domain signature from the admin panel [ #579 ]
- [tasks] Cannot setup email reminders [ #578 ]
- [mail] Some mail with attachments do not show the attach icon on the grid [ #576 ]
- [mail] Quoted attributes in html mails may note correctly render [ #570 ]
- [mail] Workaround Dovecot bug during rename folder on shared folders [ #569 ]
- [mail] Junk mail displacement with shared accounts ends up in the wrong folder [ #562 ]
- [contacts] Setting key "default.category.sync" not honored [ #544 ]
- [calendar] Rendering issue if event dates fall on DST boundaries [ #543 ]
- [z-push] Events/Contacts added using EAS cannot be synchronized again using DAV [ #541 ]
- [calendar] The date corresponding to the DST is seen twice in the monthly calendar [ #503 ]
- [mail] Emoticons are not interpreted in the mail received from webtop [ #499 ]
- [calendar] The presence of overlapping events in a day imposes a width on other events [ #469 ]

Release 5.3.3 - september 13, 2018
----------------------------------

**New Features:**

- [core] Add the ability to insert link buttons in launcher. See :ref:`system-settings-section` [ #564 ]

**Bug Fixes:**

- [mail] Bugfix 559 regression : new bug with multiple identities with same emails [ #566 ]
- [mail] Advanced search anywhere does not provide correct results [ #561 ]
- [core] TinyMCE editor applies blob conversion on inline images [ #560 ]

Release 5.3.2 - september 7, 2018
---------------------------------

**Bug Fixes:**

- [mail] Firefox does not show the grid after login, with Crisp theme [ #549 ]
- [mail] Sent receipts are always saved in the Sent folder of the main user, also inside shared identities folders [ #559 ]

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
