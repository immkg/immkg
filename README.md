<p align="center">
  <a href="https://www.linkedin.com/in/immkg/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="mailto:mayankgupta690@gmail.com">mayankgupta690@gmail.com</a> &nbsp;·&nbsp;
  Bengaluru, India
</p>

# Mayank Kumar Gupta

*Almost everything here started as something I personally needed.*

I don't usually start with a technology. I start with a thing that is mildly broken in my own
life, sit with the irritation slightly too long, and then build something.

A game I couldn't join. An inbox I couldn't clean. A day that didn't fit inside a todo list.
A person I missed.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/hero.png" width="330" alt="tangled things resolving into one built thing" /></p>

Sometimes the answer is software. Usually small software. I like finding out how far a little
system can go before it needs anything expensive underneath it.

---

### 🎲 [Ludo Anywhere](https://github.com/immkg/ludo-anywhere)

My family was playing Ludo on one phone. I wanted to join.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/ludo-room.png" width="300" alt="four devices, one board" /></p>

So I built a room where the game doesn't care how many devices are around it. Signing in is a
*device* login rather than a player one: one handset seats "Mom" and "Kid 1", and anyone else
joins from their own screen.

One process. Realtime rooms held in memory, mirrored to Redis so a restart doesn't drop a game.
About a dollar a month.

`Next.js` · `Socket.IO` · `Canvas` · `Redis` · [myludo.life](https://www.myludo.life)

---

### 🗺 [Navo](https://github.com/immkg/navo)

A todo list asks *what*. Real life starts with *I need to get this done*, somewhere, at some
point, probably on the way back from something else.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/navo-route.png" width="320" alt="an intention becoming a route" /></p>

Navo starts from the intention and discovers the work as the intention gets clearer. Locations
are first-class entities rather than tags, routes connect them, and the route through your day
decides what is actually possible. Opportunities surface when location, time and available work
line up.

The idea and the data model are the same shape, which you can read straight out of the schema.
The [decision records](https://github.com/immkg/navo/tree/main/docs/adr) are the honest part.

`Express` · `Prisma` · `React`

---

### 🗂 Relaunch · *private*

Years of work leave a trail. Projects, decisions, technologies, things you built and forgot you
built.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/relaunch-map.png" width="320" alt="scattered work becoming navigable" /></p>

Then you want to move, and find you can't answer simple questions about your own career.

Relaunch is my attempt to make that trail navigable. You relaunch yourself by understanding the
work you have already done, not by writing a fresh summary of it.

*Private, still being built.*

---

### 📧 [Gmail Cleaner](https://github.com/immkg/gmail-cleaner)

Somewhere in those 50,000 emails is a tax document you actually need, so you cannot just select
all and delete.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/gmail-home.png" width="300" alt="mail stays on your machine" /></p>

It syncs the whole account into local SQLite and lets you cut from there. Nothing leaves the
machine, and there's a protected list it will never touch.

`Python` · `SQLite` · `scikit-learn`

---

### 💝 [Bubu](https://github.com/immkg/buubuu)

She was working remotely and I missed her. I could have bought a Valentine's gift. I built one
instead.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/buubuu/main/screenshots/day1.png" width="320" alt="Bubu, day one" /></p>

Eight days, Rose Day through Valentine's, each its own screen, with the words kept in a data
file rather than baked into each one so the structure and the sentiment stayed separable. A
heart-shaped cursor, and a No button that behaves exactly as you would expect a No button to
behave. Static build, no backend. It did not need to scale.

Not everything has to serve a billion people. Some of it just has to make one person smile.

---

### How far can a small thing go?

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/small-system.png" width="300" alt="a small system going a long way" /></p>

[Clarity Classes](https://github.com/immkg/clarity-classes) is free, open-source CBSE learning
for classes 7 to 12, running on a static site, unlisted video embeds and a free database tier.
A working learning platform with essentially nothing to pay for or keep alive.

[General Scheduler](https://github.com/immkg/general-scheduler) treats university timetabling
as a constraint problem, split into *correctness* (nobody double booked) and *comfort*
(preferred hours, no brutal runs of back-to-back classes), and hands it to Z3. Writing down what
must be true beats any heuristic I would have hand-rolled, and it's far easier to change your
mind later.

That question, how far a small thing goes, is most of what I find interesting.
