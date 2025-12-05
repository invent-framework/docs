# Design

The _Invent_ framework has a certain design outlook, way of paying attention to
our users and programming philosophy. This page explains and illustrates these
things.

The summary is...

## _Invent_ is for beginners

Who are beginners?

You're a beginner if creating typical UI based applications isn't your usual
focus.

The _Invent_ framework aims to be easy to learn, so you can get on with the fun
of creating interesting things. With a little experience, you'll quickly build
all sorts of valuable stuff. _Invent_ does the technical heavy lifting so you
can focus on with the important things.

If you're asking questions about technical features of _Invent_, such
as, "why does _Invent_ use the JavaScript `Audio` class like _this_ rather than
like _that_?", then you're probably not a beginner. However, we invite
you to contribute to PyperCard if you spot ways to _enhance the experience of
beginners_.

!!! tip

    If you just want some deeply technical capability that _Invent_ doesn't
    provide, you should probably try another framework that supports that
    capability rather than try to force it into _Invent_.

## What _Invent_ is

* **Simple** - _Invent_ doesn't need a lot to _make stuff happen_.
* **Expressive** - you can do _lots of different stuff_ with _Invent_.
* **Empowering** - _Invent_ helps _assemble stuff_ so you get _what you want_.
* **Teachable** - it's easy to _explain and learn stuff_ with _Invent_.
* **Fun** - it _feels good to make stuff_ with _Invent_.

## What _Invent_ is NOT

* **Comprehensive** - rather, we try to implement _most_ of the features,
  _most_ beginners want, _most_ of the time.
* **Fast** - rather, we prefer to use Python because it is an _easy-to-learn
  and widely used_ programming language.
* **Flexible** - rather, we expect our core _pragmatic programming paradigms_
  to be _good enough most of the time_.
* **Opaque** - rather, you don't need to be a programmer with a degree in
  computer science to _get started and building stuff in only minutes_.
* **Hard** - rather, we concede that some stuff is deeply challenging and you
  should _use something else if Invent doesn't work for you_.

## Personas

To help orientate folks contributing to _Invent_, we've created a small group
of personas to illustrate the diversity of "beginner" coders we hope to help
with our project. These personas help us empathise with folks creating things
with _Invent_. They all have names, backgrounds, and certain needs, but they
also deliberately embody an archetype (learner, educator, enthusiast etc...).

In addition to a name, cultural context and associated archetype, each persona
has four sections:

1. an introduction that explains who they are,
2. a description of how they're creating with the _Invent_ framework,
3. any mitigating circumstances about their engagement with _Invent_, and,
4. a list of _Invent_related features/capabilities they need.

The persona images were made via a stable diffusion based tool for generating
faces. _These people do not actually exist_!


### Alejando 🇲🇽(Learner)
![](/assets/img/persona_alejandro.png)

Alejandro is 12 years old, lives in Mexico and is learning how to code in his
after school computer club. He is also colour blind, so the colour pallette for
user interfaces sometimes poses a challenge for him.

His teacher, Miss.Perez, has asked him to create a simple game with _Invent_ 
in a choose-your-own-adventure style. Alejando is only too pleased with this
project since he has lots of story ideas based in the Star Wars / Marvel
universes.

