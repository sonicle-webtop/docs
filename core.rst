====
Core
====

WebTop Core Services

.. _core-usersettings-section:

User settings management
########################

Most user settings can be directly managed by the user itself via the settings menu. Locked settings reuquire administration privileges.
The administrator can impersonate users through a specific login pattern (admin!user@domain) using its own admin password, to check the correctness and functionalities of the account.
Up to version 5.2.3, impersonating received administration privileges, allowing to change locked user settings once impersonated.
Since version 5.2.4 this has changed: impersonating receives samer user privileges, allowing to check exactly what the user can see.
Full user settings administration is available directly in the admin interface, by right clicking on a user: the settings menu will open the full user settings pane, with everything unlocked.

.. _core-settings-section:

Global core configuration settings
##################################

Global and per-domain configuration settings can be setup using the admin interface, using the admin user. Click on properties to show the current settings, grouped by service. You may directly edit the settings and/or add new ones as specified in the documentation. Missing settings will default to a specified value.

.. _system-settings-section:

System Settings
---------------

* | ``system.language`` [ en | it | ... ]
  | Defines system default language locale.

* | ``system.country`` [ US | IT | ... ]
  | Defines system default country locale.

* | ``themes.extra`` [ comma separated theme entries list ]
  | Entries in the form of "id=name" (theme id and its name) representing additional themes to be made available in WebTop.
  | Example:

  ::

    theme1=Theme 1,theme2=Theme 2

  | @since: 5.10.0

* | ``lafs.extra`` [ comma separated LAF entries list ]
  | Entries in the form of "id=name" (look&feel id and its name) representing additional look&feels to be made available in WebTop.
  | Example:

  ::

    laf1=LAF 1,laf2=LAF 2

  | @since: 5.10.0

* | ``tomcat.manager.uri`` [ uri-to-tomcat-manager ]
  | Defines how to reach Tomcat manager applicaton. This is necessary when running Tomcat webapp versioning to run different versions of WebTop during upgrades. Each instance will use this URL to detect other instances and decide which one is latest: only the latest will run background processes that need to be unique.

* | ``maintenance.enabled`` [ true | false ]
  | Indicates if maintenance management is active or not. Maintenance state is automatically managed by the system when problems occurs during version upgrade. This setting should be used only to disable this feature, active by default.

* | ``whatsnew.enabled`` [ true | false ]
  | Specifies if What's New visualization to users is enabled.

* | ``recipient.provider.webtop.enabled`` [ true | false ]
  | Specifies whether to include webtop-internal recipients in default (no sources specified) recipients lookups. Defaults to ``true``.
  | @since: 5.10.0

* | ``recipient.provider.auto.enabled`` [ true | false ]
  | Specifies whether to include auto-recipients in default (no sources specified) recipients lookups. Defaults to ``true``.
  | @since: 5.5.1

* | ``launcher.links`` [ json-array-of-link-objects ]
  | Specifies a list of links to be displayed as link buttons in viewport's launcher.
  | List definitiron must be specified as a JSON array. Each element is an object with the following fields:
  | - ``text``: The text to display as tooltip.
  | - ``href``: The URL of the page the link goes to.
  | - ``icon``: The URL of the image to display as button icon. In order to avoid scaling problems, vector images should be used.
  | - ``order``: An positive integer (greater than 0) value representing the display position, items will be ordered by this field. (@since: 5.6.0)
  | Example:

  ::

    [
      {
        'href': 'https://www.google.it/',
        'text': 'Google',
        'icon': 'https://upload.wikimedia.org/wikipedia/commons/5/53/Google_%22G%22_Logo.svg',
        'order': 1
      }, {
        'href': 'https://the/url/to/open',
        'text': 'The link text',
        'icon': 'https://the/icon/url',
        'order': 2
      }
    ]

  | @since: 5.3.2

* | ``ajax.specialtimeout`` [ milliseconds ]
  | Allow override of default timeout on proxies/requests that may take longer than 30 seconds.
  | Used by mail message grid to allow longer search queries.
  | Since mail version 5.8.12 used by mail send ajax call to support slow responses from SMTP servers.
  | @since: 5.3.3

