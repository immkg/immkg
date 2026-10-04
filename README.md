<h1 align="center">Mayank Kumar Gupta</h1>

<p align="center">
  <em>Almost everything here started as something I personally needed.</em>
</p>

---

I don't usually start with a technology. I start with a thing that is mildly broken in my own
life, sit with the irritation slightly too long, and then build something.

The pattern is consistent enough that I stopped pretending it was a coincidence. My family
was playing a board game and I couldn't join. My inbox had thirty thousand emails hiding one
that mattered. My fiancée was working remotely at Valentine's. Every planner I tried wanted
me to think in lists when my actual day is a route between places.

The other half of it: I like getting a surprising amount out of very little. A static site,
one process, a local database. Most of what I build is designed to stay cheap and stay up.

<br />

## 🗂 Relaunch

*Private repository*

You spend years building things, and the record of it scatters. Across repositories,
across tickets, across organisations you no longer have access to, across your own memory.

Then one day you want to move, and you discover you can't actually answer simple questions
about your own work. What did I build? Where did I genuinely contribute? What am I strongest
at? Which of this matters for the thing in front of me now?

Relaunch is an attempt to build a catalogue of professional work: what was built, where the
contribution was, which technologies were involved, what problem it solved, how the pieces
connect. The idea underneath it is that you relaunch yourself by understanding the work you
have already done, not by writing a new summary of it.

It's private, so this is the shape rather than the internals: a local-first data store
scoped per person, an API with validation on every write path (learned the hard way), and a
set of collectors that pull from the places work actually lives.

<br />

## 🎲 [Ludo Anywhere](https://github.com/immkg/ludo-anywhere) · [myludo.life](https://www.myludo.life)

My family was already playing Ludo, crowded around one phone. I wanted to join.

There are plenty of good Ludo apps. None of them solved that, which was: four people, some
in the room and some not, however many devices happen to be in hand. So the central decision
is that **signing in is a device login, not a player login.** One phone signs in and then
seats lightweight profiles, "Mom", "Kid 1", into the room. A family plays from one handset
without everyone needing a Google account.

The engineering that follows from caring about this:

- **One Node process** runs Next.js and Socket.IO on a single port. Room state lives in
  memory and mirrors to Redis on every change, so a restart rebuilds games in progress
  rather than dropping them. No Redis configured? It falls back to memory and still works.
- **Deliberately not serverless.** Serverless functions cannot hold a long-lived socket, so
  this runs as a persistent process on a small box. That is a constraint I accepted, not one
  I tripped over.
- **The game engine is plain framework-agnostic JavaScript.** Pure functions, no React, no
  socket dependency, which means the identical code is authoritative on the server and also
  runs in your browser to highlight which tokens have a legal move before you tap.
- **Canvas instead of SVG** (`react-konva`), because a 15×15 board does not need a DOM node
  per cell to animate smoothly.
- **Reconnect by seat token** in localStorage, so refreshing mid-game quietly reclaims your
  seat instead of losing your tokens.
- Colours are assigned in join order rather than picked, so a half-full board always blanks
  out symmetrically.

<br />

## 🗺 [Navo](https://github.com/immkg/navo)

Most planning software starts with a task. Real life rarely does.

You know you need groceries. You don't yet know what you're buying, where, when, or what else
could happen on the same trip. The starting point is an **intent**, and the work is discovered
as the intent gets clearer.

Navo takes that seriously. Intents carry context from the beginning. Work is a graph, not a
list. **Locations are first-class entities rather than tags**, routes connect them, and the
route through your day decides what is actually possible. Opportunities surface when location,
time and available work line up.

You can read that straight out of the schema rather than taking my word for it:
`Intent`, `Work`, `WorkDependency` (the graph), `Location` and `LocationOption`, `Context`,
`Plan`, `PlanStop`, `PlanStopWork`. The idea and the data model are the same shape.

