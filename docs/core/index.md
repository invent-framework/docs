# Core concepts 

A single page explainer of the _core concepts_, what they are, and how they
relate.

## [Functions](functions.md)

Code containing custom behaviour.

* Just Python functions with a single message argument.
* Store and change the state of things via the datastore.
* Signal events and activity by publishing messages.

## [PubSub](pubsub.md)

Listen for / emit in-app messages.

* Messages have a meaningfully named _channel_, and arbitrary _payload_.
* Publish (_pub_) messages to channels, to indicate when something happens.
* Subscribe (_sub_) to messages on a certain channel with a function, to
  handle when certain things happen.

## [Media](media.md)

Digital assets used within the app.

* Raw images, sounds, videos, text and data.

## [Widgets](widgets.md)

User interface elements or media handlers.

* Widgets are common UI elements like buttons, dropdowns, image viewers, video
  players...
* Widget attributes may subscribe to messages so they auto-update.
* Containers define the widget's formation and layout.
* Based on BeeWare's Toga framework.

## [Cards](cards.md)

Show things to the user.

* Cards display / layout widgets.
* User interactions with widgets in cards emit messages - e.g. "clicked".

## [Transitions](transitions.md)

Move between cards.

* Transitions usually have a single source card and destination card.
* Some transitions define multiple source cards and a single destination card.
* Transitions may also have a user defined function associated with them.

## [DataStore](datastore.md)

Keeps state, stores data.

* A very simple key/value store.
* When the datastore is changed, it emits a message to say what has changed.
* May include search capabilities.
* May have a backend that syncs with remote storage.

## [Tasks](tasks.md)

Do things until an outcome / result is achieved (e.g. a network request).

* Blocking tasks display a "waiting" card, in which you can cancel the task.
  When finished either transition to a success card or transition to an error
  card.
* Background tasks, when the outcome is known, either emit a message or update
  the datastore.
* Common tasks already built into the framework (get geo-location, call a
  remote API, interact with a web-socket, handle a long running user defined
  function).

## [Application](application.md)

Contains all the above.

* An application addresses / works within a specific domain.
* Has a name, icon and optional splash screen (displayed when starting up).
* Delivered via the web, or as a cross-platform package via BeeWare's
  Briefcase project.
