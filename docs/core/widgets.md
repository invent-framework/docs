# Widgets

## Outline 💭

Widgets are elements of a user interface.

The user interface defines how people interact with an application, and how
the application interacts with people.

Common widgets used to make up a user interface include (but are not limited
to):

* Activity indicators - an animation showing activity of indeterminate length,
  usually some sort of "spinner".
* Audio players - play sound files. These may be visible to the user in the
  form of playback buttons and a progress bar, or may be invisible if playing
  ambient sounds.
* Buttons - something to press or click to cause some sort of action in the
  application. Buttons may contain a text label (to indicate what it does) or
  an image (an icon that represents what it does). They may also be disabled
  (i.e. visible, but not functioning).
* Canvases - an area of the user interface in which one dynamically draws.
  This is often used as a way to display graphs, charts and other interactive
  graphical elements.
* Dividers - separators used to visually distinguish different sections of
  content in the user interface. These usually take the form of lines of a
  certain thickness and colour.
* Email inputs - for typing in valid email addresses. This is usually a text
  input that only allows the entry of valid email addresses.
* Images - contain pictures to display as part of the user interface. Images
  can be contained in other widgets, like buttons.
* Labels - short explanatory / contextual text for annotating other widgets
  (such as the text of a button, or labels for input widgets).
* Maps - display tile based data. They centre on a location and may have
  markers, routes or areas highlighted. Maps may also be draggable and
  zoomable.
* Multi-line text inputs - for entering large amounts of text.
* Multiple choice selectors - for selecting any items from a list of options.
  Options are toggled as selected / deselected with a press or a click. More
  options may be available via the use of a scroll bar.
* Number inputs - for typing in numeric input. This is usually a text input
  that only allows the entry of valid numeric values.
* Password inputs - for typing in passwords (without revealing the password on
  the user interface). These are text inputs whose value is hidden by place
  holders for the actual text (such as "`*`").
* Progress bars - for indicating the progress of a task of known length. As a
  task progresses events are fired that cause the progress bar to grow.
* Scroll bars - for moving around content on the UI that is too big to display
  in the available space. Scroll bars are usually at the edge of a scrollable
  area and move both horizontally and vertically.
* Selectors - for choosing a single item from a list of options. Items are
  selected / de-selected with a press or a click. If a different item is
  already selected, it is automatically de-selected in favour of the newly
  selected item.
* Sliders - for selecting a value within a range. The range is usually shown
  as a horizontal or vertical line, with the selected value as a draggable
  marker.
* Switches - an indicator with two possible states: True (on, checked);
  and False (off, unchecked). They are toggled via a click or press.
* Tables - layed out with rows and columns, are used for displaying tabular
  data.
* Text inputs - a single line box for typing in short amounts of text.
* Trees - for displaying data organised as hierarchical (tree like) items.
  Trees may allow themselves to be expanded or contracted by toggling parent
  items, to show or hide their child items.
* Video players - for rendering video files to the user interface. These will
  usually include playback control buttons and a progress bar.

Some of the widgets are presentational - they display or make available certain
sorts of media or data. Other widgets are interactive - the user affects change
in the application via gestures, clicks and other activities.

Widgets subscribe to messages and automatically update their media and data
when such messages are published.

Widgets are organised into containers. Containers may contain other containers.
As a result, widgets and containers will always have a parent container. A
container's widgets and containers are called its children.

Containers define the formation and layout to use to show their child widgets
and containers to the user.

Such arrangements, that stress how things appear in relation to each other,
ensure the software is able to compute the precise layout of the user interface
given different types of device (mobile, tablet or desktop) and orientations
(portrait or landscape).

There are several different types of container:

* Box - a generic container for widgets or containers.
* Tab box - a container of containers that allows the user to select which
  child container is displayed depending on a tab control.
* Split box - a container of containers between which a moveable split is
  shown so the user can change the relative sizes of the child containers.
