<h1 align="center">👋 Hello, I'm Mayank</h1>

<p align="center">
  <em>I build systems that try to understand language, and small things that make life nicer.</em>
</p>

---

Most of my days go into a stack that takes a question, turns it into a parse tree, resolves the
entities against a semantic graph store, and answers from **structure** rather than from
similarity. Embeddings are wonderful and they will carry you a long way. I keep being pulled
back to approaches where you can point at *why* an answer came out the way it did.

The rest of my time goes into things I wanted to exist. Those are usually more fun to explain.

<br />

## 🧠 What I love building

| | |
|---|---|
| 🌳 **Language that holds its shape** | Parse trees, entity recognition without a statistical model underneath, graph stores that keep meaning instead of rows |
| 🔍 **Retrieval that knows the difference** | Hybrid vector-plus-keyword search, resolving a question to the right table cell rather than the nearest paragraph |
| 🤖 **Agent orchestration** | Workflow frameworks for composing and scaling AI agents |
| 🧱 **Platforms, not apps** | Shared models, shared clients, an SDK, infrastructure that orchestrates the set. The unglamorous layer that decides whether the next ten features are pleasant or painful |
| 📐 **Writing the architecture down** | Decision records next to the code, kept honest. I enjoy this more than I probably should |

<br />

## 🛠️ Things I've built, and why

### 🗺️ [navo](https://github.com/immkg/navo)

An intent-first planning system. Every planner I tried wanted me to think in lists and boards,
but that is not how a day actually works — you form an intention, you carry context, and then
you execute it while physically moving between home, an office, a shop, a school. Where you
are determines what is even possible. Navo models that instead of pretending it away.

The [architecture notes](https://github.com/immkg/navo/blob/main/ARCHITECTURE.md) and decision
records are the honest part of this repo. **Start there if you want to see how I think.**

### 🔎 [TalkingDB/module-ttt](https://github.com/TalkingDB/module-ttt)

Symbolic reasoning workflows at the centre of the retrieval stack above. The answer to "can we
do this structurally instead of statistically" turned out to be mostly yes, and this is where
that lives.

### 🧩 [general-scheduler](https://github.com/immkg/general-scheduler)

Timetable scheduling, handed to Z3. Rooms, teachers, hours, and a pile of constraints that
cheerfully contradict each other. Writing the constraints down and letting a solver find the
answer is enormously more satisfying than any heuristic I could have written by hand. An old
favourite.

### 🎲 [ludo-anywhere](https://github.com/immkg/ludo-anywhere) · [myludo.life](https://www.myludo.life)

Mobile-first multiplayer Ludo. Create a room, send the link, everyone joins from whatever
device is in their hand. Built because getting four people around one physical board turns out
to be the hardest scheduling problem of all.

### 📧 [gmail-cleaner](https://github.com/immkg/gmail-cleaner)

> *"Because somewhere in those 50,000 emails is a tax document you actually need."*

Local-first, SQLite underneath, nothing leaves your machine. I wrote it for myself and then it
seemed unkind not to share.

### 📚 [clarity-classes](https://github.com/immkg/clarity-classes)

Structured, concept-based learning for CBSE students, Classes 7 to 12. Open source and
completely free. Good explanations should not be a paid feature.

<br />

## 🧰 What I reach for

**Python** and **TypeScript** mostly · a bit of **Dart** when something wants to be an app ·
**Kubernetes** and **Terraform** to keep it all upright · **Z3** when the problem deserves a
real solver

<br />

## 💬 Say hello

A good deal of my work lives in private repositories, which is the usual tax on building inside
a company. The public slice is above.

I'm always glad to talk about retrieval, graph stores, agent frameworks, constraint solvers, or
whatever you're currently stuck on. 🙂

<p align="center">
  <a href="https://www.linkedin.com/in/immkg/">LinkedIn</a>
</p>
