# Media

## Outline 💭

When we talk about "media" we mean the digital assets used within the app. They
may include (but are not limited to):

* Images (e.g. JPEG, PNG and GIF files).
* Sounds (e.g. MP3, WAV and other audio formats).
* Videos (e.g. MPEG4, MOV and WEBM files).
* Text (e.g. TXT files, or stored in structured data like CSV).
* Data (JSON, CSV, TOML, XML and other structured data formats).

Media assets need related "widgets" that understand how to work with them and
make them available to the user. For example, if you have a video asset, you'll
need a video player widget in the user interface to display it to the user.

Media assets are stored in a `media` directory. In the `media` directory are
further sub-directories for each type of media: `images`, `sounds`, `videos`,
`text` and `data`.

The framework understands how to refer to your media assets so you can use them
in your code.

For example, if you had a `kitten.jpg` file in the `images` sub directory of
the `media` directory, then you could refer to it in your code as:

```python
my_kitten_pic = invent.media.images.kitten.jpg
```

The resulting `my_kitten_pic` object is a representation of the image as a
`MediaSource` (a `MediaSource` understands such things as the sort of media to
which it refers, and where to find the media).

## Example use 🤖

A video widget with the id `my_video_widget` set to play a video called
`my_video.webm`:

```python
"""
Assuming my_video.webm is in the project's "videos" media directory.
"""
import invent


def play_video(msg):
    # Find the video widget by its id.
    player = invent.widgets.find("#my_video_widget")
    # Set the video source of the widget to "my_video.webm".
    player.source = invent.media.videos.my_video.webm
    # Get the widget to play the video.
    player.play()
```

Audio can be played in the background if necessary.

```python
"""
Assuming a honk.mp3 file is in the project's "sounds" media directory.
"""
import invent


def on_honk(msg):
    """
    Called when the car-horn button is pressed.
    """
    invent.play(invent.media.sounds.honk.mp3)
```

## Teaching points 🗣️

Learning / understanding outcomes:

* Media are the raw digital assets used by the application.
* Examples of media include images, sounds, videos, text and raw data.
* Such media require related "widgets" in order to make them available to the
  user.
* The media defines what something is, the widget brings the media into the
  world of the user via the app.

A useful way to think of the distinction between media and widgets is to
consider the difference between a painting (the media - the paint and pigments
of, say, the Mona Lisa) and the frame, art gallery or poster in which it is
displayed (the widget). Similarly, there's the song "Frere Jaques" (the media -
a series of notes and words) but it still needs to be performed in some way
(the widget), by a choir or on the radio. Finally, a TV programme (the media)
may be transmitted over the airwaves, but you still need a TV set to watch it
(the widget).

## Unplugged activity 🔌

This unplugged activity helps identify ways in which different types of media
are used by applications.

Open several popular web pages or apps. Ask learners to identify different
sorts of media and how they are used.

Examples may include:

* An image of a logo. Click it and you return "home".
* An animated spinner to indicate something is taking time.
* Sounds or music played to indicate certain events or activities.
* Textual content (that may have alternative translations depending on the
  human language selected).
* Informational data presented in some way (how is the story in the data
  presented?).

For each example ask them to identify three things:

* The type of media (image, sound, video, text, data etc...)
* Its purpose (informational, an alert, creating a mood etc...) and how the
  media achieves this purpose.
* The context of the media (how this sits within the larger functionality of
  the app).

By looking at examples from different web pages or apps, can learners identify
common patterns of media use (for example, the use of colour to indicate
status: success, warning, error etc...)?

Finally, ask learners to design their own media to use as part of an activity
in an app of their choice. Examples may include:

* Icons to click that represent common activities in their app (for example,
  what image could you click to show you like some content, how might you
  visually display the review ratings for a product, etc...).
* Sound effects to play at certain events: success, warning, error.
* Textual instructions for a login page, shopping cart or profile creation
  page.
* Images to place onto a map indicating the location of various types of
  location (hospital, police station, sports arena, garage, cinema etc...)
* A collection of animations to indicate certain activities are waiting to
  complete: logging in, paying for something, booking a cinema ticket,
  calculating a route for a journey.
* Displaying quantitative information over time: temperature, rainfall or
  sunshine over a year for a particular location, average journey time between
  two locations depending on time of day, how busy a restaurant usually is at
  certain times.
