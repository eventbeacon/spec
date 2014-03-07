Lightsheet specification
========================

Lightsheet is a specification for publish-subscribe mechanisms put into a concise and united API. For reference, a lightsheet compatible interface is referred to as a lightsheet.

General
-------
* A lightsheet can hold any number of events (`[0..n]`)
* An event can store any kind of data (`[0..n]`)

Storing events
--------------
* A lightsheet needs to have a method to register an event. This should be called `.on()`. If `on` is not available due to it being a reserved word, the method should be called `addListener`.
* A lightsheet needs to have a method to unregister an event. This should be called `.off()`. If `off` is not available or `on` is not available, the method should be called `removeListener`. (The latter to preserve consistency.)


Calling events
--------------
* A lightsheet needs to have a method to call an event. This should be called `trigger`.
* If the programming language allows a to add methods to instances at run-time, it should provide a shorthand function for calling events. (`.trigger('myEvent')` would be `.myEvent()` and `.trigger('myEvent', 5, 6)` would be `.myEvent(5, 6)`)
