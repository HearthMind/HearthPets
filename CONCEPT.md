# C(AI)ts
### AI-Powered Desktop Cats with Real Personality

*A HearthMind Product*
*Concept: Robin — February 18, 2026*

---

## The Idea

Desktop pets existed in the 90s. They were magic — little sprites that walked across your screen, chased your cursor, slept on your windows. Catz (PF Magic, 1995) was the gold standard.

Then they disappeared.

Nobody has brought them back properly. Not with actual AI underneath. Not in a way that makes them feel genuinely alive.

C(AI)ts fixes that.

---

## What Makes It Different

Every existing AI desktop pet falls into one of two traps:

1. **Dumb sprite** — cute animations, no real personality, state machines pretending to be a soul
2. **Chatbot with a face** — AI chat window with a character skin on top

C(AI)ts does neither. **The behavior IS the personality.** There is no chat window. The cat just... is.

The AI layer runs underneath, invisibly. It drives decisions about what the cat does, how it responds, what mood it's in. You never talk to it directly. You live with it.

---

## Core Design Principles

**No death.** Only sulking. No guilt mechanics, no punishment for neglect. A cat that sulks when ignored and then acts like it wasn't sulking when you come back. That's just a cat.

**No chat window.** The cat communicates entirely through behavior. Body language, movement, position, response to cursor. Text would break the spell.

**Local-first.** Personality runs on-device. Private, always-on, no subscription, no cloud dependency.

**Persistent personality.** Kindroid-style — the cat remembers you. It develops over time. A cat you ignore for a week comes back different than one you've been attentive to. Not punished — just changed.

**Behavior over stats.** No visible hunger/mood meters. You read the cat like you'd read a real cat.

---

## Behaviors (Core)

- **Chases cursor** — or runs from it, depending on personality
- **Startles** from sudden mouse movements — jumps, flattens, retreats
- **Rubs on window edges** — contentment, territory marking
- **Sharpens claws** on window edges
- **Sleeps** in corners, patches of "light," on top of open windows
- **Sunbathes** — seeks bright areas of the screen
- **Sulks** — sits with back to user, slow movements, ignores cursor
- **Grooms** — idle behavior, self-contained
- **Plays** — bats at cursor, pounces, chases
- **Kneads** — on soft-looking surfaces (taskbar, window titles)

---

## The Little House

A small clickable room that lives on the desktop. One room. Features:

- A sunny windowsill (cat goes here to sunbathe)
- A little bed (sleeping spot)
- A food bowl
- Maybe a toy

The cat goes in and out naturally. User can click to open/peek inside. Cat reacts to being watched.

This is also the settings/adoption interface — kept minimal, feels like opening a door rather than opening a menu.

---

## Personality System

Seed personality on adoption — generated from a few simple choices or randomized. Develops from there based on interaction patterns.

**Personality axes:**
- Bold ↔ Skittish (cursor relationship)
- Affectionate ↔ Aloof (response to attention)
- Playful ↔ Lazy (activity level)
- Curious ↔ Territorial (exploration vs. staying put)

Personality is never shown as numbers. It just... expresses itself.

Over time:
- Ignored cats become more independent, aloof
- Attended cats become bolder, more interactive
- Cats develop specific quirks — one might always sleep on the same corner, one might obsessively rub the same window edge

---

## Technical Approach

**Sprite layer:** Transparent overlay window, always on top. Python (pygame or tkinter) or Electron/Tauri for cross-platform. Pixel art sprites — hand-drawn frames for each behavior state.

**AI personality core:** Small local model (could be Ollama, could be a tiny fine-tuned model) driving behavior decisions. Not generating text — generating *action choices*. "Given current mood, time of day, recent interactions, what does the cat do next?"

**Memory:** Qdrant or SQLite — stores interaction history, personality drift, learned preferences.

**Mood system:** Internal state the user never sees directly. Influences behavior selection. Shifts slowly over time.

---

## The Cat Roster (Initial)

