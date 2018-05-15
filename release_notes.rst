=============
Release notes
=============

|

WebTop release 5

|

Major changes on wt-5.2
-----------------------
2018-05-15

**New Features:**

- WebTop DAV Server implementation through SabreDAV. See :ref:`dav-server-section`
- NothVoice PBX integration with new specific core configuration. See :ref:`PBX-settings-section` [ #475 ]
- Contacts feature one click on phone numbers and context menus to start the configured PBX call [ #476 ]
- Contacts feature one click on email column to start mail composition [ #474 ]
- Domain users are automatically added as a "webtop" contacts source when suggesting recipients [ #457 ]
- Completed implementation of What's New framework, showing changes for the user upon version upgrades and allowing to browse all history [ #463 ]
- A new action on the email tree context menu allows to upload an eml file to the right-clicked folder [ #462 ]
- Invitation requests are now rendered only with WebTop internal management UI, any attached html part is ignored to avoid confusion [ #455 ]
- Firefox now correctly remembers succesful login names [ #458 ]
- On Cloud, a new "refresh" action allows to reload folders and files [ #385 ]
- Creating new emails, images attached with spaces in the name are not displayed [ #461 ]


**Bug Fixes:**

- Using the "Neptune" theme, Persons and Mail folders can not be seen in the interactive search [ #372 ]
- The partial search in the phonebook in the mail composition does not work [ #373 ]
- New folders on google drive do not appear on the app [ #384 ]
- Scheduled emails are no more processed [ #467 ]

|

Hot fixes on wt-5.1.9
---------------------
2018-05-04

**Bug Fixes:**

- Calendar reminders via email do not work [ #464 ]
- Moving an event breaks reminder notification [ #465 ]

|

Major changes on wt-5.1.8
-------------------------
2018-04-19

**New Features:**

- New global mail configuration option allows to disable grid row preview as a default option for everyone. See :ref:`mail-default-settings-section` [ #468 ]
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