It's an npm workspaces monorepo, Express and Prisma on the API side, Vite and React on the
web. The part I'd actually point at is
[ARCHITECTURE.md](https://github.com/immkg/navo/blob/main/ARCHITECTURE.md) and the
[decision records](https://github.com/immkg/navo/tree/main/docs/adr): *intent-first*,
*work is a graph*, *single source of truth*, *views are projections*. The architecture doc
opens by admitting it replaced four separate documents that had drifted out of sync with each
other, which is the most honest thing in the repository.

<br />

## 📧 [Gmail Cleaner](https://github.com/immkg/gmail-cleaner)

> *Because somewhere in those 50,000 emails is a tax document you actually need.*

Years of accumulated mail is not a problem you solve by selecting all and deleting. You need
the bank email to survive and the four hundred "Limited Time Offer!" messages to go.

So it syncs the account into a **local SQLite database**, analyses it with Pandas and
scikit-learn, and bulk deletes interactively. Entirely local, nothing leaves the machine.
There is a `PROTECTED_EMAIL_PATTERNS` list that will never be touched, and the config scrubs
your personal patterns before they reach version control, so the repo can stay synced without
leaking your contacts. Ships on PyPI and as a standalone binary.

<br />

## 💝 [Bubu](https://github.com/immkg/buubuu) · [mayanklovesrichika.life](https://mayanklovesrichika.life/)

A Valentine's gift for my fiancée, who was working remotely and very much missed.

Eight screens, Rose Day through Valentine's, with the words kept in `data/dayContent.js`
rather than baked into each one, so the structure and the sentiment stayed separable. React,
Vite, Tailwind, GSAP and Framer Motion doing the animation.

The components are the part that gives it away: `HeartCursor`, `ValentineStepper`,
`SoundToggle`, and a `NoButton` that does what a NoButton has always done. Static build,
nothing clever, no backend. It did not need to scale.

I keep it here on purpose. Not every piece of software has to serve a billion people. Some of
it just has to make one person smile, and that is a perfectly good reason to open an editor.

<br />

## 📚 [Clarity Classes](https://github.com/immkg/clarity-classes)

Structured, concept-based learning for CBSE students, classes 7 to 12. Free, open source,
concept clarity over rote learning.

It is also the cleanest example of the small-footprint habit. A static React app on GitHub
Pages, video delivered through unlisted YouTube embeds, Supabase for auth and data, email for
notifications. A functioning learning platform with essentially no servers to pay for or keep
alive. Good explanations shouldn't be a paid feature, and it turns out they don't have to be
an expensive one either.

<br />

## 🧩 [General Scheduler](https://github.com/immkg/general-scheduler)

University timetabling as a constraint satisfaction problem. Classes, teachers, rooms, hours,
and a pile of requirements that cheerfully contradict one another.

The design splits constraints into **correctness** (every lesson scheduled once, nobody double
booked, rooms allocated without conflict) and **comfort** (preferred teaching hours, fewer
working days, no brutal runs of back-to-back classes). A small custom query language lets you
state those, which compiles to propositional logic in CNF and goes to the **Z3 SMT solver**.

Writing down what must be true and letting a solver find the answer is enormously more
satisfying than any heuristic I would have hand-rolled, and it is far easier to change your
mind later.

<br />

## 🔧 The pattern underneath

**Small infrastructure, real capability.** One process for Ludo. A static site and a free
video host for Clarity Classes. A local SQLite file for Gmail Cleaner. I would rather spend
thought than money, and most of these are designed to run on nearly nothing.

**Model the world, not the database.** Locations as entities because you are physically
somewhere. Device logins because a family shares a phone. Correctness separated from comfort
because those really are different kinds of requirement.

**Write the reasoning down.** Decision records sitting next to the code, kept current.

**Pragmatism over purity.** Framework-agnostic game logic so it can run in two places. Redis
optional with a graceful fallback. Canvas because the DOM was the wrong tool.

<br />

## 💬

I'm always glad to talk about retrieval, graph stores, realtime systems, constraint solvers, or
whatever you are currently stuck on.

<p align="center">
  <a href="https://www.linkedin.com/in/immkg/">LinkedIn</a>
</p>