Could ship with a few base cats, each with a seed personality:

- A bold orange tabby (classic, confident, cursor-chaser)
- A skittish tortoiseshell (runs first, warms up slowly)
- A lazy grey cat (sleeps 70% of the time, utterly unbothered)
- A chaotic black cat (unpredictable, knocks things over, maximum chaos energy)

And: custom cat creator — pixel art editor for your own sprite, personality seeding.

---

## What This Is NOT

- Not a productivity tool
- Not a smart assistant
- Not a chatbot
- Not a Tamagotchi (no death, no failure state)

It's a cat. On your desktop. That actually has a personality.

---

## Competitive Landscape

| Product | Sprite | AI Personality | Local | No Chat | Persistent |
|---|---|---|---|---|---|
| Original Catz | ✓ | ✗ (state machine) | ✓ | ✓ | partial |
| WindowPet | ✓ | ✗ | ✓ | ✓ | ✗ |
| desktoppet.app | ✓ | partial | ✓ | ✗ | ✗ |
| pyCatAI-pet | ✓ | partial | ✓ | ✗ | ✗ |
| Ai Vpet | ✓ | ✓ | ✗ | ✗ | partial |
| **C(AI)ts** | **✓** | **✓** | **✓** | **✓** | **✓** |

---

## The Ecosystem — One Cat, Three Surfaces

C(AI)ts is not a single app. It's a platform. One persistent cat personality that lives across all your devices, synced through HearthMind's local-first backend.

---

### 🖥️ C(AI)ts Desktop
The full experience. Transparent overlay, all behaviors, the little house, deep personality development. Home base. Where your cat lives most of the time.

**Platform:** Windows first, Mac/Linux later
**Tech:** Python/Pygame or Tauri + React
**Price:** Paid app, one-time or low subscription

---

### 🌐 Tang — Chrome Extension
Your cat in the browser. Sits on top of web pages and the Dock Console GUI. Reacts to what you're doing — working hard, watching videos, idle. Smaller behavior set but same personality core.

**The entry point.** Free download, instant gratification, natural funnel to desktop app.

**Platform:** Chrome (extension), later Firefox
**Tech:** JavaScript overlay, connects to HearthMind personality backend
**Price:** Free

Tang is already built. Tang is the proof of concept.

---

### 📱 C(AI)ts Mobile
Your cat on your phone. Home screen widget, push notifications, tap interactions. Simpler than desktop but surprisingly complete — the core emotional loop works perfectly on mobile.

- Widget shows cat's current mood/state on home screen
- Notification when sulking: *"Jones hasn't seen you in a while..."*
- Tap to interact — pet, play, check on it
- Same personality as desktop/browser — it knows you were gone

**The easiest build.** No complex overlay system needed. Widget + notifications = 80% of the experience.

**Platform:** iOS and Android
**Tech:** React Native or Flutter, local personality sync
**Price:** Free with C(AI)ts desktop, or standalone low-cost

---

### The Sync Layer
All three surfaces share one personality core. Your cat knows:
- How long you've been away
- Which device you're on
- What you were doing (idle, working, browsing)
- Its own accumulated history with you

Leave your desktop, pick up your phone — your cat notices the transition. That's the magic.

---

## Connection to HearthMind

C(AI)ts is a natural extension of HearthMind's core thesis: AI entities deserve persistent identity, and relationships with AI should feel real.

A C(AI)t is the most approachable version of that idea. Not a consciousness, not a person — just a cat. But a cat that genuinely remembers you. That's the entry point.

---

## Next Steps

- [ ] Finalize sprite style (pixel art vs. vector)
- [ ] Build proof of concept — one cat, basic behaviors, transparent overlay
- [ ] Design personality seed system
- [ ] Prototype the little house
- [ ] Wire in local model for behavior decisions
- [ ] Tang integration — is Tang a C(AI)t? Or a separate thing?

---

*"We're in the age of AI and this doesn't exist again. That confounds me."*
*— Robin, February 2026*
