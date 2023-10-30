# Functions

## Outline 💭

Functions contain code to implement custom behaviour when something happens
(represented by a message). They define the unique aspects and behaviours of
how the application interacts within the world.

Functions are:

* Just Python functions with a single message argument.
* Store and change the state of things via the datastore.
* Signal events and activity by publishing messages.

## Example use 🤖

```python
import invent


def my_handler_function(msg):
    """
    A function to handle messages. It does two things:

    1. Store a value from the message in the app's datastore.
    2. Publishes a new message to the "log_my_message" channel.
    """
    invent.datastore["answer_to_life"] = msg["meaning_of_life"]
    invent.publish("log_my_message", msg)

# Subscribe the function to the "test_channel".
invent.subscribe(channel="test_channel", my_handler_function)

# When this message is published, the function will run.
invent.publish(channel="test_channel", message={
    "meaning_of_life": 42,
})
```

## Teaching points 🗣️

Learning / understanding outcomes:

* Functions receive _arguments_ (sometimes called parameters) - data needed for
  the function to work. In our case, there is a single argument representing
  the message that caused the function to run.
* The code written inside such functions describes the behaviour needed to
  react to the message that caused it to run. Such code has access to the
  message itself, the application's global datastore and an API cook-book of
  built in utilities to achieve common and useful ends.
* The function can modify things in two ways: by storing or updating data in
  the application's global datastore, or by publishing a message to indicate
  some valuable thing has happened.

There are literally thousands of tutorials online describing Python functions.
Remember, functions that handle messages in this framework take a single
argument and can only change things in two ways (by creating, updating or
retrieving values from the datastore, or by publishing further messages). These
limitations are imposed for the sake of simplicity, ease of understandability
and teachability.

Functions are named blocks of code, so the name you give to a function is
important because it conveys something meaningful about what it does.
Furthermore, you should add documentation to your function so folks can read,
in plain English, about the its purpose and behaviour (see the example use
section, above).

Functions represent a specific set of instructions to achieve something, and
can be themselves made up of further calls to other functions. Such
instructions are called algorithms and a common metaphor is to compare them to
recipes for preparing dishes of food.

To continue the metaphor, if a function is like a recipe for a dish on the menu
of a restaurant, then when a customer orders that specific dish from the
menu, a message (in the form of an order) arrives in the kitchen from the
waiter. The chef follows the instructions in the recipe to create the dish
in response to the order. When the dish is ready, the food is stored on a
dispatch table from where a waiter will take it to the customer, and the chef
rings a bell to send a message to the waiters that there is food waiting to
be delivered to the customer.

## Unplugged activity 🔌

This unplugged activity highlights how functions react to messages.

You're going to call the register with your class of learners.

Each learner has to follow the same function:

* Identify the name in the message.
* If the name is yours, create a new message by saying "Here!"

Explain that you, the teacher, represent the "application" and that you send
messages by speaking out loud to the classroom. Each message is simply a name.

The algorithm you're using is:

* For each learner in the class...
  * Send a message containing the learner's name.
  * If you immediately get a "Here!" response, mark the learner as present in
    the register.

You may also elaborate that your function was run because you received a
"take the register" message from the school administrator, and the message
contained the register of learners used to store store the attendance. In this
way many different functions are coordinated together via a series of messages
to which specific functions react.
