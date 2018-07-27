==========
PEC Bridge
==========

PEC Bridge is a specific standalone commercial service for managing Itlaian PEC standard.

This service runs as a deamon, reading configurations from both a startup xml file and a possible WebTop database, allowing integration with WebTop.
It will periodically scan the configured PEC accounts and bring the emails into a local imap account.
It will also be able to run as an SMTP bridge, running on a dedicated port as the official SMTP server.
Any email sent through this port will be matched against the configured PEC accounts, so to use the specific PEC prodivder matched by the sender (a PEC sender).
Any non matched PEC sender will be run through the configured default SMTP server.
This allows to integrate corporate PEC accounts into the WebTop infrastructure, and share the synchronized PEC accounts as normal accounts throughout the domain.

WebTop 5 Administration panel allows for creating the list of PEC accounts to be mantained by PEC Bridge.

Configuration
#############

The main startup file is a config.xml containing all the possible settings::

  <sonicle-pec-bridge port="10125">
    <default host="localhost" port="10026" starttls="false" auth="false" debug="false" />
    <webtop driver="org.postgresql.Driver" uri="jdbc:postgresql://localhost/webtop5" user="postgres" password="the-password" />
    <fetch delay="60" />
  </sonicle-pec-bridge>

