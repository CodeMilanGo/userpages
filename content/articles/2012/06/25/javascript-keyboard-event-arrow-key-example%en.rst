JavaScript Keyboard Event (Arrow Key Example)
#############################################

:date: 2012-06-25 13:18
:modified: 2018-10-08T22:19+08:00
:tags: JavaScript, Keyboard Event, DOM
:category: JavaScript
:summary: Detect `arrow keystrokes`_ in JavaScript_.
:og_image: http://www.javatpoint.com/images/javascript/javascript_logo.png
:adsu: yes


This post will give an example for detecting `arrow keys`_ using JavaScript_.
For general `keyboard event`_, it is very easy to achieve by extending the
example in this post (also see references below). Try demo first:

.. raw:: html

  <div style="background-color: Azure; padding: 1rem;">

  Press Arrow Key or Any Other Key:<br><br>
  <div id="info"></div>

  </div>

.. raw:: html

  <script>
  var Key = {
    LEFT:   37,
    UP:     38,
    RIGHT:  39,
    DOWN:   40
  };

  /**
   * old IE: attachEvent
   * Firefox, Chrome, or modern browsers: addEventListener
   */
  function _addEventListener(evt, element, fn) {
    if (window.addEventListener) {
      element.addEventListener(evt, fn, false);
    }
    else {
      element.attachEvent('on'+evt, fn);
    }
  }

  function handleKeyboardEvent(evt) {
    if (!evt) {evt = window.event;} // for old IE compatible
    var keycode = evt.keyCode || evt.which; // also for cross-browser compatible

    var info = document.getElementById("info");
    switch (keycode) {
      case Key.LEFT:
        info.innerHTML += "&larr; ";
        break;
      case Key.UP:
        info.innerHTML += "&uarr; ";
        break;
      case Key.RIGHT:
        info.innerHTML += "&rarr; ";
        break;
      case Key.DOWN:
        info.innerHTML += "&darr; ";
        break;
      default:
        info.innerHTML += "SOMEKEY ";
    }
  }

  _addEventListener('keydown', document, handleKeyboardEvent);
  </script>

Source Code for Demo (*HTML*):

.. code-block:: html

  Press Arrow Key or Any Other Key:<br><br>
  <div id="info"></div>

.. adsu:: 2

Source Code for Demo (*JavaScript*):

.. code-block:: javascript

  var Key = {
    LEFT:   37,
    UP:     38,
    RIGHT:  39,
    DOWN:   40
  };

  /**
   * old IE: attachEvent
   * Firefox, Chrome, or modern browsers: addEventListener
   */
  function _addEventListener(evt, element, fn) {
    if (window.addEventListener) {
      element.addEventListener(evt, fn, false);
    }
    else {
      element.attachEvent('on'+evt, fn);
    }
  }

  function handleKeyboardEvent(evt) {
    if (!evt) {evt = window.event;} // for old IE compatible
    var keycode = evt.keyCode || evt.which; // also for cross-browser compatible

    var info = document.getElementById("info");
    switch (keycode) {
      case Key.LEFT:
        info.innerHTML += "&larr; ";
        break;
      case Key.UP:
        info.innerHTML += "&uarr; ";
        break;
      case Key.RIGHT:
        info.innerHTML += "&rarr; ";
        break;
      case Key.DOWN:
        info.innerHTML += "&darr; ";
        break;
      default:
        info.innerHTML += "SOMEKEY ";
    }
  }

  _addEventListener('keydown', document, handleKeyboardEvent);

There are three events related to keyboards: *onkeydown*, *onkeypress*,
*onkeyup*. To detect arrow keys, please use onkeydown_ (see [2]_).

According to the KeyboardEvent_ documentation on MDN_, the use of event.keyCode_
is deprecated. We should use event.key_ instead. If you need to support very old
browsers, use the example in this post. Otherwise see [5]_ for the new example
of event.key_.

.. adsu:: 3

----

**References**

.. [1] `Keyboard events | JavaScript Tutorial <https://javascript.info/tutorial/keyboard-events>`_
.. [2] `keyboard events - Detecting arrow key presses in JavaScript - Stack Overflow <https://stackoverflow.com/questions/5597060/detecting-arrow-key-presses-in-javascript>`_
.. [3] `JavaScript - Detecting keystrokes - QuirksMode <https://www.quirksmode.org/js/keys.html>`_
.. [4] `JavaScript Madness: Keyboard Events <http://unixpapa.com/js/key.html>`_
.. [5] `JavaScript Arrow Key Example via event.key in Keyboard Event <{filename}../../../2017/02/14/javascript-arrow-key-example-via-event-key%en.rst>`_

.. _JavaScript: https://www.google.com/search?q=JavaScript
.. _arrow keystrokes: https://www.google.com/search?q=arrow+keystrokes
.. _arrow keys: https://www.google.com/search?q=arrow+keys
.. _keyboard event: https://www.google.com/search?q=keyboard+event
.. _onkeydown: http://www.w3schools.com/jsref/event_onkeydown.asp
.. _KeyboardEvent: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent
.. _MDN: https://developer.mozilla.org/
.. _event.key: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/key
.. _event.keyCode: https://developer.mozilla.org/en-US/docs/Web/API/KeyboardEvent/keyCode
