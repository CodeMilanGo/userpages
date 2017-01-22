Python Library xml.dom.minidom Howto (1)
########################################

:tags: DOM, html, minidom, Python, XML
:category: Python
:summary: Python XML/HTML manipulation primer of xml.dom.minidom
:adsu: yes


CREATE A DOCUMENT
=================

Python provides a simple library which can be used for XML/HTML manipulation. Here I want to share some of what I learned to beginners on how to manipulate XML/HTML in Python.

First, we create a document DOM with root element called 'html'. Here is the sample code:

.. show_github_file:: siongui userpages content/articles/2012/05/24/minidom-howto-1.py

In line 7 and 8, we create a dom with root element 'html'. If you run the the script, the following result will show up.

.. code-block:: bash

    <?xml version="1.0" ?><html/>

In the next post [2]_, we will show how to add a text node to the root element.

----

*Python Library xml.dom.minidom Howto* series:

.. [1] `Python Library xml.dom.minidom Howto (1) <{filename}python-xml-dom-minidom-howto-1%en.rst>`_

.. [2] `Python Library xml.dom.minidom Howto (2) <{filename}python-xml-dom-minidom-howto-2%en.rst>`_

.. [3] `Python Library xml.dom.minidom Howto (3) <{filename}python-xml-dom-minidom-howto-3%en.rst>`_

.. [4] `Python Library xml.dom.minidom Howto (4) <{filename}python-xml-dom-minidom-howto-4%en.rst>`_

.. [5] `Python Library xml.dom.minidom Howto (5) <{filename}python-xml-dom-minidom-howto-5%en.rst>`_

.. [6] `Python Library xml.dom.minidom Howto (6) <{filename}python-xml-dom-minidom-howto-6%en.rst>`_

.. [7] `Python Library xml.dom.minidom Howto (7) <{filename}../27/python-xml-dom-minidom-howto-7%en.rst>`_
