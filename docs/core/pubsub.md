# PubSub

## Outline 💭

Pub/sub stands for _publish_ and _subscribe_. Pubsub is a way to listen for,
and send messages to organise and coordinate what should happen when something
occurs in your application.

* Messages are sent to a meaninfully named _channel_, and consist of an
  arbitrary _payload_ of data to give context.
* Publish (_pub_) messages to channels, to indicate when something happens.
* Subscribe (_sub_) to messages on a certain channel with a function, to
  handle when certain things happen.

## Example use 🤖

```python
import invent


def test_handler_function(msg):
    """
    To handle messages on the test_channel.
    """
    invent.datastore["answer_to_life"] = msg["meaning_of_life"]

# Subscribe the function to the "test_channel".
invent.subscribe(channel="test_channel", handler=test_handler_function)

# Publish a message to the "test_channel".
invent.publish(channel="test_channel", message={
    "name": "Some arbitrary data",
    "description": "The payload must be JSON serializable.",
    "meaning_of_life": 42,
})

# Things continue to happen...

# Eventually, you may want to unsubscribe the function from the "test_channel".
invent.unsubscribe(channel="test_channel", handler=test_handler_function)
```

## Teaching points 🗣️

Learning / understanding outcomes:

* Messages are published to a channel with a meaningful name.
* The message contains contextual data (that can be converted to JSON).
* Subscribe to a channel with a function to handle incoming messages on that
  specific channel. When a message is sent to the channel, the function is
  called with the message (see functions).

Imagine that pubsub is like a sort of Whatsapp, but for code.

In Whatsapp you join particular _groups_. Joining a group on Whatsapp is the
same as subscribing to a channel in pubsub, and the result is similar too.
Everyone who is a member of a Whatsapp group gets all the messages sent via
that group. Similarly, every function subscribed to a channel is run each time
a message is sent to the channel. If you want to say something to everyone in
the Whatsapp group, you just send a message to the group. Similarly, if a
piece of code requires all the functions subscribed to a certain channel to
react when something important has happened, it publishes a message describing
that important something to the channel. Just as in Whatsapp, it's possible to
unsubscribe functions from a channel.

That's really all there is to it!

In the same way it's possible to coordinate a group of friends or an
organisation by sending messages via WhatsApp groups, it's possible to
coordinate and organise how an application works by having code publish
messages, while other pieces of code (functions) react to them.

## Unplugged activity 🔌

This unplugged activity highlights how messages are sent to channels, and
functions are subscribed to channels.

This is a variation of the "Simon Says" game.

Within your class of learners, each participant is "subscribed" to a channel
signifying the colour of an item of clothing they're wearing or an object
they're carrying. For example, the colour of their top, or colour of their bag.

At the start of the game, each player has the same "function" to follow when
they receive a message:

* Follow the instructions in the message.

As teacher, you'll send messages to different channels using this very specific
recipe:

* You say the name of the desired colour / channel (e.g. "red", "blue",
  "green").
* Then you say the message (e.g. "stand on one leg", "touch your nose", "sit
  down").

If a learner gets things wrong, they're "out", with last one standing the
winner.

Mix things up! Why not..?

* Use colours that don't reflect your learners.
* Don't follow the message sending recipe.
* Send a message that causes the folks in one channel to send a message to
  another channel.

For example, with the message, "blue: send a message to red to stand on one
leg", the blue learners need to follow the message sending recipe correctly,
and the red learners can't do anything until that message has been sent.

Further refine the game by handing out custom "functions" to learners to follow
should they get a message on their channel. Such functions should reflect the
physical learning situation, such as:

* Only follow instructions in the message if the window is open.
* Resend any message you get to the "blue" channel.
* Write down the message, but don't follow it.
* Always follow the instructions in the message twice.
* Clap your hands, follow the instructions in the message, then stamp your
  feet.

Invent more "functions" of your own!
