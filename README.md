Eventbeacon specification
========================

Eventbeacon is a specification for publish-subscribe mechanisms put into a concise and united API. For reference, an event beacon compatible interface is referred to as a beacon.

General
-------
* A beacon can hold any number of events (`[0..n]`)
* An event is an object which can store any kind of data 

Event definition
----------------
An event has the following fields:
* Timestamp
* Sender (The reference to the beacon where it has been triggered from)
* Data

Storing events
--------------
* A beacon needs to have a method to register an event. This should be called `.on()`. If `on` is not available due to it being a reserved word, the method should be called `addListener`.
 * It takes two parameters:
  * The name of an event
  * A reference to a function. As its parameter it returns an event instance
 * When a beacon triggers the event, the function reference will be executed
* A beacon needs to have a method to unregister an event. This should be called `.off()`. If `off` is not available or `on` is not available, the method should be called `removeListener`. (The latter to preserve consistency.)
 * It takes one parameter:
  * The name of an event
 * It removes all events of the entered name

Calling events
--------------
* A beacon needs to have a method to call an event. This should be called `trigger`.
* The method `trigger` has exactly two parameters:
  * The name of the event
  * An Event instance (Optional)
* If possible, the `trigger` method can be overloaded with this signature:
  * The name of the event
  * The event data