* | ``ajax.longtimeout`` [ milliseconds ]
  | Allow override of default timeout on proxies/requests that possibly take longer than 5 minutes.
  | Used in these specific situatons:
  | - bulk copy/move messages operations
  | - move folder, trash folder, delete folder
  | - empty trash
  | - share mail account folders
  | @since: 5.8.12

* | ``audit.enabled`` [ true | false ]
  | If enabled, WebTop will log various actions into a dedicated DB table. Defaults to ``false``.

* | ``audit.logimpersonated`` [ true | false ]
  | Specifies whether to enable auditing for activities coming from an impersonated session. When ``false`` no entries will be produced during impersonation of a user. Defaults to ``false``.
  | @since: 5.10.0

.. _login-settings-section:

Login Settings
---------------

* | ``login.domains.hide`` [ true | false ]
  | Indicates whether to forcedly hide domain selection from login page, in case of multiple domains.

* | ``login.systeminfo.hide`` [ true | false ]
  | Indicates whether to forcedly hide footer system details (os, appserver, java) from login page.

* | ``login.webappname.hide`` [ true | false ]
  | Indicates whether to forcedly hide deployed webapp name.

.. _paths-settings-section:

Paths Settings
--------------

* | ``php.path`` [ /path/to/php ]
  | The path to the php binaary, used to run Z-Push admin commands and other php stuff.

* | ``zpush.path`` [ /path/to/zpush ]
  | The path to the root of the configured WebTop Z-Push root.

* | ``home.path`` [ /path/to/webtop/home ]
  | The path to a home folder for WebTop. This will contain domains files, such as personal cloud folders, mailcards, cloud attachment, etc.

* | ``public.url`` [ url ]
  | This URL defines how WebTop is reachable from internet. It will be used to build various URLs, such as public cloud file URLs.

* | ``davserver.url`` [ url ]
  | This URL defines how WebTop DAV Server is reachable from internet. It will be used to build various URLs, such as public DAV URLs.
  | @since: 5.2.0

.. _core-defaults-settings-section:

Settings (defaults)
-------------------

* | ``default.theme`` [ crisp | neptune | classic | gray | ... ]
  | Defines the default theme for users. Internally defaults to ``crisp``.

* | ``default.layout`` [ default | compact ]
  | Defines the default layout for users. Internally defaults to ``default``.

* | ``default.laf`` [ default ]
  | Defines the default look and feel for users. This may define an alternative icon set. Internally defaults to ``default``.

* | ``default.rtl`` [ true | false ] (not yet used)
  | If true, the web interface is delivered in right-to-left mode. Internally defaults to ``false``.

* | ``default.viewport.header.scale`` [ small | medium | large ]
  | Defines the default viewport header's scale. Internally defaults to ``small``.

* | ``default.startup.service`` [ core | mail | calendar | contacts | tasks | vfs ]
  | The default service to start with after login.

* | ``default.notifications.desktop`` [ never | always | auto ]
  | The default desktop notifications mode. Internally defaults to ``auto``.
  | ``never``: Desktop notifications will not be displayed.
  | ``always``: Desktop notification will be always displayed.
  | ``auto``: Desktop notifications will be displayed only if webapp is in background.
  | NB: A consent screen will be prompted by the browser if necessary.

* | ``default.i18n.startDay`` [ 0 | 1 ]
  | Week start day. Internally defaults to ``1``.
  | ``0``: Sunday.
  | ``1``: Monday.

* | ``default.i18n.timezone`` [ timezone-id ]
  | Users timezone. Internally defaults to ``Europe/Rome``.

* | ``default.i18n.format.date.short`` [ short-date-format-pattern ]
  | Date format pattern (java style) for short dates. Internally defaults to ``dd/MM/yyyy``.
  | ``dd/MM/yyyy``: dd/MM/yyyy
  | ``dd-MM-yyyy``: dd-MM-yyyy
  | ``dd.MM.yyyy``: dd.MM.yyyy
  | ``yyyy-MM-dd``: yyyy-MM-dd
  | ``yyyy.MM.dd``: yyyy.MM.dd
  | ``MM/dd/yyyy``: MM/dd/yyyy
  | ``MM-dd-yyyy``: MM-dd-yyyy
  | ``MM.dd.yyyy``: MM.dd.yyyy
  | ``dd. MM. yyyy.``: dd. MM. yyyy.
  | ``d/M/yy``: d/M/yy

