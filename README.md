MagicGesture.js
===============

A simple gesture event generator for those multi touch devices that do not support them natively.

Usage:
======

In your page add the following lines before the end of the head tag:

<pre>
    MagicGesture.init();
</pre>

Then somewhere in the body add:

<pre>
document.addEventListener("gesturestart", gestureStart, false);
document.addEventListener("gesturechange", gestureChange, false);
document.addEventListener("gestureend", gestureEnd, false);

function gestureStart(e) {
    e.preventDefault();
};

function gestureChange(e){
    e.preventDefault();

    e.target.style.webkitTransform =
        'scale(' + e.scale  + ') rotate(' + e.rotation + 'deg)';
};

function gestureEnd(e){
    e.preventDefault();
};
</pre>

More information on multi-touch gestures is available here: http://developer.apple.com/library/iOS/#documentation/AppleApplications/Reference/SafariWebContent/HandlingEvents/HandlingEvents.html

You can hook gestures to other elements rather than DOM elements by passing the appropriate callbacks to the init() method. This allows you to manipulate for example, elements in a canvas. For an example see http://photoviewer.pierotoffanin.com

