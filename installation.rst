============
Installation
============

WebTop Installation

Requirements
------------

Operating system
^^^^^^^^^^^^^^^^

WebTop should run on most Unix, Linux, macOS and Windows systems as long as Java and Apache Tomcat are available on this platform.


Java Virtual Machine
^^^^^^^^^^^^^^^^^^^^

The required JRE version for a given WebTop release is:

+----------------+-------------+
| WebTop release | JRE version |
+================+=============+
| 5.2.0 and up   | Java 8      |
+----------------+-------------+
| 5.1.X          | Java 7      |
+----------------+-------------+
| 5.0.X          | Java 7      |
+----------------+-------------+

.. warning::
  Java is missing support to UTF-7 so if you want to add it, you need to plug a third-party encoding implementation on the JRE:

  1. Download the JCharset jar from `https://www.freeutils.net/source/jcharset/ <https://www.freeutils.net/source/jcharset/>`_.
  2. Copy the file ``jcharset-2.0.jar`` to your ``$JAVA_HOME/jre/lib/ext`` directory. The JAR file has to be in exactly this directory for the class loader to pick it up.
  3. Restart Tomcat if it is running.

PostgreSQL Database
^^^^^^^^^^^^^^^^^^

The required DBMS version for a given WebTop release is:

+----------------+----------------------+
| WebTop release | PostgreSQL version   |
+================+======================+
| 5.X.X and up   | 9.1 or greater       |
|                | with tablefunc,      |
|                | rrule_functions      |
+----------------+----------------------+
| 5.11.0 and up  | 9.1 or greater       |
|                | with tablefunc       |
+----------------+----------------------+
| 5.0.X and up   | 9.1 or greater       |
+----------------+----------------------+

tablefunc
"""""""""

This package can be installed issuing the following SQL command:

::

  CREATE EXTENSION tablefunc;

Objects will be defined under the main ``public`` schema.

.. note::

  If the above method do not work, you can always add object manually running ``tablefunc.sql`` SQL file against WebTop's database. You can find the file under PostgreSQL's ``\contrib`` folder.

rrule_functions
"""""""""""""""

This package is not part of the official PostgreSQL extensions, neither a contrib module. Functions are provided by the great `DAViCal <https://www.davical.org/>`_ project.

You can add these functions manually running `rrule_functions.sql <https://gitlab.com/davical-project/davical/-/blob/r1.1.10/dba/rrule_functions.sql>`_ file against WebTop's database.

Apache Tomcat
^^^^^^^^^^^^^

WebTop runs greatly on Tomcat 8.5 and 8.0, but we advice to use the most recent one.

.. warning::
  WebTop may run on the older version 7 but is not reccomended due to early WebSocket support (with many reported bugs) and default use of BIO connectors.

Tomcat supports ``Parallel deployment`` that allows to deploy multiple versions of a Web application with the same context path at the same time. You can have more info `here <https://tomcat.apache.org/tomcat-8.5-doc/config/context.html#Parallel_deployment>`_.

If you are planning to use this useful feature, each WebTop application instance must be made aware of the existence of the others in order to properly handle all the background tasks that compete for the data.
Each instance will periodically monitor Tomcat in order to discover new instances and when found, it put itself in passive mode, gracefully shutting down every task. The newer instance will be the only one instance in active mode.

In order to implement this, you must enable access to Tomcat's management by defining a dedicated user access in ``tomcat-users.xml`` file:

::

  <user username="${MANAGER_USERNAME}" password="${MANAGER_PASSWORD}" roles="manager-script"/>

.. note::
  Where ``${MANAGER_USERNAME}`` is the choosen username and ``${MANAGER_PASSWORD}`` is the choosen password.

The next and final step is to instruct the application about this access. This can be done in two ways:

1. Use this SQL insert to apply configuration directly in Database:
   ::

     INSERT INTO "core"."settings" ("service_id", "key", "value") VALUES ('com.sonicle.webtop.core', 'tomcat.manager.uri', 'http://${MANAGER_USERNAME}:${MANAGER_PASSWORD}@localhost:${TOMCAT_PORT}/manager/text');

2. Use these properties within ``webtop.properties`` configuration file (@since: wt.5.9.0):
   ::

     webtop.tomcat.manager.uri=http://${MANAGER_USERNAME}:${MANAGER_PASSWORD}@localhost:${TOMCAT_PORT}/manager/text

.. note::
  Where ``${TOMCAT_PORT}`` is the configured Tomcat's port and ``${MANAGER_USERNAME}``, ``${MANAGER_PASSWORD}`` are the values choosen above.


Configuration
-------------

.. _configuration-properties-section:

Properties
^^^^^^^^^^

WebTop supports some configuration and debugging settings that can be enabled through Java properties to control application behaviour.
Properties can be specified in two ways:

1. Startup/System property: these properties are usually set by passing the ``-D`` flag to the Java virtual machine. This is the classic operative mode and so no other configuration is needed.
2. WebTop property: these properties are defined in a specific property file that is loaded during startup. This allow to not fill up the Java command-line, making configuration more clear.

In order to enable this second operative mode, the startup/system property ``webtop.etc.dir`` must be specified firstly, this will instruct the application where to find customized configuration files.
Then the property file will be looked-up using the following logic:

1. Startup process tries to find a file called ``webtop.properties`` in ``${PROP_ETC_DIR}`` directory.
2. Then, it checks the file ``webtop.properties`` in ``${PROP_ETC_DIR}/${WEBAPP_NAME}`` directory.

If valid files can be found in both locations, properties will be merged keeping precedence to the most specific file (the second one).

.. note::
  ``${PROP_ETC_DIR}`` is the value of ``webtop.etc.dir`` system property and ``${WEBAPP_NAME}`` is the web-application context-name (without any version info).


Please refer to `this page <https://code.sonicle.com/projects/WEBTOP/repos/webtop-core/browse/src/main/java/com/sonicle/webtop/core/app/WebTopProps.java>`_ to extract a list of supported properties.


.. _configuration-database-section:

Database
^^^^^^^^

Database configuration relies on a specific configuration file that will be looked-up following the sequence below:

1. Startup process tries to find a file called ``data-sources.xml`` in ``${PROP_ETC_DIR}/${WEBAPP_NAME}`` folder.
2. If no such file is found, it checks the file ``data-sources.xml`` in ``META-INF`` folder inside the application context. Note that this file is always available but it contains a default configuration.

.. note::
  Where ``${PROP_ETC_DIR}`` is the value of ``webtop.etc.dir`` system property and ``${WEBAPP_NAME}`` is the web-application context-name (without any version info).


.. warning::
  In order to look for external configuration files, the system property ``webtop.etc.dir`` must be specified pointing to a valid location. See above.


.. _configuration-logging-section:

Logging
^^^^^^^

.. warning::
  Starting from WebTop Core 5.7.0 is no longer necessary (and discouraged) to edit the :file:`logback.xml` file in order to control log output location and type.

By default WebTop will log every message in the webapps's standard output, the Tomcat's :file:`catalina.out` file.
If you want to change this default behaviour you need to set some JVM global variables (or set them into WebTop property file discussed above):

* | ``webtop.log.dir``
  | Directory where to store log files. Defaults to ``/var/log/webtop``.
  | This is only used if the target is ``file``.

* | ``webtop.log.file.basename``
  | The base filename of the log file (extension `.log` will be automatically appended). Note that appenders may append some other text to it. (eg. webtop.2019-01-01)
  | Defaults to the webapp's full context name (including context version if present).
  | This is only used if the target is ``file``.

* | ``webtop.log.file.policy``
  | The policy to apply when writing main (application) log file. Defaults to ``rolling``.
  | - ``simple``: Writes to straight file (any rolling policy support is demanded to OS).
  | - ``rolling``: Writes to a file using a rolling appender. Currently only time-based policy is supported: 15days of max history with 150MB of total size cap.
  | This is only used if the target is ``file``.

* | ``webtop.log.target``
  | Specifies the destination used for writing main (application) log entries. Defaults to ``console``.
  | - ``console``: Writes log entries to Tomcat's standard output.
  | - ``file``: Writes log entries to a file.

* | ``webtop.log.auth.target``
  | Specifies the destination used for writing auth log entries. Defaults to ``none``.
  | - ``none``: Output disabled.
  | - ``file``: Writes log entries to a file (whose name is the basename with ``_auth`` suffix appended).
  | - ``syslog``: Writes log entries to a remote syslog (see below for hostname and port defaults).
  | @since: 5.10.0

* | ``webtop.logback.syslog.host``
  | Specifies the hostname of the remote syslog server used by syslog appender. Defaults to ``localhost``.
  | @since: 5.10.1

* | ``webtop.logback.syslog.port``
  | Specifies the port of the remote syslog server used by syslog appender. Defaults to ``514``.
  | @since: 5.10.1

Due to some differences between components logging needs, the logging level cannot be set using a single variable like above.
The :file:`logback.xml` file is refreshed every 30s, so you can control your desired logging level by manually updating the level value in correspondence of each `<logger>` elements.


Installation instructions available from GitHub
-----------------------------------------------

* `Build <https://github.com/sonicle/sonicle-webtop5-gate#sonicle-webtop-5-build-environment>`_

* `Database initialization <https://github.com/sonicle/sonicle-webtop5-gate#database-initialization>`_

* `Deployment <https://github.com/sonicle/sonicle-webtop5-gate#deployment>`_

* `First Administration Steps <https://github.com/sonicle/sonicle-webtop5-gate#administration>`_