* | ``default.i18n.format.date.long`` [ long-date-format-pattern ]
  | Date format pattern (java style) for long dates. Internally defaults to ``dd MMM yyyy``.
  | ``dd MMM yyyy``: dd MMM yyyy
  | ``dd MMMM yyyy``: dd MMMM yyyy
  | ``MMM dd, yyyy``: MMM dd, yyyy
  | ``MMMM dd, yyyy``: MMMM dd, yyyy
  | ``yyyy. MMM dd.``: yyyy. MMM dd.
  | ``yyyy. MMMM dd.``: yyyy. MMMM dd.
  | ``dd. MMM yyyy.``: dd. MMM yyyy.
  | ``dd. MMMM yyyy.``: dd. MMMM yyyy.

* | ``default.i18n.format.time.short`` [ short-time-format-pattern ]
  | Time format pattern (java style) for short times. Internally defaults to ``HH:mm``.
  | ``HH:mm``: hh:mm
  | ``h:mm a``: h:mm AM/PM

* | ``default.i18n.format.time.long`` [ long-time-format-pattern ]
  | Time format pattern (java style) for long times. Internally defaults to ``HH:mm:ss``.
  | ``HH:mm:ss``: hh:mm:ss
  | ``h:mm:ss a``: h:mm:ss AM/PM

* | ``default.devices.sync.alert.enabled`` [ true | false ]
  | Enables an email alert if device synchronization is broken. Internally defaults to ``false``.

* | ``default.im.upload.maxfilesize`` [ size-in-bytes ]
  | Maximum upload size in instant-messaging. Internally defaults to ``10485760`` (10MB).

.. _editor-settings-section:

HTML Editor Settings
--------------------

* | ``editor.fonts`` [ comma separated font names list ]
  | Customize list of fonts available to the HTML editor. (do not use whitespaces after colon)
  | Default list: Arial, Comic Sans MS, Courier New, Georgia, Helvetica, Tahoma, Times New Roman, Verdana, Webdings, Wingdings
  | @since: 5.5.0

* | ``editor.fontsizes`` [ comma separated font sizes list ]
  | Customize list of font-sizes available to the HTML editor. (do not use whitespaces after colon)
  | Default list: 8px, 10px, 12px, 14px, 16px, 18px, 24px, 36px, 48px
  | @since: 5.9.0

.. _smtp-settings-section:

SMTP Settings
--------------

* | ``smtp.host`` [ host ]
  | Defines the SMTP host for outgoing mails.

* | ``smtp.port`` [ port ]
  | Defines the SMTP port to be used on the defined SMTP host.

* | ``smtp.starttls`` [ true | false ]
  | Enable starttls on SMTP send

* | ``smtp.auth`` [ true | false ]
  | Enable authentication for user sessions SMTP send. Core sessionless woker threads will continue to send with no authentication.

.. _xmpp-settings-section:

XMPP Settings
--------------

* | ``xmpp.host`` [ host ]
  | Defines the XMPP host for IM services. Defaults to ``localhost``.

* | ``xmpp.port`` [ port ]
  | Defines the XMPP port to be used on the defined XMPP host. Defaults to ``5222``.

* | ``xmpp.muc.subdomain`` [ xmpp-multiuserchat-subdomain ]
  | Defines the XMPP subdomain for multi user chat. Defaults to ``conference``.

* | ``xmpp.bosh.url`` [ url ]
  | Optional. Specifies the XMPP URL that can be accessed using BOSH protocol.
  | Currently only needed for WebRTC to work; if not present, WebRTC functions will be disabled.
  | @since: 5.2.4

.. _webrtc-settings-section:

WebRTC Settings
---------------

