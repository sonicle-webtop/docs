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


Installation instructions available from GitHub
-----------------------------------------------

* `Build <https://github.com/sonicle/sonicle-webtop5-gate#sonicle-webtop-5-build-environment>`_

* `Database initialization <https://github.com/sonicle/sonicle-webtop5-gate#database-initialization>`_

* `Deployment <https://github.com/sonicle/sonicle-webtop5-gate#deployment>`_

* `First Administration Steps <https://github.com/sonicle/sonicle-webtop5-gate#administration>`_
