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
  2. Copy the file :file:`jcharset-2.0.jar` to your :file:`$JAVA_HOME/jre/lib/ext` directory. The JAR file has to be in exactly this directory for the class loader to pick it up.
  3. Restart Tomcat if it is running.


Apache Tomcat
^^^^^^^^^^^^^

WebTop runs greatly on Tomcat 8.5 and 8.0, but we advice to use the most recent one.

.. warning::
  WebTop may run on the older version 7 but is not reccomended due to early WebSocket support (with many reported bugs) and default use of BIO connectors.


Configuration
-------------

.. _configuration-properties-section:

Properties
^^^^^^^^^^

WebTop supports some configuration and debugging settings that can be enabled through Java properties.
Properties can be specified in two ways:

1. System property: these properties are usually set by passing the ``-D`` flag to the Java virtual machine.
2. WebTop property: these properties are defined in a specific property file that is loaded during startup.

In order to enable the WebTop property way, the system property ``webtop.etc.dir`` must be specified first, this will instruct the application where to find customized configuration files.
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
  ``${PROP_ETC_DIR}`` is the value of ``webtop.etc.dir`` system property and ``${WEBAPP_NAME}`` is the web-application context-name (without any version info).


.. warning::
  In order to look for external configuration files, the system property ``webtop.etc.dir`` must be specified pointing to a valid location. See above.


.. _configuration-logging-section:

Logging
^^^^^^^

.. warning::
  Starting from WebTop Core 5.7.0 is no longer necessary (and discouraged) to edit the :file:`logback.xml` file in order to control log output location and type.

By default WebTop will log every message in the webapps's standard output, the Tomcat's :file:`catalina.out` file.
If you want to change this default behaviour you need to set some JVM global variables (or set them into WebTop property file discussed above):

* | ``webtop.log.target``
  | Specifies the destination used for writing log entries. Defaults to ``console``.
  | - ``console``: Writes log entries to Tomcat's standard output.
  | - ``file``: Writes log entries to a file.

* | ``webtop.log.dir``
  | Directory where to store log files. Defaults to ``/var/log/webtop``.
  | This is only used if the target is ``file``.

* | ``webtop.log.file.basename``
  | The base filename of the log file (extension `.log` will be automatically appended). Note that appenders may append some other text to it. (eg. webtop.2019-01-01)
  | Defaults to the webapp's full context name (including context version if present).
  | This is only used if the target is ``file``.

* | ``webtop.log.file.policy``
  | The policy to apply when writing log files. Defaults to ``rolling``.
  | - ``simple``: Writes to straight file (any rolling policy support is demanded to OS).
  | - ``rolling``: Writes to a file using a rolling appender. Currently only time-based policy is supported: 15days of max history with 150MB of total size cap.
  | This is only used if the target is ``file``.

Due to some differences between components logging needs, the logging level cannot be set using a single variable like above.
The :file:`logback.xml` file is refreshed every 30s, so you can control your desired logging level by manually updating the level value in correspondence of each `<logger>` elements.


Installation instructions available from GitHub
-----------------------------------------------

* `Build <https://github.com/sonicle/sonicle-webtop5-gate#sonicle-webtop-5-build-environment>`_

* `Database initialization <https://github.com/sonicle/sonicle-webtop5-gate#database-initialization>`_

* `Deployment <https://github.com/sonicle/sonicle-webtop5-gate#deployment>`_

* `First Administration Steps <https://github.com/sonicle/sonicle-webtop5-gate#administration>`_