* | ``webrtc.ice.servers`` [ json-array-of-iceserver-objects ]
  | Defines list of ICE servers as a JSON array.
  | Each element is an object with the following fields:
  | - ``url``: The server URL.
  | - ``username``: The server username. (optional)
  | - ``credential``: The server password. (optional)
  |
  | Example:

  ::

    [
      {
        'url': 'stun:stun.l.google.com:19302'
      }, {
        'url': 'stun:stun.mystunserver.com:19302'
      }, {
        'url': 'turn:myturnserver.com:80?transport=tcp',
        'username': 'my_turn_username',
        'credential': 'my_turn_password'
      }
    ]

  | @since: 5.2.4

.. _security-settings-section:

Security Settings
-----------------

* | ``security.knowndeviceverification.enabled`` [ true | false ]
  | Enable or disable remote-device reporting: an email notice is sent to a set of recipients if, after a successful login, the device is not already marked as known-device. Defaults to ``true``.
  | @since: 5.10.0

* | ``security.knowndeviceverification.recipients`` [ comma separated recipient list ]
  | List of email addresses to use as CCN recipients that will receive a copy of unknown-device notice, mainly addressed to the involved user.
  | @since: 5.10.0

* | ``security.knowndeviceverification.netwhitelist`` [ comma separated network list ]
  | List of network addresses that will be considered trusted. IP addresses belonging to this networks, will be treated as safe clients and so no report will be sent. Networks are specified in CIDR format.
  | Example:
  | ``192.168.0.0/24`` or ``192.168.0.0/24,192.168.1.1/32``
  | @since: 5.10.0

.. _OTP-settings-section:

OTP Settings
------------

* | ``otp.enabled`` [ true | false ]
  | Enable or disable One Time Password (Two Factors Authentication) globally.

* | ``otp.provider.sonicleauth.kvi`` [ seconds ]
  | Overrides default provider key validation interval (KVI).

* | ``otp.trust.addresses`` [ IPs | Networks ]
  | List of comma separated IP addresses and/or networks to be trusted against OTP. You may specify your internal LAN here to disable OTP internally.

* | ``otp.trust.device.enabled`` [ true | false ]
  | Enable or disable trust option during first OTP access. If enabled, a checkbox will be available to the user during OTP access, allowing to specify "trust this device" from now on. Defaults to true.

* | ``otp.trust.device.duration`` [ days ]
  | Duration of the cookie used for trusting the device. Defaults to 0 (forever).

.. _FAX-settings-section:

FAX Settings
------------

* | ``fax.filetypes`` [ file-extensions ]
  | A list of comma separated attachment file extensions supported by the fax provider.

* | ``fax.maxrecipients`` [ number ]
  | Maximum number of fax recipients supported by the fax provider. Defaults to unlimited.

* | ``fax.pattern`` [ pattern ]
  | The pattern to transform fax numbers into emails for the fax provider, for example "{number}@fax.provider.com"

* | ``fax.subject`` [ subject ]
  | A fixed subject to be used with the fax provider. If not specified, user will be able to write its own subject.

* | ``fax.smtp.host`` [ host ]
  | In case of specific fax smtp gateways, you may specify here the host to be used. Defaults to WebTop SMTP host.

* | ``fax.smtp.port`` [ port ]
  | In case of specific fax smtp gateways, you may specify here the port to be used. Defaults to WebTop SMTP port.

.. _SMS-settings-section:

SMS integration Settings
------------------------

* | ``sms.provider`` [ smshosting | twilio ]
  | SMS provider name. Currently only SMS Hosting and Twilio are supported.
  | @since: 5.2.4

* | ``sms.provider.webrest.user`` [ user-or-sid ]
  | Specifies a global authorization user or SID to access the SMS provider
  | @since: 5.2.4

* | ``sms.provider.webrest.password`` [ password-or-token ]
  | Specifies a global authorization password or token to access the SMS provider
  | @since: 5.2.4

* | ``sms.provider.webrest.url`` [ url ]
  | Optional. If specified, overrides the baseURL of provider implemenation (really useful only for ``smshosting`` provider). Use only in emergency cases, each provider already knows its own URL to reach.
  | @since: 5.2.4

