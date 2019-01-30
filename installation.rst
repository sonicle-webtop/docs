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

.. _configuration-logging-section:

Logging
^^^^^^^

.. warning::
  Starting from WebTop Core 5.5.1 is no longer necessary (and discouraged) to edit the :file:`logback.xml` file in order to control log output location and type.

By default WebTop will log every message in the webapps's standard output, the Tomcat's :file:`catalina.out` file.
If you want to change this default behaviour you need to set some JVM global variables:

* | ``webtop.log.appender``
  | Specifies the pre-configured appender to use for writing log entries. Defaults to ``stdout``.
  | - ``stdout``: Writes to Tomcat's standard output
  | - ``file``: Writes to a straight file (any rolling policy support is demanded to OS)
  | - ``rollingfile``: Writes to a file using a time-based rolling policy (file is rolled every day using a max history of 15 days and 150MB of size cap each file)

* | ``webtop.log.dir``
  | Directory where to store log files. Defaults to ``/var/log/webtop``.
  | This is only used if the appender targets a file output.

* | ``webtop.log.file.basename``
  | The base filename of the log file (extension `.log` will be automatically appended).
  | Defaults to the webapp's full context name (including context version if present).
  | This is only used if the appender targets a file output.

Due to some differences between components logging needs, the logging level cannot be set using a single variable like above.
The :file:`logback.xml` file is refreshed every 30s, so you can control your desired logging level by manually updating the level value in correspondence of each `<logger>` elements.


Installation instructions available from GitHub
-----------------------------------------------

* `Build <https://github.com/sonicle/sonicle-webtop5-gate#sonicle-webtop-5-build-environment>`_

* `Database initialization <https://github.com/sonicle/sonicle-webtop5-gate#database-initialization>`_

* `Deployment <https://github.com/sonicle/sonicle-webtop5-gate#deployment>`_

* `First Administration Steps <https://github.com/sonicle/sonicle-webtop5-gate#administration>`_
