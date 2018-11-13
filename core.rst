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

* | ``syslog.enabled`` [ true | false ]
  | If enabled, WebTop will log various actions into a dedicated Postgres table.

* | ``system.language`` [ en | it | ... ]
  | Defines system default language locale.

* | ``system.country`` [ US | IT | ... ]
  | Defines system default country locale.

* | ``tomcat.manager.uri`` [ uri-to-tomcat-manager ]
  | Defines how to reach Tomcat manager applicaton. This is necessary when running Tomcat webapp versioning to run different versions of WebTop during upgrades. Each instance will use this URL to detect other instances and decide which one is latest: only the latest will run background processes that need to be unique.

* | ``maintenance.enabled`` [ true | false ]
  | Indicates if maintenance management is active or not. Maintenance state is automatically managed by the system when problems occurs during version upgrade. This setting should be used only to disable this feature, active by default.

* | ``whatsnew.enabled`` [ true | false ]
  | Specifies if What's New visualization to users is enabled.

* | ``launcher.links`` [ json-array-of-link-objects ]
  | Specifies a list of links to be displayed as link buttons in viewport's launcher.
  | List definitiron must be specified as a JSON array. Each element is an object with the following fields:
  | - ``href``: The URL of the page the link goes to.
  | - ``text``: The text to display as tooltip. (optional)
  | - ``icon``: The URL of the image to display as button icon. In order to avoid scaling problems, vector images should be used.
  |
  | Example:

  ::

    [
      {
        'href': 'https://www.google.it/',
        'text': 'Google',
        'icon': 'https://upload.wikimedia.org/wikipedia/commons/5/53/Google_%22G%22_Logo.svg'
      }, {
        'href': 'https://the/url/to/open',
        'text': 'The link text',
        'icon': 'https://the/icon/url'
      }
    ]

  | @since: 5.3.2

* | ``ajax.specialtimeout`` [ milliseconds ]
  | Allow override of default timeout on proxies/requests that may take longer than 30 seconds.
  | Currently used only by mail message grid to allow longer search queries.
  | @since: 5.3.3

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
  | Defines the default theme for users. Defaults to ``crisp``.

* | ``default.layout`` [ default | compact ]
  | Defines the default layout for users. Defaults to ``default``.

* | ``default.laf`` [ default ]
  | Defines the default look and feel for users. This may define an alternative icon set. Defaults to ``default``.

* | ``default.rtl`` [ true | false ] (not yet used)
  | If true, the web interface is delivered in right-to-left mode. Defaults to ``false``.

* | ``default.viewport.header.scale`` [ small | medium | large ]
  | Defines the default viewport header's scale. Defaults to ``small``.

* | ``default.startup.service`` [ core | mail | calendar | contacts | tasks | vfs ]
  | The default service to start with after login.

* | ``default.notifications.desktop`` [ never | always | auto ]
  | The default desktop notifications mode. Defaults to ``auto``.
  | ``never``: Desktop notifications will not be displayed.
  | ``always``: Desktop notification will be always displayed.
  | ``auto``: Desktop notifications will be displayed only if webapp is in background.
  | NB: A consent screen will be prompted by the browser if necessary.

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

.. _OTP-settings-section:

OTP Settings
---------------

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

.. _PBX-settings-section:

PBX Settings
------------

* | ``pbx.provider`` [ nethvoice ]
  | PBX provider name. Currently only NethVoice is supported.
  | @since: 5.2.0

* | ``pbx.provider.nethvoice.webrest.url`` [ url ]
  | Specifies the NethVoice base URL to access its webrest APIs
  | @since: 5.2.0

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

SMS Settings
------------

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

.. _core-docserver-settings-section:

DocumentServer Settings
-----------------------

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
  | Since that algorithm HS256 is used to generate JWT token, a secret key of 256bits (32 chars) or more is required.
  | @since: 5.4.0

* | ``documentserver.secret.in`` [ string ]
  | Specifies the secret shared key to use for incoming communications from the DocumentServer. WebTop will decrypt incoming calls using this key.
  | Since that algorithm HS256 is used check JWT token's signature, a secret key of 256bits (32 chars) or more is required.
  | @since: 5.4.0
