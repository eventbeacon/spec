Eventbeacon specification
========================

Eventbeacon is a specification for publish-subscribe mechanisms put into a concise and united API. For reference, an event beacon compatible interface is referred to as a beacon.

General
-------
* A beacon can hold any number of events (`[0..n]`)
* An event can store any kind of data (`[0..n]`)

Storing events
--------------
* A beacon needs to have a method to register an event. This should be called `.on()`. If `on` is not available due to it being a reserved word, the method should be called `addListener`.
* A beacon needs to have a method to unregister an event. This should be called `.off()`. If `off` is not available or `on` is not available, the method should be called `removeListener`. (The latter to preserve consistency.)


Calling events
--------------
* A beacon needs to have a method to call an event. This should be called `trigger`.
* The method `trigger` has exactly two parameters:
  * The name of the event
  * The data of the event (Optional)
