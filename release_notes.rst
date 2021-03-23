=============
Release notes
=============

WebTop release 5

Release 5.11.0 - mar 23, 2021
-----------------------------

**New Features:**

- [core] New Jitsi Meet integration and support for 3rd party meeting links [ #WT-879 ]
- [core] New Jitsi Meet server module for WebTop authentication [ #WT-943 ]
- [core] New gelocalization services integration settings [ #WT-942 ]
- [core] New authentication text log for monitoring through fail2ban [ #WT-938 ]
- [admin] New authentication log admin tool with geo info [ #WT-850 ]
- [core] New email notifications upon new device login, with geo info [ #WT-929 ]
- [core] New setting to allow extra custom themes and LAFs definition [ #WT-933 ]
- [core] Support german short date format [ #WT-925 ]
- [core] New more visible MessageEditor toggle buttons [ #WT-914 ]
- [core] "Authorize notifications" is now more informational [ #WT-908 ]
- [core] New password policy options for WebTop managed domains [ #WT-898 ]
- [core] OTP mail template is now more responsive [ #WT-887 ]
- [calendar] New user setting to set grid increment to 15 minutes [ #WT-888 ]
- [mail] Grid JSON normalization for forthcoming ExtJS upgrade [ #WT-839 ]
- [mail] New better auto height of images on message view [ #WT-937 ]
- [contacts] New facility for import debugging [ #WT-909 ]

Release 5.10.5 - mar 09, 2021
-----------------------------

**Bug Fixes:**

- [core] TinyMCE html editor upgrade, to solve known issues [ #WT-939 ]
- [mail] In-mail long links are not word-wrapped properly [ #WT-936 ]

Release 5.10.4 - feb 25, 2021
-----------------------------

**Bug Fixes:**

- [mail] Mail badly packaged by an old client may not show text during forward [ #WT-923 ]
- [mail] Support old content type "application/x-pkcs7-signature" [ #WT-924 ]
- [mail] Focus sometimes is not in the right field when opening new message [ #WT-924 ]
- [mail] A forwarded email from a GMail email with attached images, may not show the attach icon [ #WT-928 ]
- [calendar] Organizer is overwritten [ #WT-927 ]

Release 5.10.3 - feb 18, 2021
-----------------------------

**Bug Fixes:**

- [mail] Workaround bugged parts with missing encoding also during forward or reply [ #WT-911 ]
- [mail] Forwarding an email with attached eml multiplies attached files [ #WT-915 ]
- [mail] Sent message's mailcard does not reflect choosen identity [ #WT-916 ]
- [mail] Links on email views always have same target tab/window [ #WT-917 ]
- [mail] Opening and saving draft from live autosaved copy may cause a JavaMail bug to delete wrong draft [ #WT-922 ]

Release 5.10.2 - feb 02, 2021
-----------------------------

**Bug Fixes:**

- [mail] Missing default folder in settings causes problems to mail interface [ #WT-907 ]
- [mail] Mailcards linked to personal identities do not show the values of the variables [ #WT-904 ]
- [mail] Forwarding text only message may contain missing text parts [ #WT-901 ]
- [mail] PEC message not set as seen when opened [ #WT-885 ]
- [mail] Shrinking width of browser horizontally may let grid disappear giving all space to message view [ #WT-863 ]
- [mail] Character encoding of text parts is not always correct [ #WT-841 ]
- [cloud] Unable to download files from cloud public folder link [ #WT-905 ]

Release 5.10.1 - jan 25, 2021
-----------------------------

**Bug Fixes:**

- [core] Page is not reloaded after personal info changes [ #WT-834 ]
- [core] Access via OTP returns blank page under some conditions [ #WT-796 ]
- [core] Zip attachment causes "BAD HEADER SECTION" [ #WT-886 ]
- [calendar] Missing some recurring instances in weekly view [ #WT-876 ]
- [calendar] Missing background colors on events cell [ #WT-844 ]
- [calendar] Shared calendars are not sorted by calendar name [ #WT-890 ]
- [contacts] Shared categories are not sorted by name [ #WT-891 ]
- [mail] It is not possible to save identity mailcards via admin panel [ #WT-903 ]
- [mail] Searching for recipients does not in clude cc or ccn [ #WT-894 ]
- [mail] Recipients with displayname containing apices in the middle are wrongly broken generating an additional wrong recipient [ #WT-902 ]
- [mail] In the event of problem saving on shared accounts, the mail is sent but is not saved anywhere [ #WT-900 ]
- [mail] An empty mailcard is not switched by changing identity [ #WT-899 ]
- [mail] Missing label on Save All button [ #WT-897 ]
- [mail] Incorrect labels management on tag menus [ #WT-896 ]

Release 5.10.0 - dec 15, 2020
-----------------------------

**New Features:**

- [core] Bump commons-configuration dependency [ #WT-849 ]
- [core] Complete logging management allowing overrides [ #WT-847 ]
- [core] New HTML Editor [ #WT-724 ]
- [core] Add setting to disable the automatic search for internal users mail [ #WT-884 ]
- [mail] Don't show empty rectangles without mailcards [ #WT-785 ]
- [mail] Menu are not responsive [ #WT-820 ]
- [mail] Add user option to always show time on email grid as well [ #WT-877 ]
- [cloud] QR code generation on a link folder is not supported [ #WT-878 ]

Release 5.9.5 - nov 19, 2020
----------------------------

**Bug Fixes:**

- [cloud] Error accessing Nextcloud resources [ #WT-629 ]
- [cloud] cloud service not initialized for usernames that contain the _ character [ #WT-852 ]
- [mail] Mails containing tables with height 100% may not be correctly displayed [ #WT-857 ]
- [mail] Compose: generic error on UI after some time [ #WT-859 ]
- [mail] Sending scheduled mail from shared accounts does not work [ #WT-860 ]
- [mail] Mails with inline text or html content shows attachment icon [ #WT-861 ]
- [mail] Eml attachements may cause broken headers on rspamd [ #WT-864 ]
- [mail] Forwarded message should containt reference headers as for replies [ #WT-865 ]
- [mail] The text/plain part of an html email may have missing content [ #WT-866 ]
- [mail] Message send should support ajax special timeout [ #WT-867 ]
- [mail] Long ajax timeout for possibly long operations [ #WT-869 ]
- [calendar] Adding a calendar on a shared resource is not shown after save [ #WT-870 ]
- [contacts] Adding a category on a shared resource is not shown after save [ #WT-871 ]
- [tasks] Adding a category on a shared resource is not shown after save [ #WT-872 ]
- [mail] Shift+delete should delete an email permanently [ #WT-873 ]
- [mail] Dragging from shared special folders to main account special folders keeps mails in shared account [ #WT-875 ]

Release 5.9.4 - oct 08, 2020
----------------------------

**Bug Fixes:**

- [core] Blank page shown on public areas [ #WT-846 ]
- [core] Missing unicode equivalents in .properties i18n files [ #WT-843 ]
- [core] Custom fields visibility limit not satisfied [ #WT-848 ]
- [mail] Missing support to sieve impersonate (no vmail) [ #WT-845 ]

Release 5.9.3 - sep 15, 2020
----------------------------

**Bug Fixes:**

- [core] Custom login image broken if FQDN for auth differs from the one used to reach webapp [ #WT-832 ]
- [core] Massive notification of autosave data [ #WT-842 ]
- [mail] After login some tree folders cannot be opened [ #WT-374 ]
- [mail] Do not save contact lists in automatic recipients [ #WT-290 ]
- [mail] Special folders should show unseen states [ #WT-840 ]
- [mail] Sending mail to a list does not work if the name contains the character ":" [ #WT-838 ]
- [contacts] Never allow use of logically deleted lists [ #WT-581 ]
- [calendar] Invitation mail is not sent to any invitee [ #WT-835 ]

Release 5.9.2 - sep 01, 2020
----------------------------

**Bug Fixes:**

- [mail] Flags label are not valued in advanced search [ #WT-805 ]
- [mail] Downloading attachments in zip format does not open on OSX [ #WT-811 ]
- [mail] The print preview of an email does not open [ #WT-814 ]
- [mail] False positive word detection attached in text-only mode [ #WT-815 ]
- [mail] Advanced search with multiple condition returns an unexpected result [ #WT-821 ]
- [mail] Unencoded labels in the audit window [ #WT-830 ]
- [calendar] Click + CTRL on event hides changes to the text [ #WT-762 ]
- [calendar] Deleting recurrence events cause errors [ #WT-806 ]

Release 5.9.1 - aug 10, 2020
----------------------------

**Bug Fixes:**

- [core] Existing labels duplicated on first login post upgrade [ #WT-823 ]
- [core] Custom login image is no longer displayed [ #WT-824 ]
- [core] Unable to delete private tag [ #WT-825 ]
- [mail] Advanced options sometimes breaks UI [ #WT-826 ]
- [mail] Special folders unseen count not always honouring unchecked "search new messages" [ #WT-828 ]

Release 5.9.0 - jul 30, 2020
----------------------------

**New Features:**

- [core] Display confirmation message on close (browse/tab) [ #WT-23 ]
- [core] Implement tags [ #WT-693 ]
- [core] Implement custom fields [ #WT-31 ]
- [core] Calendar: provide a better layout logic [ #WT-680 ]
- [core] All notified reminders should all be selected [ #WT-476 ]
- [core] Provide wider color palette [ #WT-780 ]
- [core] Simplify management deprecating core-db project [ #WT-46 ]
- [contacts] Move grouping "Contact list" in the multiple search window [ #WT-801 ]
- [mail] Reactivate external imap accounts [ #WT-698 ]
- [mail] Special folders unseen count management [ #WT-214 ]

**Bug Fixes:**

- [core] Push messages are lost when user session is not active [ #WT-777 ]

Release 5.8.5 - may 27, 2020
----------------------------

**New Features:**

- [cloud] Generate, print or save the QR Code to share a file in few clicks [ #WT-799 ]
- [cloud] When uploading same file, manage overwrite or rename [ #WT-803 ]

**Bug Fixes:**

- [core] Unable to start subsequent parallel deployed webapp for clash of new joda time JVM system properties [ #WT-800 ]

Release 5.8.4 - may 08, 2020
----------------------------

**Bug Fixes:**

- [mail] Receipt email user language not honoured [ #WT-407 ]
- [mail] Message view with large images should try to layout without scrollbars [ #WT-794 ]
- [mail] Invite email with description containing links (e.g. MS Teams) may not work [ #WT-784 ]
- [mail] Error after logging in with favorite folders linked to shared accounts [ #WT-783 ]
- [mail] Sorting by state loses sorting by date in some cases [ #WT-778 ]
- [mail] Missing label in a field for advanced search [ #WT-744 ]
- [mail] False deletion of a subfolder of a public folder [ #WT-382 ]
- [mail] The ">" character in the Display name generates an error [ #WT-261 ]
- [mail] With the plain text the focus always ends at the end of the text [ #WT-256 ]
- [mail] The dots at the bottom of the list of recipients do not expand the list [ #WT-252 ]
- [mail] Ldap/AD auth should allow for imap/smtp authentication without domain [ #WT-790 ]
- [mail] Possible bug with imap backends not supporting combining diacritical marks in file names [ #WT-793 ]
- [calendar] Accepted invitation does not create event on the default calendar [ #WT-767 ]
- [calendar] Breaking the 1st instance of recurring event generates an UI error [ #WT-520 ]
- [contacts] Missing DisplayName in contacts import [ #WT-792 ]
- [contacts] The value entered in the company field is not saved [ #WT-789 ]
- [tasks] Missing icon in home page tasks summary [ #WT-782 ]
- [cloud] Single file download via link creates an incorrect file [ #WT-764 ]

Release 5.8.3 - mar 09, 2020
----------------------------

**Bug Fixes:**

- [mail] Attach words detection may get false positive during reply [ #WT-776 ]
- [mail] Mail with attachments misplaced in multipart/alternative are not showed [ #WT-774 ]
- [mail] Regression: failed to send mail with images resized in the mailcard [ #WT-773 ]
- [mail] Sharing the root does not show previous shares [ #WT-760 ]

Release 5.8.2 - mar 04, 2020
----------------------------

**Bug Fixes:**

- [mail] Mails with preformatted text do not print correctly [ #WT-757 ]
- [mail] View of message with large images does not show scrollbar [ #WT-758 ]
- [mail] Use mailcard button fails when signature disabled on reply [ #WT-759 ]
- [mail] Cannot send email in old browsers on old systems [ #WT-768 ]
- [mail] View-option for flagged emails should list messages in ASC order [ #WT-768 ]
- [mail] Avoid sending receipts multiple times [ #WT-771 ]
- [mail] Sorting by attachment doesn't work correctly [ #WT-772 ]
- [calendar] Privacy status public/private in DAV sync is not supported [ #WT-770 ]

Release 5.8.1 - feb 14, 2020
----------------------------

**Bug Fixes:**

- [core] Prevent WebTop's pages indexing by crawlers [ #WT-745 ]
- [core] Build process is broken [ #WT-748 ]
- [mail] PEC special preview may fail on some pec message [ #WT-282 ]
- [mail] Missing icon open mail window [ #WT-344 ]
- [tasks] Internal href value is not filled with default value [ #WT-747 ]
- [tasks] New task added on apple device is not synchronized with EAS [ #WT-746 ]

Release 5.8.0 - jan 13, 2020
----------------------------

**New Features:**

- [core] Make logback configuration more smart, enabling customers modifications [ #WTCORE-94 ]
- [core] Complete review of Atmosphere component [ #WTCORE-96 ]
- [mail] Detect missing attachment on send [ #WTMAIL-246 ]
- [mail] Highlight searched keywords [ #WTMAIL-249 ]
- [mail] Search new messages and Web notifications on Favorite folders	 [ #WTMAIL-252 ]
- [mail] Customize description of incoming sharing root [ #WTMAIL-260 ]
- [mail] Move the preview mover button to a dedicated menu [ #WTMAIL-280 ]
- [mail] Add readStatus and flags support view options menu [ #WTMAIL-281 ]
- [mail] Add option to use or not mailcard on a new email [ #WTMAIL-284 ]
- [mail] Paste from contact list to email recipients [ #WTMAIL-285 ]
- [mail] Menu for account root to manage sharing of all account [ #WTMAIL-288 ]
- [mail] Add support to eml (message mime) attachment in forward [ #WTMAIL-323 ]
- [contacts] Add the default grouping choice [ #WT-568 ]
- [contacts] Changing the owner does not show the category of a shared resource [ #WTCONTACTS-39 ]
- [contacts] Add control on contacts that cannot be synchronized with DAV [ #WTCONTACTS-45 ]
- [contacts] Add function and department into contacts search [ #WTCONTACTS-48 ]
- [contacts] Highlight searched keyword [ #WTCONTACTS-49 ]
- [contacts] Add address and notes into contacts search [ #WTCONTACTS-50 ]
- [calendar] Changing the owner does not show the category of a shared resource [ #WTCALENDAR-72 ]
- [calendar] Auto-update start/end in a better way [ #WTCALENDAR-75 ]
- [calendar] Highlight searched keyword [ #WTCALENDAR-94 ]
- [tasks] Changing the owner does not show the category of a shared resource [ #WTTASKS-11 ]
- [tasks] New unified search tool [ #WTTASKS-12 ]
- [tasks] Highlight searched keyword [ #WTTASKS-13 ]
- [eas-server] Add support to specialUsers in log management [ #WTEASSRV-18 ]

**Bug Fixes:**

- [calendar] CalDav: Adding imported event from invitation should not send a new notification [ #WTCALENDAR-109 ]
- [calendar] Private events are synchronized and shown when shared [ #WTCALENDAR-82 ]

Release 5.7.7 - dec 19, 2019
----------------------------

**Bug Fixes:**

- [calendar] All-day recurring event does not show the first event [ #WTCALENDAR-107 ]

Release 5.7.6 - dec 11, 2019
----------------------------

**Bug Fixes:**

- [mail] Mail with html part containing Content-ID header is shown as with attachment [ #WTMAIL-324 ]
- [core] Socket connections timeouts of JavaMail should not be infinite [ #WTCORE-104 ]
- [cloud] The icon on the Remove button is not shown [ #WTCLOUD-27 ]
- [cloud] Confirmation key does not appear complete on small screens [ #WTCLOUD-25 ]
- [calendar] Invitation message not in english [ #WTCALENDAR-104 ]
- [calendar] Recurring event generate interface error [ #WTCALENDAR-95 ]

Release 5.7.5 - nov 18, 2019
----------------------------

**Bug Fixes:**

- [mail] Strange behaviour of interactive search filter dialogs [ #WTMAIL-309 ]
- [mail] Links with mailto containing encoded characters are not decoded in new mail [ #WTMAIL-307 ]
- [mail] Importing an external invitation fails in some cases [ #WTMAIL-306 ]
- [mail] Mail with attachment referenced from html shows the paper clip [ #WTMAIL-305 ]
- [mail] The condition is not saved in the inbox filter [ #WTMAIL-300 ]
- [mail] Filtering rules in interactive search do not work [ #WTMAIL-231 ]
- [cloud] File names with the ":" character in Google Drive generate an error [ #WTCLOUD-26 ]
- [calendar] Import should disarm or ignore past alarms [ #WTCALENDAR-93 ]
- [calendar] Import should keep first valid VALARM [ #WTCALENDAR-92 ]
- [calendar] Recurring all-day events longer than a week are not shown correctly [ #WTCALENDAR-91 ]
- [calendar] Event cannot be synchronized in some iphone devices [ #WTCALENDAR-90 ]

Release 5.7.4 - oct 30, 2019
----------------------------

**Bug Fixes:**

- [core] Some timezone IDs are not supported [ #WTCORE-97 ]
- [mail] Some email addresses are not found during the recipient's auto-completion phase [ #WTMAIL-303 ]
- [mail] Folder with unseen messages in FF is not displayed in bold [ #WTMAIL-302 ]
- [mail] Some inline attachments should still be seen as attachments [ #WTMAIL-301 ]
- [mail] The number of emails to read is not always updated [ #WTMAIL-299 ]
- [mail] Mail without attachment shows the paper clip [ #WTMAIL-298 ]
- [mail] Regression: failed to send mail with images resized in the mailcard [ #WTMAIL-297 ]
- [mail] The mail service does not start in the Tablet layout [ #WTMAIL-296 ]
- [mail] The color change of a custom label applies the label to the whole mailbox [ #WTMAIL-295 ]
- [mail] Truncated display of the mail message [ #WTMAIL-294 ]
- [mail] Opening draft does not consider saved sender [ #WTMAIL-293 ]
- [mail] With the compact view mode it does not show the memo icon [ #WTMAIL-290 ]
- [contacts] VCard writer should escape double-quotes [ #WTCONTACTS-46 ]
- [calendar] Reminders incorrectly synchronized with CalDAV and Apple devices [ #WTCALENDAR-89 ]
- [calendar] All-day events of several days with recurrence are not shown correctly [ #WTCALENDAR-87 ]
- [calendar] Initial date shift of a recurring event does not work properly [ #WTCALENDAR-86 ]
- [calendar] Importing a ics file from google causes java.lang.NullPointerException [ #WTCALENDAR-85 ]
- [calendar] Event notifications on internet calendars are replicated at each synchronization [ #WTCALENDAR-80 ]
- [dav-server] Contacts synchronization with Android removes the business role field [#WTDAVSRV-7]

Release 5.7.3 - sep 10, 2019
-----------------------------

**Bug Fixes:**

- [core] Changes to user settings from the admin panel are not propagated [ #WTCORE-63 ]
- [mail] Automatic conversion of text file attachments [ #WTMAIL-258 ]
- [mail] Interactive search does not work "open in Folder" button [ #WTMAIL-274 ]
- [mail] Possible leak during discconnect of external accounts [ #WTMAIL-277 ]
- [mail] Manage Tags does not open [ #WTMAIL-278 ]
- [mail] Missing icon on manage tags [ #WTMAIL-279 ]
- [mail] JavaScript error on mail on slow internet or browser breaks mail functionality [ #WTMAIL-282 ]
- [mail] When rename of folder fails, original folder is no more working correctly [ #WTMAIL-283 ]
- [contacts] ContactList: linked contact with missing firstname/lastname generates error [ #WTCONTACTS-44 ]
- [calendar] Events search result should not be filtered [ #WTCALENDAR-84 ]

Release 5.7.2 - aug 01, 2019
-------------------------------

**Bug Fixes:**

- [mail] Text of the email does not wrap the window down [ #WTMAIL-214 ]
- [mail] Preventing to flag/tag email from a shared read-only account [ #WTMAIL-227 ]
- [mail] The advanced search does not open if a favorite folder is selected [ #WTMAIL-240 ]
- [mail] Image for mailcard not converted if the name contains spaces [ #WTMAIL-250 ]
- [mail] Content editable in html mails should be filtered [ #WTMAIL-251 ]
- [mail] Moving IMAP folders requires a refresh [ #WTMAIL-256 ]
- [mail] Favorite folders from external accounts are not deleted [ #WTMAIL-261 ]
- [mail] Inverted mouse over labels [ #WTMAIL-262 ]
- [mail] Mail Home Portlet shows all Inbox messages [ #WTMAIL-263 ]
- [mail] Operations window does not take query parameter [ #WTMAIL-264 ]
- [mail] Mail Service cleanup during logout is not quickly garbaged [ #WTMAIL-265 ]
- [mail] The Manage Tags window does not close [ #WTMAIL-268 ]
- [mail] Mailcards are rendered with wrong line spacings [ #WTMAIL-269 ]
- [mail] Minimize imap objects for heavy loads [ #WTMAIL-270 ]
- [mail] Inbox in favorites causes serious leak [ #WTMAIL-273 ]
- [calendar] All-day events are displayed incorrectly [ #WTCALENDAR-76 ]
- [calendar] Weekly recurring event is displayed incorrectly [ #WTCALENDAR-77 ]
- [calendar] In some limit cases displayed events overlap on each other [ #WTCALENDAR-79 ]
- [calendar] Shared calendars are not updated on Apple devices with CalDAV [ #WTCALENDAR-83 ]
- [contacts] base64 values are not converted when importing from an LDIF file [ #WTCONTACTS-43 ]

**New Features:**

- [eas-server] Prevents the device from performing a full resync of data after transitioning to webtop-eas-server [ #WTEASSRV-17 ]
- [dav-server] Avoid NotAuthenticated critical exceptions in logs [ #WTDAVSRV-8 ]

Release 5.7.1 - jun 14, 2019
-----------------------------

**Bug Fixes:**

- [core] Usernames starting with a number in AD domain, are not allowed in admin interface [ #WTCORE-91 ]
- [core] Allow change password for writable ldap directory users marked as "Not in WebTop" [ #WTCORE-89 ]
- [core] Add method to activate js debug mode using browser console[ #WTCORE-88 ]
- [mail] Mail filters cannot be saved [ #WTMAIL-254 ]
- [mail] Error managing external account grid [ #WTMAIL-255 ]
- [mail] Using addressbook, no recipients are shown without a name or surname [ WTMAIL-253 ]
- [contacts] Changing the "Show names by" setting does not reload the page [ #WTCONTACTS-42 ]

Release 5.7.0 - may 28, 2019
----------------------------

**Bug Fixes:**

- [core] After user autoCreation an error entry is traced [#WTCORE-86]
- [mail] Mail preview may break html5 content [#WTMAIL-237]
- [calendar] Event instance is lost when recurring event start is moved ahead [#WTCALENDAR-69]
- [calendar] Copying an event does not synchronize the original event via CalDAV [#WTCALENDAR-64]
- [calendar] Until date in recurring event is excluded from instances count [#WTCALENDAR-70]
- [calendar] The availability of the guest is not shown [#WTCALENDAR-74]
- [cloud] File download notification is not sent [#WTCLOUD-21]
- [cloud] Webdav server fails to list folders with special characters [#WTCLOUD-17]

**New Features:**

- [core] Faster login loading time [#WTCORE-85]
- [core] Implement the exclusion of all robots from the login page [#WTCORE-75]
- [mail] Mail grid compact view [#WTMAIL-248]
- [mail] Option to add unknown contacts [#WTMAIL-247]
- [mail] New unified search on emails [#WTMAIL-244]
- [mail] Inhibit selection of root nodes in tree [#WTMAIL-234]
- [mail] Show something on the message view when nothing is selected [#WTMAIL-233]
- [mail] External mail account management [#WTMAIL-232]
- [mail] Description of favorite [ #WTMAIL-257 ]
- [calendar] Provide a better hierarchical display of Calendars [#WTCALENDAR-62]
- [calendar] The reminder on calendar events is not synchronized [#WTCALENDAR-63]
- [calendar] Make logic insensitive to all-day events time convention (part1) [#WTCALENDAR-67]
- [calendar] New unified search tool [#WTCALENDAR-73]
- [calendar] Each shared schedule should always be activated and expanded by default [#WTCALENDAR-23]
- [contacts] Edit contact button in the preview window [#WTCONTACTS-31]
- [contacts] Provide a better hierarchical display of Categories [#WTCONTACTS-35]
- [contacts] Add display name field [#WTCONTACTS-37]
- [contacts] New unified search tool [#WTCONTACTS-41]
- [tasks] Transform the category chooser (during Move/Copy) into a tree [#WTTASKS-9]
- [tasks] Provide a better hierarchical display of Categories [#WTTASKS-7]
- [eas-server] Create better RRULE for android devices [#WTEASSRV-16]

Release 5.6.5 - may 27, 2019
----------------------------

**Bug Fixes:**

- [mail] Double clicking on an email, the seen flag is not changed with "Manual Seen" and "Seen on open" option enabled [#WTMAIL-245]

Release 5.6.4 - apr 19, 2019
------------------------------

**Bug Fixes:**

- [core] Chat audio/video conferencing does not work when ice servers are configured in globals [#WTCORE-84]
- [core] The what's new window is always shown after login [#WTCORE-77]
- [core] ZPush admin script output is not parsed correctly [#WTCORE-81]
- [mail] The scheduled notification email does not show the html content [#WTMAIL-242]
- [mail] Missing icon in scheduled emails [#WTMAIL-241]
- [mail] With no mailcard set, editor reacts insanely on first enter [#WTMAIL-239]
- [mail] In manual seen mode, unseen number decrease incorrectly [#WTMAIL-238]
- [mail] Mail preview may break html5 content [#WTMAIL-237]
- [mail] Mail drafts always become read when opened with manual seen set [#WTMAIL-236]
- [mail] The OK key of hidden folder recovery does not work [#WTMAIL-220]
- [mail] PDF attachments sent with add-ons do not open in view [#WTMAIL-100]
- [calendar] Broken recurrences are not synchronized correctly with EAS and DAV [#WTCALENDAR-59]
- [calendar] Sync customization on shared calendar is not honored [#WTCALENDAR-65]
- [contacts] Values from some fields can not be deleted  [#WTCONTACTS-34]
- [contacts] Sync customization on shared category is not honored [#WTCONTACTS-36]
- [tasks] DB error when inserting a new task [#WTTASKS-10]
- [tasks] Sync customization on shared category is not honored [#WTTASKS-8]
- [eas-server] Folders are duplicated after upgrade [#WTEASSRV-10]
- [eas-server] Events are not editable in Android's Google Calendar if you have a customized email address [#WTEASSRV-11]
- [eas-server] Occasionally sync with Android devices is not done [#WTEASSRV-12]
- [eas-server] config.js not always found correctly [#WTEASSRV-13]
- [eas-server] All-day events created by the device after the upgrade are modified [#WTEASSRV-14]

Release 5.6.3 - mar 22, 2019
------------------------------

**Bug Fixes:**

- [core] Old launcher links setting format in globals may cause main interface problems [#WTCORE-79]

Release 5.6.2 - mar 13, 2019
------------------------------

**Bug Fixes:**

- [core] Missing db namespace in init-data-core.sql [#WTCORE-76]

Release 5.6.1 - mar 07, 2019
------------------------------

**Bug Fixes:**

- [mail] Order by Status or Priority then by descending date [#WTMAIL-229]
- [mail] Forwarding mails with multiple bodies (e.g. Italian PEC) misses parts [#WTMAIL-228]
- [mail] Using Firefox and plain text the interface crashes [#WTMAIL-221]

Release 5.6.0 - feb 28, 2019
---------------------------------

**Bug Fixes:**

- [core] Error removing domain settings [#WTCORE-72]
- [core] Automatic recipients cannot be deleted if they contain accented characters [#WTCORE-74]
- [mail] Failed to send mail with images resized in the mailcard [#WTMAIL-224]
- [mail] Possible timeouts and errors during scheduled mails check [#WTMAIL-223]
- [mail] Add failure message when try to flag/tag a read-only shared account [#WTMAIL-219]
- [mail] Mail with special characters in the object can not be saved [#WTMAIL-217]
- [mail] Some threads are not grouped correctly [#WTMAIL-154]
- [mail] In some cases the mail of the organizer is not detected even if present in the attached .ics file [#WTMAIL-141]
- [cloud] It is not possible to rename files with extension [#WTCLOUD-20]

**New Features:**

- [core] Add a management view for launcher links [#WTCORE-70]
- [mail] PEC View [#WTMAIL-226]
- [mail] Import contact from vcf attachment [#WTMAIL-225]
- [cloud] Download complete folder as a zip file [#WTCLOUD-19]
- [eas-server] Brand new ActiveSync Server, full rewrite of the old webtop-zpush [#WTEASSRV-7]
- [dav-server] Align config.js and API clients as the EAS server (see dav-server docs) [#WTDAVSRV-5]

Release 5.5.3 - feb 19, 2019
---------------------------------

**Bug Fixes:**

- [mail] From the admin panel the domain mailcard is not editable [#WTMAIL-222]

Release 5.5.2 - feb 8, 2019
---------------------------------

**Bug Fixes:**

- [mail] Sending email sometimes shows error on "closed folder" [#673]

Release 5.5.1 - jan 30, 2019
---------------------------------

**New Features:**

- [core] Add setting to hide auto-suggested recipient in lookups (see :ref:`system-settings-section`) [#645]
- [core] Reset two-factor authentication (OTP) from admin [#360]
- [mail] Add subject customization in auto-responder [#646]
- [mail] Add support to DnD attachments between message preview to cloud [#639]
- [mail] Save an attachment from an email directly to your personal cloud [#329]
- [mail] Edit subject of a mail and save it. A specific setting is needed to enable this functionality, see :ref:`mail-settings-section` [#297]
- [mail] Remember search field by folder [#205]
- [calendar] Show day name in first column of weekly view [#650]
- [contacts] Add support to multiselect when moving or copying contacts [#623]

**Bug Fixes:**

- [core] Sometimes log file is not written (startup configuration needs to be updated here, please see :ref:`configuration-logging-section`) [#661]
- [core] Click on email in the body does not pick up email address [#654]
- [core] Upgrade plupload to avoid WRONG_FORMAT error [#565]
- [core] Some upload button/item no longer work with the upgraded plupload [#665]
- [core] Some fileType icons are missing [#663]
- [core] Key translation error on postpone reminder [#660]
- [mail] Mails created with feature [#629] turned on may not work properly on Apple Mail [#664]
- [mail] The delete button does not work by opening the email [#664]
- [mail] Hide unneeded date columns in message grid header options [#659]
- [mail] Check mailcard permissions server side during write [#658]
- [mail] Advanced search on folders other than INBOX goes wrong [#656]
- [mail] Deleting/Renaming a folder set as favorite causes a UI error [#655]
- [mail] Clicking on web notification of a new mail does not refresh the inbox and cause javascript error [#648]
- [mail] Broken inline images on "Forward" or "Open as new message" [#643]
- [mail] Match unconditionally option in filters (incoming) doesn't require rules [#600]
- [contacts] List element with linked contact may throw null pointer exception on open [#642]
- [tasks] It is not possible to copy tasks from one category to another [#623]
- [cloud] Creating folders with the character : in the name you no longer access your personal cloud [#479]

Release 5.5.0 - nov 30, 2018
---------------------------------

**New Features:**

- [mail] Request to save drafts by closing an uncompleted email [ #247 ]
- [mail] Add support to multiline text when using reject action in filter actions[ #601 ]
- [mail] Customize color of todays messages[ #604 ]
- [mail] Add start/end dates and days on vacation filter [ #611 ]
- [mail] Option to transform resource links to inline attachment (e.g. card images) [ #629 ]
- [mail] External archiving management [ #635 ]
- [dav-server] Add support to shared resources synchronization [ #507 ]
- [core] Customize font list available to the html editor [ #610 ]
- [contacts] Restyling: infinite grid, initials, modern grouping, preview pane [ #622 ]
- [cloud] Drag & Drop files from cloud to email message [ #386 ]
- [calendar] Improve invitation behaviour [ #595 ]
- [calendar] Allow recurring event start date modification [ #596 ]

**Bug Fixes:**

- [mail] It is not possible to rename subfolders in case of alternative root [#634]
- [mail] Opening more than one new message and sending may delete only one of the automatic drafts [#637]

Release 5.4.5 - nov 21, 2018
---------------------------------

**Bug Fixes:**

- [calendar] Through DAV is not possible to make invitations on events [#627]

Release 5.4.4 - nov 20, 2018
---------------------------------

**Bug Fixes:**

- [mail] Bulleted list lost by forwarding the mail [ #613 ]
- [mail] Image inserted in the body of the email are not always shown [ #614 ]
- [mail] Mails with wrong html may cut parts of text away [ #615 ]
- [mail] Replying to an email, inline images are lost [ #616 ]
- [mail] Events in scheduler display are not grouped by calendar [ #620 ]
- [mail] Inline cids generated as filenames may duplicate during fwds/replies [ #625 ]
- [mail] Replies do not retain possible original html styles and or inner bodies [ #626 ]

Release 5.4.3 - nov 2, 2018
---------------------------------

**Bug Fixes:**

- [mail] Insert file image produces broken image [ #612 ]
- [mail] Advanced search problem with columns after subject [ #607 ]

Release 5.4.2 - oct 24, 2018
---------------------------------

**New Features:**

- [mail] Avoid removing recipients equal to my identities during ReplyToAll [ #603 ]

**Bug Fixes:**

- [contacts] Contacts list virtual address is not expanded anymore [ #602 ]
- [contacts] The search result is not updated by deleting the key [ #591 ]

Release 5.4.1 - oct 12, 2018
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

Release 5.4.0 - oct 2, 2018
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

Release 5.3.3 - sep 13, 2018
----------------------------------

**New Features:**

- [core] Add the ability to insert link buttons in launcher. See :ref:`system-settings-section` [ #564 ]

**Bug Fixes:**

- [mail] Bugfix 559 regression : new bug with multiple identities with same emails [ #566 ]
- [mail] Advanced search anywhere does not provide correct results [ #561 ]
- [core] TinyMCE editor applies blob conversion on inline images [ #560 ]

Release 5.3.2 - sep 7, 2018
---------------------------------

**Bug Fixes:**

- [mail] Firefox does not show the grid after login, with Crisp theme [ #549 ]
- [mail] Sent receipts are always saved in the Sent folder of the main user, also inside shared identities folders [ #559 ]

Release 5.3.1 - sep 5, 2018
---------------------------------

**Bug Fixes:**

- [mail] Some text/plain mails with non utf-8 charset may not display correctly [ #554 ]
- [mail] Sending or discarding a new message may sometime prompt errors [ #555 ]

Release 5.3.0 - jul 27, 2018
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


Release 5.2.3 - jul 11, 2018
-----------------------------

**Bug Fixes:**

- [dav-server] Parsing exceptions on some CentOS installations [ #516 ]
- [mail] Subject is not saved during send for later suggestions [ #515 ]
- [core] Java8 breaks mediaType guessing order in mimeutil [ #513 ]
- [core] Calls to public services override user subject associated to execution thread [ #512 ]
- [mail] Can not use the action marks as seen in the filters [ #511 ]
- [mail] Possible deadlocks when having many many folders, caused by JavaMail standard library [ #518 ]


Release 5.2.2 - jun 11, 2018
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


Release 5.1.8 - apr 19, 2018
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
