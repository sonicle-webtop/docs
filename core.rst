====
Core
====

WebTop Core Services

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

* | ``public.url`` [ the-public-url ]
  | This URL defines how WebTop is reachable from users. It will be used to build various URLs, such as public cloud file URLs.

* | ``public.url`` [ the-public-url ]
  | This URL defines how WebTop is reachable from users. It will be used to build various URLs, such as public cloud file URLs.

.. _core-defaults-settings-section:

Defaults Settings
-----------------

* | ``default.theme`` [ crisp | neptune | classic | gray | ... ]
  | Defines the default theme for users.  

* | ``default.layout`` [ webtop | outlook | mozilla | ... ]
  | Defines the default layout for users.  

* | ``default.laf`` [ webtop | ... ]
  | Defines the default look and feel for users. This may define an alternative icon set.

* | ``default.rtl`` [ true | false ]
  | If true, the web interface is delivered in right-to-left mode. Defaults to false.

* | ``default.startup.service`` [ core | mail | calendar | contacts | tasks | vfs ]
  | The default service to start with after login.

* | ``default.notifications.desktop`` [ never | always | background ]
  | The default desktop notifications mode.

.. _smtp-settings-section:

SMTP Settings
--------------

* | ``smtp.host`` [ the-smtp-host ]
  | Defines the SMTP host for outgoing mails.

* | ``smtp.port`` [ the-smtp-port ]
  | Defines the SMTP port to be used on the defined SMTP host.

.. _xmpp-settings-section:

XMPP Settings
--------------

* | ``xmpp.host`` [ the-xmpp-host ]
  | Defines the XMPP host for IM services.

* | ``xmpp.port`` [ the-xmpp-port ]
  | Defines the XMPP port to be used on the defined XMPP host.

* | ``xmpp.muc.subdomain`` [ the-xmpp-multiuserchat-subdomain ]
  | Defines the XMPP subdomain for multi user chat. Defaults to "conference".

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


* | ``pbx.provider.nethvoice.webrest.url`` [ nethvoice-base-url-to-webrest ]
  | Specifies the NethVoice base url to access its webrest APIs

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
  | A fixed subject to be used with the fax provider. If not specified, user will be able to write its own subject. Defaults is none.

* | ``fax.smtp.host`` [ fax-smtp-host ]
  | In case of specific fax smtp gateways, you may specify here the host to be used. Defaults to WebTop SMTP host.

* | ``fax.smtp.port`` [ fax-smtp-port ]
  | In case of specific fax smtp gateways, you may specify here the port to be used. Defaults to WebTop SMTP port.