Alejandro doesn't speak English, but Miss.Perez has created resources in
Spanish, based on the _Invent_ documentation and tutorials. He builds and
hosts his projects on [PyScript.com](https://pyscript.com/).

Alejando needs:

* A Spanish language version of PyScript.com.
* The availability of auto-didactic resources such as:
  - Beginner friendly example projects.
  - Tutorials.
  - A simple development environment that supports learning.
* Support for light, dark, high-contrast and custom themes in the UI layer.

### Ash 🇬🇧(Engineer)
![](/assets/img/persona_ash.png)

Ash, 29, works as a back-end Python engineer at a hedge fund in the City of
London. They are part of a team responsible for ensuring the right information
and alerts get to the right colleagues as market conditions change throughout
the day. Most of their Python work is related to data science and the Python
tooling needed to create the bespoke and commercially sensitive information
used by their colleagues.

They often need to direct non-technical colleagues to specialist sources of
information, and to this end Ash has used _Invent_ to create a simple wizard
like app to signpost and track the usage of internal services, depending on
user role and need. Ash hopes to follow this up with another _Invent_ app that
allows traders to read financial alerts consumed from an internally developed
news API.

Ash, as an experienced developer who is already familiar with Python, was drawn
to the ease with which UI driven apps could be created by folks with little or
no frontend experience. They were up and running within an hour, after reading
the cheatsheet and skimming the relevant sections of the tutorials.
It took just three days for them to produce the
wizard app for internal colleagues, and they presented their work to the wider
engineering teams in the company, as part of a lunchtime technical "brown bag"
session. They also suggested a couple of documentation changes as PRs to the
_Invent_ repository and have been active on the project
[discord channel](https://discord.gg/TKyjvSynTP). They intend to suggest
_Invent's_ use in an upcoming London Python Code Dojo community meetup.

What Ash needs:

* A technical cheat sheet for getting experienced developers up and running.
* A simple and intuitive (yet powerful) means of making network calls via both
  HTTP and web-socket protocols.

### Mandisa 🇿🇦(Educator)
![](/assets/img/persona_mandisa.png)

Mandisa, 35, is a high school teacher in a girl's school in Claremont, Cape
Town, South Africa. She is a subject matter specialist for computing and is
responsible for developing and delivering the programming curriculum for
students aged between 11-16.

She first heard of _Invent_ from a tutorial given at PyCon Africa in
Ghana, and has remained in touch with the mentor who ran the tutorial. She
understands the basics of Python but is often only a little bit more advanced
in her understanding than her most advanced 16 year old students. She enjoys
the fact that she can use _Invent_ to create interactive presentations for her
students, doesn't need to persuade her school sysadmin to install anything (it
all works in the browser), and her students can easily take her example apps
as starting points for their own _Invent_ projects.

She hopes to contribute an _Invent_ talk at next year's education summit at
PyCon South Africa and all her learning resources, released under
[Creative Commons](https://creativecommons.org/) or
[Open Source](https://opensource.org/) licenses, can be found online via her
school's website and her [PyScript.com](https://pyscript.com/) account.

What Mandisa needs:

* Good mobile performance so her students can run their work on their personal
  computing devices (MicroPython).
* Teacher friendly learning resources that can be freely adapted / adopted in
  the classroom.
* A classroom friendly configuration of pyscript.com (where teacher has admin
  control over student's workspaces / applications).

### Parminder 🇮🇳(Informatician)
![](/assets/img/persona_parminder.png)

Parminder, 44, is a research scientist attached to the United Nations. Her
focus is the measurement and impact of long term environment change on
glaciers. She is also partially sighted, and often uses a screen reader and/or
magnification features while working across all her computing platforms
(Android mobile, Apple iPad and a Windows "work" Lenovo laptop).

She uses _Invent_ to design data collection apps for both her scientific
colleagues and non-specialists in the field. These apps are often used in
relatively disconnected areas with only patchy 3G internet coverage, or
faster Starlink (satellite) based wifi at base-camps.

What Parminer needs:

* Responsive: same app works on both mobile and laptop.
* Offline storage.
* Robust error handling for network based tasks.

### Janet 🇨🇦(Administrator)
![](/assets/img/persona_janet.png)

Janet, 52, is COO at an established and flourishing aeronautical engineering
company. Based in Vancouver, the company has several thousand employees in
offices in Canada, the US, UK, France and Italy. Much of her work depends on
her ability to learn and then communicate key facts in a timely manner. Janet,
as someone with a strong engineering background, has picked up a basic
understanding of Python.

She uses _Invent_ to create a set of pages containing live data for the
purposes of sharing key insights with her colleagues. She likes to think of her
_Invent_ apps as interactive dashboards quickly created for other C-level
executives in the company, and her reports who use it to monitor key status
indicators relating to all sorts of factors including financial, logistical,
manufacturing and sales based data.

She especially appreciates how _Invent_ works with real-time data and behaves
like a multi-path presentation tool, depending upon what key insights the user
wants to learn. She also appreciates how easy it is to update the _Invent_
app, as business needs change, and the app just updates to the latest version
when refreshed ~ making the deployment story very easy, cross platform
(including mobile) and requiring little or no technical knowledge.

What Janet needs:

* Visual UI designer with access to code behind.
* A simple and intuitive (yet powerful) means of making network calls via both
  HTTP and web-socket protocols.
* Examples of pages to display common data patterns.

### Hasan 🇹🇷(Hobbyist)
![](/assets/img/persona_hasan.png)

Hasan, 67, is an amateur tech enthusiast and restaurant owner from Selçuk,
Turkey. The historic ruins of the ancient city of Ephesus are only a few miles
away.

Never shy of embracing technology, he's decided to write a multi-lingual
_Invent_ app that acts as the menu for tourists at his restaurant. He aims to
support Turkish, English, Arabic, Hebrew, French, German, Italian and Spanish
versions of his menu. He's famous among his friends for experimenting with new
technology. For instance, he's been using spreadsheets for managing stock and
accounting since Windows 3.1 and recently embraced a take-away food delivery
app to increase the reach of his restaurant (the inspiration and template for
his own menu app).

He started to learn Python as a personal project during the COVID
pandemic (his daughter-in-law is a Python programmer in Istanbul, and suggested
he look at _Invent_). Because of the tourist trade, he has relatively good
English and is working his way through the _Invent_ tutorials while sketching
out his ideas for the menu app for his restuarant. He likes using Python,
appreciates that _Invent_ works on all his customer's devices (thanks to
MicroPython), and is pleased his rusty HTML skills can be used for generating
the user interface.

What Hasan needs:

* Internationalization support.
* Ability to hand-craft HTML based cards.
