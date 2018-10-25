[Golang] XML Parsing Example (4)
################################

:date: 2015-02-24 10:09
:tags: Go, Golang, XML, html
:category: Go
:summary: How to read XML/HTML files in Go programming language (for newbie)
          - Read multiple direct child elements.
:adsu: yes


In this exmaple, we will parse a *div* element with multiple *span* child
elements:

.. show_github_file:: siongui userpages content/code/go-xml/example-4.xml

To parse multiple *span* child elements, the struct field in *div* struct of
previous example [3]_:

.. code-block:: go

    ChildSpan	span

becomes:

.. code-block:: go

    SpanList	[]span		`xml:"span"`

The type :code:`span` becomes :code:`[]span`, and **`xml:"span`** is added to
indicate the tag name of child elements.

.. adsu:: 2

`Run code on Go Playground <https://play.golang.org/p/2s4GK0plEk>`_

.. show_github_file:: siongui userpages content/code/go-xml/parse-4.go
.. adsu:: 3

The output result:

.. code-block:: txt

  {{ div} [{SpanText1} {SpanText2} {SpanText3}]}

.. note::

  If you uncomment the following line:

  .. code-block:: go

    //	XMLName		xml.Name	`xml:"span"`

  The output will be:

  .. code-block:: txt

    {{ div} [{{ span} SpanText1} {{ span} SpanText2} {{ span} SpanText3}]}



Tested on: ``Ubuntu Linux 14.10``, ``Go 1.4``.

----

*[Golang] XML Parsing Example* series:

.. [1] `[Golang] XML Parsing Example (1) <{filename}../17/go-parse-xml-example-1%en.rst>`_

.. [2] `[Golang] XML Parsing Example (2) <{filename}../19/go-parse-xml-example-2%en.rst>`_

.. [3] `[Golang] XML Parsing Example (3) <{filename}../21/go-parse-xml-example-3%en.rst>`_

.. [4] `[Golang] XML Parsing Example (4) <{filename}go-parse-xml-example-4%en.rst>`_

.. [5] `[Golang] XML Parsing Example (5) - Parse OPML <{filename}../25/go-parse-opml%en.rst>`_

.. [6] `[Golang] XML Parsing Example (6) - Parse OPML Concisely <{filename}../26/go-parse-opml-concisely%en.rst>`_

.. [7] `[Golang] XML Parsing Example (7) - Parse RSS 2.0 <{filename}../27/go-parse-rss2%en.rst>`_

.. [8] `[Golang] XML Parsing Example (8) - Parse Atom 1.0 <{filename}../28/go-parse-atom%en.rst>`_

.. [9] `[Golang] Convert Atom to RSS <{filename}../../03/02/go-convert-atom-to-rss-feed%en.rst>`_

.. [10] `[Golang] Parse Web Feed - RSS and Atom <{filename}../../03/03/go-parse-web-feed-rss-atom%en.rst>`_

----

.. [a] `XML to Go struct : golang <https://old.reddit.com/r/golang/comments/9r1fgc/xml_to_go_struct/>`_