* Scroll box - a container, with a specified height or width, that may contain
  content larger than the available display size. Vertical and horizontal
  scroll bars my be used to make visible different areas of the content in the
  available display area.

All containers are oriented in one of two ways:

* Vertical - that displays its children vertically one after the other.
* Horizontal - displays its children horizontally side by side of each other.

All containers also have a direction associated with vertical or horizontal
orientations.

* Vertical - starting either from the top to the bottom or other other way up,
  from the bottom to the top. Default: top to bottom.
* Horizontal - starting from either the left to the right, or the other way
  around, from the right to the left. Default: left to right.

Containers are drawn onto cards. A card is an individual screen in an app.

## Example use 🤖

The following code creates a form for entering a postal address, containing
several containers and widgets. The textual description of the form can be
updated via messages to the "address_instructions" channel, because the widget
that represents the instructions subscribes to this channel.

```python
import invent
from invent.ui.widgets import Label, TextInput
from invent.ui.containers import Box, VERTICAL, HORIZONTAL


# Create a parent box to hold the rest of the form.
address_form = Box(VERTICAL)

# Create some instructions to put at the top.
instructions = Label("Please fill in your address.")
# Because the instructions could change (e.g. if the address is invalid and the
# user needs to know they should correct it), then subscribe the textual
# content of the instructions to the "address_instructions" channel.
invent.subscribe("address_instructions", instructions.text)

# Each of the entries in the address is a label, a textual input and a
# horizontal box to contain them.
name_label = Label("Name:")
name_input = TextInput()
name_container = Box(
    HORIZONTAL, children=[name_label, name_input, ]
)

number_street_label = Label("House number / street:")
number_street_input = TextInput()
number_street_container = Box(
    HORIZONTAL, children=[number_street_label, number_street_input, ]
)

town_label = Label("Town:")
town_input = TextInput()
town_container = Box(
    HORIZONTAL, children=[town_label, town_input, ]
)


postcode_label = Label("Postcode/Zip:")
postcode_input = TextInput()
postcode_container = Box(
    HORIZONTAL, children=[postcode_label, postcode_input, ]
)

# Add all the parts of the address form into the address container.
address_form.children = [
    instructions,
    name_container,
    number_street_container,
    town_container,
    postcode_container,
]
```

## Teaching points 🗣️

Learning / understanding outcomes:

* Widgets are common UI elements like buttons, dropdowns, image viewers, video 
  players...
* Widget attributes may subscribe to messages so they auto-update.
* Containers contain widgets and other containers as their "children". They
  define the widget's formation and layout.

Widgets are to the user interface of an application, as knobs, switches and
indicator lights are to, say, a kitchen appliance. They are a way to transmit
information from the application to the user (by displaying media and data) or
from the user to the application by manipulating or interacting with widgets.

Since widgets are instantiated in some way (for example, they're drawn on the
screen, or they're playing sounds), a great deal of thought and talent can be
invested in how people and applications interact. This field of computing is
called Human Computer Interaction (HCI) and encompasses design, psychology,
learning, cultural studies, linguistics, security, sociological research and
deeply technical work. Many disciplines outside the field of computing can be
brought to bear through HCI. For instance, one of the foundational texts in
HCI discusses how the user interfaces of applications are a form of theatre,
and many musicians spend time composing fragmentary pieces, that often last
less than a second, but which are used to indicate something has happend (such
as an alert for a new email).

Most importantly, when designing a user interface by assembling widgets and
containers it is important to do so with empathy, compassion and collaborative
communication... you need to know your user interface is engaging, fulfils its
purpose and relates to the people you imagine will use it. That's why it's
essential to place human beings, their culture and social interactions at the
heart of such work.

## Unplugged activities 🔌

These two unplugged activities help secure the notion of "widgets" and model
the way containers form and layout widgets in the user interface.

### The widget cafe ☕

Task - identify "widgets" in a real kitchen of a cafe.

### Team formation ⚽

Layout of your team on the pitch (like widgets).
