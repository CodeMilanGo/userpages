[Python] Internationalization (i18n) of Python Application by GNU gettext Tools
###############################################################################

:date: 2016-01-14T20:28+08:00
:tags: Python, i18n, Locale, gettext, List Files in Directory
:category: Python
:summary: Internationalization (i18n_) of Python_ applications by GNU gettext_
          tools. This post shows how to use PO_ and MO_ files in Python_.
:adsu: yes


GNU gettext_ tools are great for creating i18n (web) applications. In this post,
assume that PO_ and MO_ files are ready and we will use the PO_ and MO_ files to
let Python_ applications speak local languages. If you do not know what PO_ or
MO_ files are, or you do not know how to create them by gettext_ tools, please
read my previous post [1]_ first. If you want to know how to render HTML by
Jinja2_ template engine with the translated texts in PO_ and MO_ files in your
Python_ web application, please refer to [9]_.


PO_ and MO_ files
+++++++++++++++++

I will show how to use MO_ and PO_ files by example. In the example, we support
two locale_, *zh_TW (Traditional Chinese)* and *vi_VN (Vietnamese)*. The zh_TW
PO file are located at ``locale/zh_TW/LC_MESSAGES/messages.po`` and vi_VN PO
file are located at ``locale/vi_VN/LC_MESSAGES/messages.po``.

zh_TW PO file ``locale/zh_TW/LC_MESSAGES/messages.po``:

.. show_github_file:: siongui userpages content/code/python-i18n-gettext/locale/zh_TW/LC_MESSAGES/messages.po
.. adsu:: 2

vi_VN PO file ``locale/vi_VN/LC_MESSAGES/messages.po``:

.. show_github_file:: siongui userpages content/code/python-i18n-gettext/locale/vi_VN/LC_MESSAGES/messages.po
.. adsu:: 3

Generate corresponding MO files by msgfmt_. Put MO files together with PO files.
So we have two PO files and two MO files:

.. code-block:: txt

  locale/zh_TW/LC_MESSAGES/messages.po
  locale/zh_TW/LC_MESSAGES/messages.mo
  locale/vi_VN/LC_MESSAGES/messages.po
  locale/vi_VN/LC_MESSAGES/messages.mo


Source Code
+++++++++++

Now we can let Python_ application speak local language. The
application-independent code is put in the following module:

.. show_github_file:: siongui userpages content/code/python-i18n-gettext/i18n.py
.. adsu:: 4

Use above module to get translated texts:

.. show_github_file:: siongui userpages content/code/python-i18n-gettext/demo.py
.. adsu:: 5

.. note::

  The *domain* in this case is **messages**. If you name your PO_ and MO_ file
  as **hello**, the *domain* becomes **hello**.

  .. code-block:: txt

    locale/zh_TW/LC_MESSAGES/hello.po
    locale/zh_TW/LC_MESSAGES/hello.mo
    locale/vi_VN/LC_MESSAGES/hello.po
    locale/vi_VN/LC_MESSAGES/hello.mo


Output of Demo
++++++++++++++

.. code-block:: txt

  首頁
  經典
  關於
  設定
  翻譯
  Trang chính
  Kinh điển
  Giới thiệu
  Thiết lập
  Dịch


Tested on: ``Ubuntu Linux 15.10``, ``Python 2.7.10``.

----

References:

.. [1] `Internationalization (i18n) of Web Application by GNU gettext Tools <{filename}../07/i18n-web-application-by-gnu-gettext-tools%en.rst>`_

.. [2] `22.1. gettext — Multilingual internationalization services — Python 2.7.11 documentation <https://docs.python.org/2/library/gettext.html>`_

.. [3] `Extensions — Jinja2 Documentation <http://jinja.pocoo.org/docs/extensions/#i18n-extension>`_

.. [4] `i18n support in template file (web.py) <http://webpy.org/cookbook/i18n_support_in_template_file>`_
.. adsu:: 6
.. [5] `Run-time language switch (web.py) <http://webpy.org/cookbook/runtime-language-switch>`_

.. [6] `i18n.py - webapp-improved - Google App Engine's webapp, take two - Google Project Hosting <https://code.google.com/p/webapp-improved/source/browse/webapp2_extras/i18n.py>`_

.. [7] `16.2. threading — Higher-level threading interface — Python 2.7.11 documentation <https://docs.python.org/2/library/threading.html>`_

.. [8] `[Golang] Internationalization (i18n) of Go Application by GNU gettext Tools <{filename}../08/golang-i18n-go-application-by-gnu-gettext%en.rst>`_

.. [9] `i18n Python Web Application by gettext and Jinja2 <{filename}../17/i18n-python-web-application-by-gettext-jinja2%en.rst>`_


.. _gettext: https://www.gnu.org/software/gettext/
.. _i18n: https://en.wikipedia.org/wiki/Internationalization_and_localization
.. _locale: https://en.wikipedia.org/wiki/Locale
.. _Python: https://www.python.org/
.. _PO: https://www.gnu.org/software/gettext/manual/html_node/PO-Files.html
.. _MO: https://www.gnu.org/software/gettext/manual/html_node/MO-Files.html
.. _msgfmt: https://www.gnu.org/software/gettext/manual/html_node/msgfmt-Invocation.html
.. _Jinja2: http://jinja.pocoo.org/