* | ``sms.sender`` [ default-sender ]
  | Sepecifies the default sender when sending SMS: number (max 16 chars) or name (max 11 chars).
  | The user has its own setting panel to override this sender with his own, in General / SMS.
  | @since: 5.3.1

.. _PBX-settings-section:

PBX integration Settings
------------------------

* | ``pbx.provider`` [ nethvoice ]
  | PBX provider name. Currently only NethVoice is supported.
  | @since: 5.2.0

* | ``pbx.provider.nethvoice.webrest.url`` [ url ]
  | Specifies the NethVoice base URL to access its webrest APIs
  | @since: 5.2.0

.. _GeoIP-settings-section:

IP Geolocation integration Settings
-----------------------------------

* | ``geolocation.provider`` [ ipstack ]
  | IP geolocation provider name. Currently only Ipstack is supported.
  | @since: 5.10.0

* | ``geolocation.ipstack.apikey`` [ ipstack-api-key ]
  | Ipstack service API key. Create an account at https://ipstack.com/.
  | @since: 5.10.0

.. _core-meeting-settings-section:

Meeting integration Settings
----------------------------

* | ``meeting.popular.providers`` [ comma separated theme entries list ]
  | Entries in the form of "name=url" (service name and its conference base URL) representing popular meeting services available online. Domain wildcards are supported by adding "\*." as subdomain placeholder.
  | Defaults to: ``Google Meet=https://meet.google.com/,Microsoft Teams=https://teams.microsoft.com/l/meetup-join/,Zoom=https://*.zoom.us/j/,Jitsi Meet=https://meet.jit.si/``
  | @since: 5.10.0

* | ``meeting.provider`` [jitsi]
  | Meeting platform provider name. Currently only Jitsi is supported.
  | @since: 5.10.0

* | ``meeting.jitsi.name`` [ string ]
  | (only for jitsi provider)
  | The name of the service to refer to within the application. Defaults to ``Jitsi Meet``.
  | @since: 5.10.0

* | ``meeting.jitsi.url`` [ string ]
  | (only for jitsi provider)
  | The URL at which the meeting service is served. Required, E.g. ``https://meet.jit.si/``.
  | @since: 5.10.0

* | ``meeting.jitsi.meetingid.prependusername`` [ boolean ]
  | (only for jitsi provider)
  | Specifies whether to prepend user's username to generated meeting IDs. Defaults to ``false``.
  | @since: 5.10.1

.. _core-docserver-settings-section:

DocumentServer integration Settings
-----------------------------------

* | ``documentserver.enabled`` [ true | false ]
  | Enable or disable DocumentServer integration.
  | @since: 5.4.0

* | ``documentserver.public.url`` [ url ]
  | Specifies how the DocumentServer is reachable externally (from public network or internet).
  | This is the base URL used to build the location path at which the browser can load the DocumentServer's client JavaScript API.
  | @since: 5.4.0

* | ``documentserver.local.url`` [ url ] (not used yet)
  | Specifies how the DocumentServer is reachable internally (from local network).
  | @since: 5.4.0

* | ``documentserver.loopback.url`` [ url ]
  | Specifies how WebTop is reachable by the DocumentServer.
  | This is the base URL used to build the location path at which the DocumentServer can contact WebTop in order to handle documents operations.
  | This is usually an internal URL if both WebTop and DocumentServer reside on the same network.
  | @since: 5.4.0

* | ``documentserver.secret.out`` [ string ]
  | Specifies the secret shared key to use for outgoing communications to the DocumentServer. WebTop will sign outgoing calls using this key.
  | Since that HS256 algorithm is used to generate JWT token, a secret key of 256bits (32 chars) or more is required.
  | @since: 5.4.0

* | ``documentserver.secret.in`` [ string ]
  | Specifies the secret shared key to use for incoming communications from the DocumentServer. WebTop will decrypt incoming calls using this key.
  | Since that HS256 algorithm is used to check JWT token's signature, a secret key of 256bits (32 chars) or more is required.
  | @since: 5.4.0

.. warning::
  Shared key specified at ``documentserver.secret.in`` is cached for speeding up request filtering, you have to restart the application upon each changes.
