===============
Document Server
===============

This integration enables user to view and edit documents from WebTop using ONLYOFFICE Document Server.
The following document formats can be handled through the provided editor: doc, docm, docx, dot, dotm, dotx, epub, fodt, htm, html, mht, odt, ott, pdf, rtf, txt, djvu, xps, csv, fods, ods, ots, xls, xlsm, xlsx, xlt, xltm, xltx, fodp, odp, otp, pot, potm, potx, pps, ppsm, ppsx, ppt, pptm, pptx.
Collaboration is also enabled, allowing multiple users to collaborate in real time and to save back those changes to WebTop.

.. _doc-server-section:

Installation
------------

You will need an instance of ONLYOFFICE Document Server (version 4.3.6 and later) that is resolvable and reachable both from WebTop and any remote client. ONLYOFFICE Document Server must also be able to POST to WebTop directly.
For installation instructions, please refers to the official ONLYOFFICE Document Server documentation page: `Document Server for Linux <https://helpcenter.onlyoffice.com/server/linux/document/linux-installation.aspx>`_.

Configuration
-------------

To restrict the access to ONLYOFFICE Document Server, for security reasons and data integrity the encrypted signature feature can be used.
First of all you need to define a shared *Secret key* to use: you can just easily use a strong password (eg. `https://www.grc.com/passwords.htm <https://www.grc.com/passwords.htm>`_).

::

  C87AF72A053479E8E248E0F8F6307113D9D857E5BC4B5D5BA5A23EA5C121E801

Then, in the ONLYOFFICE Document Server `config file <https://api.onlyoffice.com/editors/signature/>`_ specify the secret key and enable the validation.

::

  {
    "services": {
      "CoAuthoring": {
        "secret": {
          "browser": {
            "string": "C87AF72A053479E8E248E0F8F6307113D9D857E5BC4B5D5BA5A23EA5C121E801"
          },
          "inbox": {
            "string": "C87AF72A053479E8E248E0F8F6307113D9D857E5BC4B5D5BA5A23EA5C121E801"
          },
          "outbox": {
            "string": "C87AF72A053479E8E248E0F8F6307113D9D857E5BC4B5D5BA5A23EA5C121E801"
          }
        },
        "token": {
          "enable": {
            "browser": true,
            "request": {
              "inbox": true,
              "outbox": true
            }
          }
        }
      }
    }
  }

Finally specify the same *Secret key* in WebTop's settings (see :ref:`core-docserver-settings-section`) at ``documentserver.secret.out`` and ``documentserver.secret.in``.

.. warning::
  For now all keys must point to the same value. This behaviour could change in future.
