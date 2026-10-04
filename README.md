<p align="center">
  <a href="https://www.linkedin.com/in/immkg/">LinkedIn</a> &nbsp;·&nbsp;
  <a href="mailto:mayankgupta690@gmail.com">mayankgupta690@gmail.com</a> &nbsp;·&nbsp;
  Bengaluru, India
</p>

### I build things when something feels unnecessarily difficult.

A game I couldn't join. An inbox I couldn't clean. A day that didn't fit inside a todo list.
A person I missed.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/hero.png" width="330" alt="tangled things resolving into one built thing" /></p>

Sometimes the answer is software. Usually small software. I like finding out how far a little
system can go before it needs anything expensive underneath it.

---

### 🎲 [Ludo Anywhere](https://github.com/immkg/ludo-anywhere)

My family was playing Ludo on one phone. I wanted to join.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/ludo-room.png" width="300" alt="four devices, one board" /></p>

There are plenty of good Ludo apps. None of them solved that, which was: four people, some in
the room and some not, however many devices happen to be in hand. So signing in is a *device*
login rather than a player one. One handset signs in, seats lightweight profiles like "Mom"
and "Kid 1", and a family plays from a single screen while anyone else joins from their own.

A single Node process runs Next.js and Socket.IO on one port. Room state lives in memory and
mirrors to Redis on every change, so a restart rebuilds games in progress instead of dropping
them. Deliberately not serverless, because a serverless function cannot hold a long-lived
socket. The game engine is plain framework-agnostic JavaScript, so the identical pure functions
are authoritative on the server and also run in your browser to light up which tokens have a
legal move before you tap. The board is canvas rather than SVG, because a 15×15 grid does not
need a DOM node per cell to animate. Each seat carries a token in localStorage, so refreshing
mid-game quietly reclaims your place.

Runs for about a dollar a month.

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

You can read that straight out of the schema instead of taking my word for it: `Intent`,
`Work`, `WorkDependency`, `Location`, `LocationOption`, `Plan`, `PlanStop`. The idea and the
data model are the same shape.

The [decision records](https://github.com/immkg/navo/tree/main/docs/adr) are the honest part.
The architecture doc opens by admitting it replaced four separate documents that had drifted
out of sync with each other.

`Express` · `Prisma` · `React`

---

### 🗂 Relaunch · *private*

Years of work leave a trail. Projects, decisions, technologies, things you built and forgot you
built, scattered across repositories and tickets and organisations you no longer have access to.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/relaunch-map.png" width="320" alt="scattered work becoming navigable" /></p>

Then one day you want to move, and discover you cannot actually answer simple questions about
your own career. What did I build? Where did I genuinely contribute? What am I strongest at?

Relaunch is an attempt to turn that trail into something navigable. The idea underneath it is
that you relaunch yourself by understanding the work you have already done, rather than by
writing a fresh summary of it. It's the current one, still being built.

---

### 📧 [Gmail Cleaner](https://github.com/immkg/gmail-cleaner)

Somewhere in those 50,000 emails is a tax document you actually need, so you cannot just select
all and delete.

<p align="center"><img src="https://raw.githubusercontent.com/immkg/immkg/main/art/gmail-home.png" width="300" alt="mail stays on your machine" /></p>

It syncs the account into a local SQLite database, analyses it with Pandas and scikit-learn,
and bulk deletes interactively. Entirely local, nothing leaves the machine. There is a
protected list it will never touch, and the config scrubs your personal patterns before they
reach version control, so the repo can stay synced without leaking your contacts.

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
as a constraint satisfaction problem. Constraints split into *correctness*, every lesson
scheduled once and nobody double booked, and *comfort*, preferred hours and fewer brutal runs
of back-to-back classes. A small query language compiles those to CNF and hands them to Z3.
Writing down what must be true and letting a solver find the answer beats any heuristic I would
have hand-rolled, and it is far easier to change your mind later.

That question, how far a small thing goes, is most of what I find interesting.
