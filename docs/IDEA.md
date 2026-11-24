# Desh Chalao: product definition

Version 0.4 · 2026-11-24 · v0.1 was agreed in chat on 2026-11-22/23. v0.2 folds in the research and competitor changes you accepted on 2026-11-24. v0.3 records that you're OK to show your address on Play ("okay to give address", 2026-11-24), which makes one-time purchases possible, and revises the Business verdict. v0.4 adds the hardening pass (2026-11-24): the feature list, screens and first version are changed in place, and "Hardening decisions" at the end gives the reasons. Some assumptions are still open for correction.
**Since 2026-11-24, [PRD.md](PRD.md) is the source of truth.** This file is the background it was built from; later decisions are recorded in PRD.md. Research is in [RESEARCH.md](RESEARCH.md) ("R§n" below). Competitors and the USP are in [COMPETITORS.md](COMPETITORS.md) ("C§n").

**Labels:**
- **FACT**: you said it.
- **ASSUMPTION**: I inferred it. Correct me before it becomes the product.
- **OPEN QUESTION**: nobody knows yet.
- **HARDENED (H#, B#)**: changed by the hardening pass of 2026-11-24. The reasons are in "Hardening decisions" at the end. Say if you want any of them reversed.

---

## Decisions accepted on 2026-11-24

You said "yes to all changes" on 2026-11-24, so every change below is now **FACT**. Rows 1–8 come from the research; rows 9–17 come from the competitor study; rows 18–19 come from the USP ("yes to both additions", 2026-11-24).

| # | Change (now FACT) | Why | R§ |
|---|---|---|---|
| 1 | v1 has no ads, purchases, analytics or sign-in, so it collects no personal data. Money comes in v1.1, after Decision D3. | Selling anything from a personal account shows your full payments-profile address on Google Play. Ads run into India's under-18 data rules. | 0, 2.1, 2.5, 2.10 |
| 2 | v1 is offered in India only (country setting in Play Console). | Keeps EU/UK privacy and consent rules out of scope. | 2.0 |
| 3 | The store title is 30 characters or fewer, e.g. "Desh Chalao: MLA to PM" (22). | "Desh Chalao: Run India for a Day" is 32 characters, over Play's limit. | 3 |
| 4 | None of these appear in the title, icon, store art, purchase names or game art: the national flag, the Ashoka Chakra, any government emblem or seal, or the name or picture of Parliament, a State Legislature, a court, a secretariat, Rashtrapati Bhavan or Raj Bhavan. All buildings in the game are fictional. | Emblems and Names Act 1950 | 2.9 |
| 5 | No party names at all. Use "Your Party", "Ruling Alliance" and "Opposition". | Thousands of real registered parties exist, so any invented name may already belong to one. | 1 (O1) |
| 6 | A credits screen from v1. | game-icons.net is CC BY 3.0, which requires attribution; it is not CC0 as the old spec said. FreeType's licence asks for a credit line. | 2.11 |
| 7 | A Contact & grievance screen that names you as grievance officer. | Required once you sell, and free to add now. | 2.10 |
| 8 | v1 text says "the Assembly", not a legislature's official name. Names like Parliament, Lok Sabha and Rashtrapati wait for the CM/PM tiers and a legal check. | Emblems and Names Act, item 17 | 2.9 |

**From the competitor study** ([COMPETITORS.md](COMPETITORS.md) §9):

| # | Change (now FACT) | Why | C§ |
|---|---|---|---|
| 9 | "Govern after winning, then rise" is the core and the store pitch. Elections are short result screens. The v1 MLA term is about governing, not just surviving. | 48 of 418 Indian Election Game reviews ask to govern after winning | 2.4, 8 |
| 10 | Every option shows which way it moves each meter, free. The paid "advisor hint" is dropped. | Lapse sells this information and draws the complaint (71 people at 3★) | 3, 4 |
| 11 | No timers, energy or mid-story paywalls, ever. | Money friction is complaint #5 (115+ people), and the big competitors do it on purpose | 3, 4 |
| 12 | Basic music and sound from v1. | Hidden Lake players complain "There is no background music" | 7 |
| 13 | Rules against repeats from v1: no file repeats within N days, chains, regional events. The closed test asks "which file did you see too often?" | Content running out is complaint #1 (236 people) | 3, 4 |
| 14 | A meter near 0 or 100 shows a warning, and no crisis ending comes without one. | "Unfair deaths" is complaint #2 (205 people) | 3, 4 |
| 15 | Hindi text is written or reviewed by a fluent speaker. | Players call Lapse's Hindi poor | 3 |
| 16 | Watch The Mandate and Indian Election Game. | The closest concept, and the most direct competitor | 1.6, 8 |
| 17 | Time marketing pushes to election-result weeks, with no real-election content. | Searches spike in result weeks | 2.2 |
| 18 | A ladder strip on the Desk: "MLA ● — CM ○ — PM ○ · Day 3 of 48". | Makes the USP visible in the first minute | USP U4 |
| 19 | Tapping the ladder opens a "next rung" goal panel, e.g. "To become CM: …". The exact rule is design work. | Shows the promotion goal from minute one | USP U4 |

**Also on 2026-11-24:**
- D3 is decided as (a), "yes agreed" — **FACT**.
- The hardening pass changed the design in place. Each change is tagged **HARDENED** where it sits, and "Hardening decisions" at the end gives the reasons.

---

## 1. What you actually mean

**The game:**
- A single-player, offline Android card game about a political career in India — **FACT**.
- One app, played level by level: **MLA → Chief Minister → Prime Minister** — **FACT**.
- The heart of it is **governing after you win**, not the campaign. Each rung starts with you in office, and the election at the end of a term judges your record — **FACT** (accepted 2026-11-24, C§9).
- At the start the player picks a state. Any state is allowed, and the game is not tied to Tamil Nadu — **FACT**.
- Each in-game day, someone around you (an aide, a party senior, a minister) brings you a file: a short situation with 2–3 options. Your choice moves the meters, the money, and the morale and loyalty of the people around you. Some choices unlock or block later files — **FACT** (original spec).

**The content rules:**
- People and parties are fictional. Real institutions are described neutrally and accurately — **FACT**.
- Decisions are about policy, never religion, caste or communal identity. No real tragedies, no map — **FACT**.
- No connection to Vijay or any real politician, direct or indirect — **FACT**.
- Staying legally safe comes before growth tricks ("legal free is important") — **FACT**.
- Players learn how government really works from short "How it really works" explainers, each with a public source — **FACT**.

**The build:**
- Plays fully offline. Built with libGDX (Java), no server, free tools and free assets only — **FACT**.
- English and Hindi — **FACT**. More Indian languages later, Tamil first — **FACT**.

**Money:**
- Earns from one-time purchases: scenario packs (₹49–99 each) and office themes (₹49), with Restore purchases — **FACT** (original spec). Selling is possible because you're OK to show your address on Play — **FACT** ("okay to give address", 2026-11-24; R§2.10). No ads, ever — **FACT** (D3 (a), "yes agreed", 2026-11-24). Nothing bought ever changes the numbers, and nothing is worded as helping the real country — **FACT** (original spec).
- v1 earns nothing. Money comes in v1.1 — **FACT** (accepted 2026-11-24).
- Never: timers, energy, mid-story paywalls or paid hints. What each option does is shown free — **FACT** (accepted 2026-11-24, C§9).

**Name:** working name Desh Chalao — **FACT**.

**"User get update, right?":**
- **ASSUMPTION:** you meant two things. The player is promoted rung by rung, and new rungs (CM, then PM) arrive as normal Play Store updates, with content shipped inside the app and no server needed. Both are yes.
- **OPEN QUESTION:** confirm this is what you meant.

**The earlier fork is closed.** I offered three products: a PM game, a Tamil Nadu CM game, and a civics trainer.
- You merged the first two into one ladder — **FACT**.
- A civics trainer for schools or exams is a different product — **ASSUMPTION**; see the non-goals in §7.

---

## 2. The complete feature set (where the app ends up)

### CORE: without these it is not the product
- **Card engine.** One file a day, each with 2–3 options. Each option moves meters, money, and people's morale and loyalty. Options can set or require flags and can unlock follow-up files (chains) — **FACT**.
- **Meters** 0–100, shown as bars with icons. Changes animate so cause and effect is obvious — **FACT**.
  - A meter at 0 or at 100 ends the run in a crisis, and so does running out of money — **FACT** for the PM tier, **ASSUMPTION** for every tier.
  - Before you choose, each option shows which way it moves each meter (↑/↓), free — **FACT** (accepted 2026-11-24).
  - A meter near 0 or 100 shows a warning first. No crisis ending comes without one — **FACT** (accepted 2026-11-24).
- **Career ladder** MLA → CM → PM. Promotion is earned through results — **FACT** for the ladder, **ASSUMPTION** for the conditions:
  - MLA → CM: win re-election with strong Party Standing.
  - CM → PM: finish a strong CM term, then win the general election.
- **Tier content** — **FACT** that there are three tiers; **ASSUMPTION** for what each contains:

  | Tier | Desk | Meters | People |
  |---|---|---|---|
  | **MLA** | Your constituency | Development, Public Approval, Party Standing, Reputation; plus a constituency fund | 2–3 aides and party seniors |
  | **CM** | The state government | Economy, Law & Order, Welfare, Farmers & Rural, Centre–State Relations, Public Approval; plus the state treasury | A state cabinet |
  | **PM** | The Union government (your original spec) | Economy, Security, Welfare, Farmers & Rural, Foreign Relations, Public Approval; plus the Treasury in "₹ lakh crore", in-game only | 6 ministers: Finance, Home, Defence, External Affairs, Health, Agriculture |

  The PM tier's meters, Treasury and six ministers are **FACT**.
- **State choice** at the start, picked from a list with search and never from a map — **FACT** (any state, no map).
  - Content is state-generic, with regional tags — **ASSUMPTION**; see D2.
- **Calendar:** a year is 24 days and a term is 5 years, with an election at the end of each term — **FACT** for PM, **ASSUMPTION** for the other tiers.
  - Elections are short result screens that judge your record — **FACT** (accepted 2026-11-24).
- **The House** — **FACT** for Parliament, **ASSUMPTION** for the Assembly:
  - Bills need a majority, built from approval plus loyalty, and failed bills have consequences.
  - A no-confidence motion comes when support falls too low.
- **Budget session:** a multi-file sequence that splits money across departments — **FACT** (PM). The CM tier gets a state version — **ASSUMPTION**.
- **Saving:** autosave after every decision, with save/load and migration between versions — **FACT**.
  - Each save also gets a checksum, an atomic write and a backup copy — **HARDENED (H14)**.
  - A save from a newer version is refused, never overwritten — **HARDENED (H14)**.
  - Saves hold game state only: no typed text and no clock times — **HARDENED (H14)**.
- **Endings:** each crisis ending gets its own short story screen — **FACT**.
- **Correct Hindi text rendering** (complex-script shaping) — **FACT**; see D1. Hindi text is written or reviewed by a fluent speaker — **FACT** (accepted 2026-11-24).
- **Content pipeline** — **FACT**:
  - all content lives in data files;
  - cards are written in a CSV sheet and converted to JSON;
  - a validator rejects missing fields, broken links, impossible requirements and options with no effect;
  - it also fails the build on the content rules, a missing source date, a missing writer, reviewer or neutrality tick, a missing Hindi string, and any option that costs nothing — **HARDENED (B3, B4, H12)**.
- **Sources:** every explainer carries a public source. Uncertain facts go to a review list for you, and nothing is invented — **FACT**. Each source has a "checked on" date, and all sources are re-checked yearly — **HARDENED (H11)**.
- **Fresh files:** no file repeats within N days, and chains and regional events keep the deck changing — **FACT** (accepted 2026-11-24).
- **Content rules:** no real politicians, parties or symbols; nothing on religion, caste or communal identity; no real tragedies; no map — **FACT**.
  - Institution names stay generic in every tier: "the Assembly", "the House", "the Head of State" — **HARDENED (H7)**.
  - Every option costs something — **HARDENED (H12)**.

### EXPECTED: users will be annoyed if these are missing
- **Continue / New career,** where starting a new career warns that it ends the current one — **ASSUMPTION**.
- **First run:** choose a language, then one-line hints, with the first decision within 10 seconds — **FACT** for the hints and the 10 seconds, **ASSUMPTION** for asking the language first.
- **Settings** — **FACT** for the explainers toggle and the items your template lists; the rest are **ASSUMPTION**:
  - language, sound, music, text size. Haptics come later, because they need a permission — **HARDENED (H15)**;
  - "How it really works" on/off;
  - erase progress;
  - credits, the privacy text itself (it works offline), terms, contact, app version — **HARDENED (H6)**.
- **Pause and resume** anywhere, made safe by autosave — **ASSUMPTION**.
- **Basic music and sound effects from v1** — **FACT** (accepted 2026-11-24; competitors' players complain when they're missing).
- **Three difficulty levels** — **FACT**.
- **Achievements** — **FACT**. They stay on the phone; Play Games Services is parked because it brings data collection — **HARDENED (H9)**.
- **Purchases,** once money ships — **FACT** for restore, **ASSUMPTION** for the rest:
  - a pending state for payments that settle later (Play requires apps to handle these, R§1 T10);
  - failed and offline states;
  - restore purchases;
  - each purchase acknowledged at once — **HARDENED (B6)**;
  - owned items re-read from Google Play at every launch — **HARDENED (B6)**;
  - an on-device signature check — **HARDENED (B6)**;
  - prices taken from Google Play — **HARDENED (H13)**.
- **Offline play** — **FACT**.
  - No ads (D3 (a)) — **FACT**.
  - Our own code never uses the network; purchases go through the Play Store app — **HARDENED (H2)**.
- **Accessibility basics** — **ASSUMPTION**:
  - larger text;
  - meters that work for colour-blind players;
  - no meaning carried by colour alone.
- **Contact & grievance,** plus "Report a wrong fact", which opens an email carrying the file's ID. Both are in v1 — **HARDENED (H4, H5)**:
  - a separate free Gmail used only for the game, with an automatic reply within 48 hours;
  - one line above the buttons saying who reads the email, why, and that it's deleted 90 days after the issue is resolved;
  - "Under 18? Please ask a parent or guardian to write for you.";
  - the report email carries only the file ID, language and app version.
- **Credits and licences** — **ASSUMPTION** (R§2.11).

### DIFFERENTIATING: why someone picks this over the alternatives
- **One career from MLA to PM** — **FACT**. Whether any competitor already does this gets checked in the competitors step — **OPEN QUESTION**.
- **Real Indian institutions explained, with sources** — **FACT**.
- **Hindi from day one** — **FACT**.
- **"My state, my career":** regional events by state type — **FACT** for the state choice, **ASSUMPTION** for the regional events.
- **People who remember** — **FACT**:
  - ministers and aides carry morale and loyalty;
  - low morale brings resignation threats, low loyalty brings leaks and rebel votes.
- **Leadership Report at term end,** plus a share-card image sent through Android's share sheet — **FACT**. The card uses list names only and prints "A fictional game" — **HARDENED (H10)**.
- **Neutral and safe:** fictional people and no real parties, so it can be shared at school and at home — **ASSUMPTION**.

### LATER: real ideas, deliberately deferred
- **Tamil, then other state languages** — **FACT** that Tamil is later.
- **Scenario packs** (Pandemic Year, Budget Crisis, Monsoon Failure) and office themes, each sold once: ₹49–99 a pack, ₹49 a theme — **FACT** (original spec). The first pack is the money in v1.1 (Business verdict). Packs sit beside the ladder and never block it — **ASSUMPTION**.
  - The first pack is Monsoon Failure or Budget Crisis. "Pandemic Year" comes last, stays generic and educational (R§2.8), and is never promoted during a real outbreak — **HARDENED (H8)**.
  - No tricolour theme, and no chakra, emblem, seal or real building, in any theme, pack art or name — **HARDENED (H8)**.
- ~~Rewarded ads~~ and ~~"Remove ads ₹99"~~ are **dropped for good** — **FACT** (D3 (a), 2026-11-24).
  - The "second chance" an ad would have paid for becomes free, once per term — **ASSUMPTION** (design work); **HARDENED (H1)**.
  - The paid advisor hint is also **dropped**, because effect direction is free for everyone — **FACT** (accepted 2026-11-24).
- **Play Games achievements, leaderboards and cloud save** — **ASSUMPTION**. Parked: they send gamer identity and play statistics to Google, which adds privacy-form entries and an under-18 data problem — **HARDENED (H9)**.
- **A minister rung** between MLA and CM, and a comeback after losing — **ASSUMPTION**.
- **Classroom mode for teachers** — **ASSUMPTION**.
- **iOS,** which needs Apple's $99 a year — **FACT** that there is no money for it now. Later, only if revenue pays for it.
- **A map,** only one that matches Survey of India boundaries exactly — **FACT**.

---

## 3. The one core loop

**Read the file → choose → watch the meters and people react (sometimes learning "how it really works") → next day.**

- The repeated action is deciding one file, taking about 10–20 seconds — **ASSUMPTION**. A session is 5–10 files — **ASSUMPTION**.
- Around it sits a longer loop — **FACT** for the ladder, **ASSUMPTION** for its shape:
  1. survive the term;
  2. face the election;
  3. get promoted;
  4. sit at a new desk with bigger stakes.
- **Verdict:** this app has a clear repeated action, so the loop itself is not the risk. The risk is running out of fresh files (R§1 A3).

---

## 4. Every screen (where the app ends up)

v1 = in the first version (§8). "Dialog" means it shows over another screen.

### Screens most apps forget

| Screen | What it is for | Label | v1 |
|---|---|---|---|
| Permission priming | **Not needed.** v1 asks for no permissions at all (**HARDENED, H2**). Reminders aren't planned. If they ever come, they're opt-in, at most one a day, never guilt-worded, and a priming screen comes before the OS prompt, because a denial is permanent (**HARDENED, H16**). | ASSUMPTION | — |
| Offline | **Not a screen.** The game is offline. The Store shows an inline "needs internet" note. There are no ads (D3 (a)). | ASSUMPTION | later |
| Force-update | **Not needed** for an offline game. Later, if a save-format break requires it, use Play's In-App Updates. | ASSUMPTION | — |
| "This no longer exists" | **No push notifications or deep links.** The same problem appears differently: a saved career points at a file that an update removed. The dialog says "This file was withdrawn; your career continues." | ASSUMPTION | dialog |
| Session expired | **Not needed:** no accounts. | — | — |
| Empty states | **"Never had any":** Library ("Decide files to unlock explainers"), Achievements, Reports, Purchases. **"Filtered to zero":** a Library topic filter that finds nothing ("Nothing in this topic yet — clear filter"). | ASSUMPTION | — |
| In-app account deletion | **Not needed:** no accounts (R§2.4). The equivalent is Settings → Erase all progress, with a confirmation. | ASSUMPTION | yes |
| Restore purchases | In the Store and in Settings, once purchases exist. | FACT | later |
| Privacy policy and terms inside the app | The privacy text itself sits in About, so it works offline; the web copy and the terms are linked. Play accepts the policy as a "link or text within the app" (R§2.12) — **HARDENED (H6)**. | FACT | yes |
| App version in Settings | Shown in Settings and About. | FACT | yes |

### Screens this app needs

| Screen | What it is for | Label | v1 |
|---|---|---|---|
| Launch | Loads fonts and warms the text cache. No ad may show before it (R§3). | ASSUMPTION | (part of start) |
| Language choice | English / हिन्दी, chosen before any other text. | ASSUMPTION | yes |
| Welcome & disclaimer | "Fictional people. Real institutions, explained with sources. Not affiliated with any government." (R§2.8) | ASSUMPTION | yes |
| Title / Home | Continue, New career, Library, Settings. | ASSUMPTION | yes |
| New career | Pick a state from a list with search (no map), pick a name from a curated list, pick difficulty (later). No typing anywhere in the app — **HARDENED (H3)**. | FACT / ASSUMPTION | yes (no difficulty) |
| Career intro | The tier's opening story card. | ASSUMPTION | yes |
| Desk (the day) | The file card and its options, each showing effect arrows (↑/↓) free. The meters, with a warning near 0 or 100. The ladder strip ("MLA ● — CM ○ — PM ○ · Day 3 of 48"). The date and the money. A tap animates the meters. | FACT | yes |
| Next-rung goal panel | Opened by tapping the ladder strip: what it takes to reach the next rung, e.g. "To become CM: …". | FACT | dialog |
| Explainer card | "How it really works" with a source line and its "checked on" date, shown after relevant files, with a "Report a wrong fact" button — **HARDENED (H4, H11)**. | FACT | yes |
| Pause | Resume, Settings, Quit to title. | ASSUMPTION | dialog |
| Election | Campaign summary and result at term end. | FACT | yes |
| Crisis ending | One story screen per ending. | FACT | yes |
| To be continued | The end of v1 content: "The CM tier arrives in an update." | ASSUMPTION | yes |
| Promotion | MLA → CM and CM → PM: the ceremony, then the new desk. | FACT / ASSUMPTION | later |
| House vote | A bill, the support count, the result. | FACT | later |
| Budget session | Several files in a row that split the budget. | FACT | later |
| No-confidence motion | The vote that can end the run, with one free "second chance" per term instead of an ad (**HARDENED, H1**; ASSUMPTION). | FACT | later |
| People list / person detail | Morale, loyalty, portfolio, pending files, recent decisions. | FACT | later |
| Reshuffle | Change portfolios, a limited number of times per term. | FACT | later |
| Leadership Report | Decision style, best and worst calls, a meters chart. | FACT | later |
| Share card | Preview, then Android's share sheet. No free-typed text on the image (R§2.6), list names only, and a printed "A fictional game" label — **HARDENED (H10)**. | FACT / ASSUMPTION | later |
| Library | Unlocked explainers, filterable by topic and tier. | ASSUMPTION | later |
| Achievements | — | FACT | later |
| Store | Packs and themes priced in ₹, with pending, failed and restored states. Prices come from Google Play. No countdowns, "sale" timers or struck-through prices. Packs get one neutral mention at the end of a term, at most once per career — **HARDENED (H13, B6)**. | FACT | later (v1.1) |
| ~~Advisor-hint offer~~ | **Dropped** (accepted 2026-11-24). Every option shows its effect direction free, on the Desk. | FACT | — |
| Save recovery | A corrupt save is replaced by offering the last good backup. | ASSUMPTION | dialog |
| Settings | Language, sound, music, text size, explainers on/off, erase progress, links, version. Haptics come later (**HARDENED, H15**). | FACT / ASSUMPTION | yes |
| About | Privacy (the full text, in the app); terms (opened in the browser); credits and licences; contact & grievance with the notice and under-18 lines; "Report a wrong fact"; version — **HARDENED (H4–H6, B2)**. | ASSUMPTION | yes |

---

## 5. What you have not thought about

Each item has its detail in RESEARCH.md.

- **Indic text.** Your spec says libGDX's normal font path draws Hindi wrong — **FACT**. That isn't proven yet; the M0 spike settles it (D1, R§1 T1).
- **Content is the real build.** Three tiers × ~200 sourced files × two languages, each checked for accuracy and neutrality. That is far more work than the code (R§1 T5).
- **"Any state" with one content set.** Every file must be true for every state or carry a regional tag. State-specific legal claims are a trap (D2, R§1 T6).
- **Saves must survive updates** that add tiers and change files. That takes stable file IDs, a save version, a "file withdrawn" path and a backup copy (R§1 T4).
- **Play's yearly deadlines.** Apps must target API 36 now, native code must support 16 KB memory pages, and Billing Library versions expire every year. libGDX has to keep up (R§1 T2, D2).
- **Twelve testers first.** Before the public can install the app, 12 testers must stay opted in for 14 days in a row (R§3 #1). Your friends are ready (**FACT**, 2026-11-23). Keeping them opening it daily for 14 days is the part to plan.
- **In India, under 18 is a child for data law.** Ads plus a 13+ audience collide from 13 May 2027 (R§2.5). D3 (a) avoids that: no ads and no data. Only support email is left, and it is an accepted risk (Hardening K5).
- **Selling shows your address.** Selling anything puts your full payments-profile address on your Play listing (R§2.10). You're OK with that — **FACT** (2026-11-24).
- **Earnings bring tax questions.** GST, withholding tax and tax collected at source (TCS) are a chartered accountant's job (R§2.10). You won't pay for one (your rule), so keep every payout statement. A CA only if earnings pay for one, with your yes (Hardening H17, K6).
- **National symbols, government buildings and institution names are restricted for trade use.** The art direction has to be fictional (R§2.9).
- **No analytics means limited numbers.** Without an analytics SDK you get only Play Console figures and tester feedback, so measuring the loop needs a plan (§7).
- **Offline purchases can be cracked.** Accepted on purpose, because checking purchases on a server would mean collecting children's data (Hardening K1).
- **Political players read bias into anything.** Neutrality is a content process, not a sentence in the README (R§1 O1).

---

## 6. The three decisions you must make now

### D1: how Indic text is drawn

**Options:**
- **(a)** Android's own text engine draws each string into a texture through a libGDX platform interface. Desktop builds use Java's text engine.
- **(b)** A HarfBuzz-based libGDX library (e.g. Matn: Apache-2.0, 0 stars) plus FreeType.
- **(c)** English-only v1, with Hindi later.

**Recommendation: (a)** — **ASSUMPTION**.
- It uses the shaping Android already ships for every Indian script, so Tamil later costs nothing extra.
- It adds no extra native library that must meet the 16 KB rule.
- Its cost is managing the text-texture cache.

**Why now:** all UI text passes through it, so changing later means touching every screen.

### D2: what "any state" means

**Options:**
- **(a)** Real states picked from a list. One state-generic content set, plus regional tags: coastal/cyclone, drought, border, hill, industrial.
- **(b)** Fictional states: legally safest, but loses the "my state" pull.
- **(c)** Real states with content written for each: the content load multiplies by 28.

**Recommendation: (a)** — **ASSUMPTION**.
- Leave Union Territories out, because their chief ministers have different powers — **ASSUMPTION**.
- No map — **FACT**.

**Why now:** the content schema, the writing style and every file depend on it.

### D3: who it's for (age) and how it earns

**Options:**
- **(a)** 13+ as your spec says, with no ad SDK. One-time purchases only, from v1.1; your address becomes public on Play.
- **(b)** An 18+ target audience, with rewarded ads plus purchases.
- **(c)** 13+ with ads, only after legal advice. India treats 13–17-year-olds as children: from 13 May 2027 that means verifiable parental consent and no targeted ads.

**Recommendation:** v1 ships with neither ads nor purchases. Choose (a) before v1.1, unless advice clears ads — **ASSUMPTION**.

**Already settled, whatever D3 decides** (accepted 2026-11-24): no timers, no energy, no mid-story paywalls and no paid hints.

**Reopened on 2026-11-24:** you first said your address was not OK to show, then "okay to give address" the same day — **FACT**. So option (a) is open again, and it's still the recommendation:
- 13+, no ad SDK, one-time purchases from v1.1;
- no legal consult and no new personal data;
- about 37× more per install than ads (Business verdict §4).

**Decided: (a).** You said "yes agreed" on 2026-11-24 — **FACT**.

**Why now:** these all follow from it, and switching after launch means a re-review and rewriting:
- the Play target-audience declaration;
- the privacy policy;
- the store listing;
- the art style, which must not look like a children's game.

---

## 7. What success looks like, and what this is not

**One month after launch.** The numbers below are **ASSUMPTION**; set your own (**OPEN QUESTION**).
1. **People come back.** At least 15% of installers still have the game after 7 days, and at least 7% after 30 days. These come from Play Console's installer figures; confirm the metric names when the console is set up.
2. **People finish a term.** At least 40% of closed-test players reach the first election, and there are at least 25 public reviews averaging 4.2 or more.
3. **It stayed clean.** Zero policy warnings and zero takedown or legal notices.

**What this is not:**
- not a real-politics, news or opinion app: no real people, parties, symbols or current events;
- not multiplayer, chat or user posts;
- not real money, betting or loot boxes;
- not exam prep: the explainers serve the game, not a syllabus;
- not a map;
- not a government service, and never "official";
- not pay-to-win: nothing bought changes the numbers;
- not on iOS until revenue pays Apple's fee.

**Watch list and timing** — **FACT** (accepted 2026-11-24, C§9):
- Watch The Mandate, the closest concept, and Indian Election Game. If Indian Election Game adds governing, the gap narrows.
- Time marketing pushes to election-result weeks, when searches spike, without referring to real elections in the content.

---

## 8. The first version: the smallest one worth shipping

**Goal:** one real player completes the core loop through one MLA term, and you learn whether they come back.

**In:**
- **The MLA tier only,** in one shortened term: 2 in-game years (48 days) ending in re-election — **ASSUMPTION**. It starts after you've won your seat, and its files are about governing your constituency — **FACT** (accepted 2026-11-24).
- **Content:**
  - 40 files with chains, plus a few recurring constituency files — **FACT** for 40 starter cards;
  - 4 meters plus the constituency fund;
  - 3–4 crisis endings;
  - explainers on about 10 files.
- **State picker** with all 28 states. In v1 the state is cosmetic plus a regional tag — **ASSUMPTION**.
- **English and Hindi** if the D1 spike passes; otherwise English first — **FACT** / **ASSUMPTION**.
- **Autosave** with a backup copy, and save versioning from day one.
- **Free effect arrows on every option, crisis warnings, rules against repeats, basic music and sound, and Hindi reviewed by a fluent speaker** — **FACT** (accepted 2026-11-24).
- **The ladder strip on the Desk, and the next-rung goal panel** — **FACT** (accepted 2026-11-24).
- **No ads, purchases, analytics, sign-in, notifications or permissions.** No typing anywhere, and no network use by our code — **HARDENED (H2, H3)**.
- **From the hardening pass, needed from the first user** — **HARDENED** (the reasons are in Hardening decisions):
  - "Report a wrong fact" on explainer cards and in each file's menu (H4);
  - Contact & grievance with the game's own Gmail, a 48-hour automatic reply, and the notice and under-18 lines (H5, B8);
  - the privacy text inside the app, plus privacy, terms and grievance pages on GitHub Pages (H6, B1, B2);
  - the validator's policy rules and the content audit fields (B3, B4);
  - saves with a checksum, an atomic write and refusal of newer versions (H14);
  - build guards: the permission allow-list, backup rules, no developer shortcuts in release, and keys kept off GitHub (B5);
  - before the first upload: 2-step verification on Google and GitHub, the upload key backed up offline, and a free trademark search (B7, B9).
- **Offered in India only.**

**Screens (12):**
1. Language choice
2. Welcome & disclaimer
3. Title / Home
4. New career
5. Career intro
6. Desk
7. Explainer card
8. Election
9. Crisis ending
10. To be continued
11. Settings
12. About (privacy text, terms link, credits, contact & grievance, "Report a wrong fact", version)

Plus dialogs: pause, erase confirm, save recovery, file withdrawn, next-rung goal.

**Of the screens most apps forget, v1 keeps only what a store rule demands from the first user:**
- the privacy-policy link inside the app (Play User Data policy);
- the "does not represent a government" statement (Play's government-information rule);
- contact & grievance, which the law requires once you sell and which costs nothing to add now (row 7, H5).

Credits stay because a licence requires them. Everything else on that list doesn't apply to v1: no accounts, permissions, push notifications or purchases.

**Out** (these are where the app is headed, not the first build): the CM and PM tiers, people screens, House votes, budget session, Leadership Report, share card, Library, achievements, difficulty, Store, ads and Tamil.

**Before the public:** a closed test with 12 testers opted in for 14 straight days, collecting:
- the day each tester's career fell;
- the file that felt most real;
- any file that felt unfair or biased;
- the file they saw too often (the repetition check) — **FACT** (accepted 2026-11-24).

**Effort** — **ASSUMPTION**: 41 sessions, about 82 hours of your time, including the hardening work. At 10 hours a week that is about 11 weeks to public, counting the 14-day test and Play's review (Business verdict §3). Writing and sourcing the 40 files is the slowest part. Your hours are an **OPEN QUESTION**.

---

## 9. My bar

| Item | Your answer | Label |
|---|---|---|
| What I want back | Users and money | FACT |
| Which comes first | Users first; users bring the money ("user who let us come money", 2026-11-24) | FACT |
| How many users, how much money, by when | No specific target: "everything in profit is welcome" (2026-11-24) | FACT |
| What I can put in: time | "Time is okay, let it take"; no deadline | FACT |
| What I can put in: hours a week | 10 hours a week ("10 hours a week is fine", 2026-11-24) | FACT |
| What I can put in: money | Nothing beyond the Play developer account ("no investment more than playstore developer account", 2026-11-24). So no lawyer, CA, paid tools or paid assets | FACT |
| What I already have: account | A personal Google Play developer account, already created | FACT |
| What I already have: account date | Created after 13 Nov 2023? If so, the 12-tester rule applies | OPEN QUESTION (assumed yes) |
| What I already have: experience | This is your first game | FACT |
| What I already have: skills | Java and full-stack (from your public GitHub) | ASSUMPTION |
| What I already have: 12 testers | Your friends; ready (said 2026-11-23) | FACT |
| What I already have: an audience beyond friends for the first 100 players | Friends only ("communicate with my friends", 2026-11-24). Every other player must come from Play search | FACT |
| Where I sell first | Google Play (**FACT**, 2026-11-24), in India (**ASSUMPTION**: Indian theme, ₹ prices; research recommends India-only for v1) | FACT / ASSUMPTION |
| Showing your address on Play so you can sell | OK ("okay to give address", 2026-11-24; earlier that day it was not OK). One-time purchases are possible from v1.1, and your full payments-profile address will show on your Play listing | FACT |
| What it may cost | Free tools and free tiers only (**FACT**). Paying for anything later, out of the game's own earnings, still needs your yes (**ASSUMPTION**) | FACT / ASSUMPTION |
| Fixed costs | Play account paid. Apple's $99 a year is not planned, so Android only | FACT |
| Legal stance | "Legal free is important": choose the conservative option when unsure | FACT |
| Where the work is kept | Pushed to GitHub regularly: github.com/rameshkumark24/Desh-Chalao, which stays public ("keep it public", 2026-11-24) | FACT |

---

## Open questions (one batch, whenever you're ready)

1. Testers: answered. Your friends are ready (**FACT**, 2026-11-23). Still open: who beyond friends can you reach for the first 100 players? A college, a workplace, WhatsApp or Telegram groups, an audience?
2. Which languages can you, or someone you trust, fact-check cards in?
3. Who writes and checks the cards? You, a helper who knows civics, or me drafting while you verify every source?
4. Answered: 10 hours a week, and no specific target ("everything in profit is welcome"), both 2026-11-24.
5. When was your Play developer account created: before or after 13 Nov 2023?
6. Is the idle game ("App") on Play, and can I get access to its code for Milestone 0? (Its GitHub repo returned 404.)
7. Did "user get update" mean promotion rung by rung, new tiers arriving as app updates, or both?
8. Answered: you said "yes to all changes" and "yes to both additions" on 2026-11-24, so all 19 changes at the top are accepted.
9. Answered: D3 is (a), "yes agreed" (2026-11-24).
10. Answered: the GitHub repo stays public ("keep it public", 2026-11-24).

---

## Business verdict

**DO IT, with a stop rule.** Users and a first payout both need only ORDINARY numbers. A salary-sized income needs RARE ones. **This verdict rests on ASSUMED numbers** (installs, retention, how many players buy); each is labelled below.

- **Written:** 2026-11-24, from IDEA.md, [RESEARCH.md](RESEARCH.md) and [COMPETITORS.md](COMPETITORS.md), including the USP.
- **Revised:** the same day, after you said "okay to give address". The first version found money RARE because nothing could be sold. Now one-time purchases are possible, so the money below comes from them.
- **Updated for the hardening pass** (2026-11-24): v1 grows to 41 sessions and v1.1 to 7. §3, §7, §8 and the SCORE line include them.
- **Labels:**
  - **SEEN**: opened on 2026-11-24 and linked.
  - **DERIVED**: worked out from seen numbers, with the arithmetic shown.
  - **ASSUMED**: a guess, with what would confirm it.
- **Exchange rate:** $1 = ₹92.92 (ECB rate of 2026-11-23, [FX] · SEEN).

### Before the arithmetic

**Your bar** (§9, plus your answers of 2026-11-24):
- **What you want back:** users first; users bring the money (**FACT**).
  - No specific target: "everything in profit is welcome" (**FACT**, 2026-11-24). So I judge money by its first milestones (earning back the $25, then the first payout), and users against example targets.
  - The smallest real money milestone is **your first payout**. Google pays Indian developers by wire transfer in US dollars, and only once your balance reaches **US$100** ([Play-wire] · SEEN).
- **What you can put in:** no cash beyond the Play account, and time "let it take" (**FACT**).
  - **10 hours a week** (**FACT**, "10 hours a week is fine", 2026-11-24).
  - No price is put on your hours (your rule).
- **What you have:** a personal Play account; 12 friends as testers, who are also your only reach (**FACT**).
- **Where you sell:** Google Play (**FACT**), in India (ASSUMPTION).
- **Address on Play: OK** (**FACT**, "okay to give address", 2026-11-24). Accounts that sell "must show their full address on Google Play", taken from your payments profile ([Play-address] · SEEN). From v1.1, anyone can see it on your listing.

**What is judged here** (§8 and D3):
- **The first version:** the MLA tier only, one 48-day term, 40 files, 12 screens; English and Hindi; no ads, purchases or sign-in; India only.
- **v1.1, the first money:** one scenario pack sold once through Google Play, with no ads. This is D3 option (a), which you agreed to on 2026-11-24 (**FACT**).

### 1. Who pays

**The player, once.** Scenario packs at ₹49–99 each and office themes at ₹49 are your own plan (**FACT**, original spec). For the arithmetic I use **one ₹99 scenario pack in v1.1**, such as Monsoon Failure (ASSUMED: the top of your range).
- The packs sit beside the ladder and never block it. MLA → CM → PM stays free, so the USP still holds: "nothing makes you pay to keep going" (C§U2).
- Nothing bought changes the meters (**FACT**).
- Digital items must be sold through Google Play's billing (R§2.7).

**What reaches you from one ₹99 sale: ₹84.15** (DERIVED: 99 × 0.85).
- Google keeps 15% if you enrol in the 15% tier, which is free ([Play-fees] · SEEN). Without enrolling it keeps 30% (R§2.7).
- **Tax is yours to settle.** Google says India-based developers "must determine any tax obligation themselves and pay GST as applicable". That includes GST "under reverse charge on service fee charged by Google" ([Pay-India] · SEEN). Google also takes TDS/TCS out of payouts (R§2.10).
  - The figures below assume no GST is due at this size (ASSUMED). With no paid advice (your rule), that stays an assumption unless earnings pay for a CA (Hardening K6).
  - If GST does apply, about ₹15 of each ₹99 is tax, leaving roughly ₹66–69. Every money figure here would then drop by about a fifth (DERIVED).

**How the money reaches you:**
- As a monthly US-dollar wire, once your balance reaches US$100 (₹9,292). Below that it carries over to the next month ([Play-wire] · SEEN).
  - A search summary mentioned a ₹100 minimum for India, but none of Google's pages I opened show it (NOT VERIFIED). Your payments profile will show the real figure (ME).
- Your bank may charge "from US$0 to US$50 or more" for each wire ([Play-wire] · SEEN). Ask your bank (ME).
- Indian developers due a payout must first pass a KYC check with BillDesk, Google's payment partner ([Pay-hold] · SEEN). It "may require submitting documents, conducting a live video call, and verifying your location" ([Pay-India] · SEEN). This is ME work: your documents and your phone.

**What players pay competitors today** (COMPETITORS §2.3, SEEN 2026-11-23):
- a ₹49 one-time PRO version (MA 2);
- ₹250 upfront (Reigns);
- purchases up to ₹11,300 (Hidden Lake).

A ₹99 pack sits between these.

**A price players accept:** paid once, with the price shown up front, and nothing on a timer.
- Money friction is the genre's complaint #5 (115+ people, C§3).
- India's dark-pattern rules forbid fake countdowns and hidden prices anyway (R§2.7).

**No ads** under D3 (a). §4 shows this costs almost nothing.

### 2. The reachable market (year one, bottom-up)

| Channel | What it gives | Label |
|---|---|---|
| Your 12 friends and their WhatsApp circles | About 50 installs at launch | **FACT** (12) + ASSUMED (×4) |
| Play search for India-politics queries: the only channel that scales | New entrants in this niche reach at least 2,500 installs a month: GovSim had 10K+ in about 4 months, The Mandate 5K+ in about 2. The leader, Indian Election Game, reached at least 6,250 a month (50K+ in about 8 months). Neeti, which doesn't rank, has 100+ after 6 months. | DERIVED from COMPETITORS §1 (badges SEEN 2026-11-23; launch dates ESTIMATED) |
| Election-result weeks | Searches for "election game" peak at 10× the 2026 weekly median (100 vs 10) | SEEN, Google Trends (COMPETITORS §2.2) |

Year one is about 3 months building plus about 9 months live (§3 below).

| Case | Installs a month (M) | Year-one installs | Label |
|---|---|---|---|
| Worst | 100 | ~950 | ASSUMED: like Neeti, it never ranks |
| Likely | 1,200 | ~10,850 | ASSUMED: half the entrants' floor |
| Best | 6,250 | ~56,300 | DERIVED: the leader's pace |

**What would confirm it:** Play Console installs in the first 60 days after launch.

### 3. The cost of the first version

**To build: 18 slices, mostly 2 sessions each (I build, then you review) = 41 sessions,** including 5 for the hardening work.

| # | Slice | Sessions |
|---|---|---|
| 1 | Project skeleton: libGDX + Android (API 36), desktop runner, and a first internal-test upload to check 16 KB alignment. Build guards: permission allow-list, backup rules, release-only checks, `.gitignore` (Hardening B5) | 3 |
| 2 | Hindi text spike (D1a: Android draws text into textures), plus a desktop fallback | 2 |
| 3 | Content schema, CSV → JSON importer, validator, plus the validator's policy rules and the audit fields (Hardening B3, B4) | 4 |
| 4–5 | Engine: meters, effects, flags, chains, the no-repeat rule, crisis warnings, endings | 4 |
| 6 | Saves: autosave, backup, versions, migration tests | 2 |
| 7 | Screens: language, welcome and disclaimer, title, new career (state list) | 2 |
| 8–9 | Desk: the card, effect arrows, meter animation, ladder strip, goal panel | 4 |
| 10 | Explainer card, election result, crisis ending, "to be continued" | 2 |
| 11 | Settings; About (privacy text, terms, credits, contact and grievance, "Report a wrong fact", version); music and sound (Hardening B2) | 3 |
| 12 | Tall phones and edge-to-edge layout; a pass on a 2–3 GB phone | 2 |
| 13 | Balance simulator (runs without screens) to check fairness | 2 |
| 14–16 | Content: 40 files, recurring files and about 10 sourced explainers (2 slices), then a Hindi pass with a fluent reviewer (1 slice) | 6 |
| 17 | Store listing in English and Hindi, icon, screenshots, privacy, terms and grievance pages, and the Play forms: Data safety, content rating, target audience, government declaration (Hardening B1) | 3 |
| 18 | Release: signing, app bundle, internal test, then the closed test | 2 |

At about 2 hours of your time per session (ASSUMED), that is **82 hours** (DERIVED).

| Your hours a week | Build weeks | Fixed waits | To public |
|---|---|---|---|
| 5 | 16.4 | +3 | ~19–20 weeks |
| **10 (FACT)** | **8.2** | **+3** | **~11 weeks** |
| 20 | 4.1 | +3 | ~7 weeks |

**The fixed waits nobody can shorten** ([Play-testing] · SEEN):
- the closed test, with 12 testers "opted in continuously for at least 14 days";
- then Play's production review, which "usually takes seven days or less".

**Then v1.1, the first money** (ASSUMED):
- Play Billing with Restore purchases, plus the purchase handling from the hardening pass (Hardening B6): 3 sessions.
- One scenario pack of about 15 files, with its Hindi pass: 4 sessions.
- That's 7 sessions, about 14 hours, plus Play's review. You can build it during the 60 days you wait for the go result (§7).

**Cash before the first user: ₹0.**

| Item | Cost | Why / source |
|---|---|---|
| Play developer account | ₹0 now ($25 already paid) | **FACT** |
| Privacy-policy page | ₹0: GitHub Pages, which allows it because it isn't an e-commerce site | [GH-pages] · SEEN |
| Domain | ₹0: not needed | — |
| Lawyer | ₹0: not needed for v1 as designed, or for D3 (a) | RESEARCH §2.13 |
| Art, fonts, sounds | ₹0: CC0, OFL, CC BY and Unlicense assets | RESEARCH §2.11 |
| Test phone | ₹0: your own | ASSUMED |

**Later, if it grows:**
- **No paid advice** (your rule, 2026-11-24). Keep every Play payout statement. Use a CA (chartered accountant) for GST, TDS/TCS and income tax (RESEARCH §2.10) only if earnings can pay for one, with your yes (Hardening K6).
- **No legal consult.** It was only needed for ads, and D3 (a) has none.

**To run each month: ₹0.**
- There is no server (**FACT**).
- Play's fee comes out of each sale ([Play-fees] · SEEN). There is no monthly charge.

**To win one user:**
- **Organically:** ₹0 cash.
- **Paid:** a typical install in India costs $0.12, or ₹11.15 ([Linkrunner] · SEEN for the dollar median of casual Android games; ₹ DERIVED). The range is $0.08–0.30 ([Playio-CPI] · SEEN).
- **One install earns** ₹0.84 in the likely case and ₹1.68 in the best (DERIVED, §4).
- **So every paid install still loses money. Organic only.**

### 4. The ROI math

**The model:**
- daily players (DAU) ≈ M × P ÷ 30;
- money earned a month ≈ M × C × ₹84.15.

**The inputs:**

| Input | Worst | Likely | Best | Label |
|---|---|---|---|---|
| M: installs a month | 100 | 1,200 | 6,250 | §2 |
| P: days played per install | 2.0 | 2.5 | 5.8 | DERIVED (see the bullets below) |
| C: share of installs that buy the pack | 0.5% | 1% | 2% | Likely DERIVED: MA 2 PRO has 100K+ installs against MA 2's 1 crore+ (COMPETITORS §2.3). Worst and best ASSUMED at half and double. The first 60 days of v1.1 confirm it. |
| What reaches you per sale | ₹84.15 | ₹84.15 | ₹84.15 | DERIVED (§1), before any GST |

**Why 1% may be high:** MA 2's free version shows ads, which pushes people to buy PRO. Yours shows none.

**How P is derived:**
- The inputs are GameAnalytics' 2026 benchmarks ([GA] · SEEN):
  - median D7 "just under 4%" and median D30 0.69–0.79%;
  - top 10%: D1 40% and D7 11–12%;
  - median D1 about 22% (REPORTED).
- I fitted a curve through D1 and D7, summed it over 30 days, then added the install day and a tail.
- The worst case sits below the median because "75 per cent of games analysed fail to achieve a 3 per cent Day-30 retention rate" in India ([ITV] · SEEN).

**The timeline behind it** (ASSUMED): about 3 months to build, launch around month 3, and the pack on sale from about month 6. That gives 7 months of sales in year one.

**Results at month 12** (all DERIVED):

| | Worst | Likely | Best |
|---|---|---|---|
| Year-one installs | ~950 | ~10,850 | ~56,300 |
| Daily players (M × P ÷ 30) | 7 | **100** | 1,208 |
| Earned a month (M × C × ₹84.15) | ₹42 | **₹1,010** | ₹10,519 |
| Earned in year one (7 months of sales) | ~₹290 | ~₹7,070 | ~₹73,600 |
| First US$100 payout (₹9,292 earned) | about 18 years away, so never in practice | **around month 16** | month 7 |
| Paid out in year one | ₹0 | **₹0** | up to ~₹63,000 |
| Earned per install (C × ₹84.15) | ₹0.42 | ₹0.84 | ₹1.68 |

**What it means:**
- **Running cost:** covered at zero players, because it is ₹0 a month.
- **Earning back the $25 you've already paid (₹2,323):**
  - likely case: about 2,800 installs after the pack goes on sale, so within its first 3 months. The cash comes with the first payout.
  - worst case: about 5,500 installs, which takes 4–5 years;
  - best case: the first week of sales.
- **The first payout** comes around month 16 in the likely case, so ₹0 reaches your bank in year one. Earning the first US$100 inside year one needs **about 1,600 installs a month** (₹9,292 ÷ (7 × ₹0.84)). That is ORDINARY, and the payout follows a month later.

**Against ads (D3 (b) or (c)), for comparison:**
- Rewarded ads earn about ₹0.02 per install in the likely case. That assumes one "second chance" view per 10 days played at $1.00 per 1,000 views ([vmobify], [ITV] · SEEN; DERIVED).
- AdMob also pays only from $100 ([AdMob-thr] · SEEN). Reaching that in year one needs about 57,200 installs a month, 9× the niche leader.
- **So the pack earns about 37× more per install than ads,** with no ad SDK and no under-18 data problem (RESEARCH §2.5).

### 5. The one number that decides it

**Organic installs a month from Play search (M).**

Between the worst and best case it swings both users and money 62×. The share of players who buy swings money 4×, and days played swings daily players about 3× (DERIVED from the §4 inputs).

| Your target (examples) | M needed (likely inputs) | Ordinary or rare? |
|---|---|---|
| 100 daily players at month 12 | 1,200 a month | **ORDINARY**: below the 2,500+ a month that GovSim and The Mandate show (COMPETITORS §1.6) |
| Earning your first US$100 inside year one | ~1,600 a month | **ORDINARY**: still below the new entrants' 2,500+ |
| 500 daily players | 6,000 a month | **RARE**: the niche leader's pace (Indian Election Game, 6,250+ a month, §1.1) |
| ₹10,000 a month at month 12 | ~11,900 a month | **RARE**: about twice the leader |
| 1,000 daily players | 12,000 a month | **RARE**: twice the leader |
| ₹50,000 a month, a salary | ~59,400 a month | **RARE**: about 10× the leader; nobody in the niche is near it |

The benchmarks are competitors' visible numbers: install badges SEEN 2026-11-23, with monthly rates DERIVED from estimated release dates.

### 6. What kills it

1. **Nobody finds it.** Play search never ranks it, and installs stay near the worst case.
   - Neeti has 100+ installs after 6 months and ranks for none of 18 India queries. Politician Career Simulator has 100+ (COMPETITORS §1, SEEN 2026-11-23/24).
   - **Not fatal:** every new app faces this. The ways through are ratings from friends, a Hindi listing, election-week pushes and monthly updates. It costs your hours.
2. **Players leave once the files repeat.** This is the genre's #1 complaint (236+ people, COMPETITORS §3), and it's HARD for everyone.
   - **Not fatal:** it costs you monthly content.
3. **Too few players buy.** Indian players pay rarely, and the US$100 threshold delays the first cash. In the worst case (0.5% buying, 100 installs a month) the first payout never comes in practice.
   - **Not fatal:** packs cost no cash, players still come, and the price and the pack can change (the money check in §8).

None of the three is fatal on its own.

### 7. The cheapest test

The deciding number, organic installs a month, only exists once the app is live on Play. Play won't open production until the 14-day closed test ends ([Play-testing] · SEEN). **No one-week test can measure it. The first version IS the test**: ₹0 cash, about 11 weeks at 10 hours a week.

**What you can do this week, for ₹0:**
- (a) Get the 12 friends ready to join a test track, and agree they'll open the app daily for 14 days.
- (b) Play 10 sample files on paper with 3–5 friends. Does "govern after winning" feel like a game? This is a qualitative read, not the number.

**The result that means go:**
- **Users:** within 60 days of public launch, **1,000+ organic installs a month** and **D7 of 6% or more** (the top-25% band, [GA] · SEEN). Then build the CM tier.
- **Money:** within 60 days of the pack going on sale, **1% or more of new installs buy it**. Then make the next pack, or the ₹49 office themes.

### 8. The verdict

**DO IT, with a stop rule. It rests on ASSUMED numbers. In the likely case the game earns about ₹1,000 a month by month 12, but the first payout lands around month 16.**

**Why, by the rule:**
- There is no fatal finding (§6).
- The first version fits what you can put in: ₹0 cash and about 82 hours of your time (§3). The first money adds about 14 hours.
- **Users:** about 100 daily players needs 1,200 installs a month, which is ORDINARY.
- **Money:** earning the first payout inside year one needs about 1,600 installs a month, which is ORDINARY. ₹10,000 a month needs about 11,900, which is RARE. So expect pocket money, not a salary.
- Every target your bar names reaches its first milestone with ORDINARY numbers, so the rule says DO IT. The stop rule guards the ASSUMED ones.

**Stop rule:**
- **Users:** at **launch + 90 days**, if organic installs are **below 300 a month** and D7 is **below 4%** (the industry median, [GA] · SEEN), stop building new tiers.
  - That is about May 2027 if you start in early December (ASSUMED).
  - Leave the app live, since it costs ₹0 a month, as a portfolio piece, and move to your next idea.
- **Money:** 60 days after the pack goes on sale, if fewer than **0.5% of new installs** buy it, make one change: drop to ₹49, the bottom of your range, or offer a different pack.
  - If it is still below 0.5% after another 60 days, stop making paid packs and keep the game free.

**What would change the money answer:**
- **More to buy:** your plan already has several packs (₹49–99) and office themes (₹49). Each adds sales from the same players (ASSUMED).
- **Charging for the CM and PM tiers:** probably more money per install. But it breaks "nothing makes you pay to keep going" (C§U2) and invites the paywall complaints that are the genre's #5. Not recommended.
- **Ads on top:** about ₹0.02 per install, and they bring back the under-18 legal problem. Not worth it.
- **A different payer:** schools, coaching centres or civics NGOs paying for a classroom edition. Untested; ask 5 teachers before building anything.

[FX]: https://api.frankfurter.app/latest?from=USD&to=INR
[Play-address]: https://support.google.com/googleplay/android-developer/answer/13634081
[Play-fees]: https://support.google.com/googleplay/android-developer/answer/112622
[Play-testing]: https://support.google.com/googleplay/android-developer/answer/14151465
[Play-wire]: https://support.google.com/googleplay/android-developer/answer/2700656
[Pay-India]: https://support.google.com/paymentscenter/answer/7421525
[Pay-hold]: https://support.google.com/paymentscenter/answer/11595946
[AdMob-thr]: https://support.google.com/admob/answer/2772208
[GH-pages]: https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
[vmobify]: https://vmobify.com/blog/casual-game-marketing-strategy
[ITV]: https://indiantelevision.com/iworld/indias-gaming-edge-is-cheap-installs-but-player-retention-lags-report/
[GA]: https://gamedevreports.substack.com/p/gameanalytics-mobile-and-pc-game
[Linkrunner]: https://linkrunner.io/cost-per-install-benchmark
[Playio-CPI]: https://blog.playio.co/mobile-game-cpi-benchmarks-2026

SCORE — first version: ~11 weeks (₹0 cash; at 10 h/week) · likely at month 12: ~100 daily players, ~₹1,000/month earned from one ₹99 pack (first $100 payout ~month 16) · needs: organic Play installs ≥1,600/month (ORDINARY; new entrants show ≥2,500) · DO IT (with a stop rule; rests on ASSUMED numbers)

---

## Hardening decisions

**Written:** 2026-11-24, from IDEA.md v0.3, [RESEARCH.md](RESEARCH.md) and [COMPETITORS.md](COMPETITORS.md). It follows your answers that day:
- D3 is (a), "yes agreed";
- no investment beyond the Play account;
- no specific target;
- push to GitHub regularly.

**What didn't change: the app's best protection is what it doesn't have.** No server, no accounts, no ads, no analytics, no typing, and no network calls from our code. Nothing about a player leaves the phone through us. So most of the hardening is content checks, build checks, careful purchase handling, and risks written down on purpose.

**How to read it:**
- **H#** = a feature that changed (§1). **B#** = something new to build (§2). **D#** = a row of the data table (§3). **E#** = a rule and where it's enforced (§4). **K#** = a risk we accept (§5).
- In §1–§9 above, each changed item is tagged **HARDENED** with its number.
- R§ = RESEARCH.md and C§ = COMPETITORS.md. New links are at the end of this section.

### 1. What changes in the feature set

| # | Feature | Was | Now | Forced by |
|---|---|---|---|---|
| H1 | Rewarded ads, "Remove ads ₹99" | LATER, "only if D3 allows them" | **Dropped for good.** The "second chance" an ad would have paid for becomes free, once per term (ASSUMPTION: design work) | D3 (a), FACT 2026-11-24; R§2.5 (ad data from under-18s); R§2.7 ("Remove ads" when the only ads are opt-in would mislead) |
| H2 | The network | "Offline play, with the network used only for purchases and ads" | **Our code never uses the network.** v1 asks for no permissions at all. From v1.1, only what Google Play Billing adds itself; purchases run through the Play Store app | R§2.1 (data that stays on the phone isn't "collected"); §3 below |
| H3 | Player name | "Pick a name from a curated list" (ASSUMPTION) | **List names only, and no typing anywhere in the app** | R§2.6 (a typed "PM <real name>" on a share card); R§2.8 (impersonation, personality rights). No typing also means no moderation |
| H4 | Report a wrong fact | EXPECTED, ASSUMPTION; not in v1 | **In v1**, on every explainer card and in each file's ⋯ menu. It opens the player's email app with only the file ID, language and app version filled in | R§1 O1, O2 (bias claims, a wrong civic fact); R§2.8 (Play bans false election content) |
| H5 | Contact & grievance | You, named as grievance officer (row 7) | **In v1, with:** a separate free Gmail used only for the game; an automatic reply within 48 hours; one line above the buttons, "Opens your email app. Only the developer reads it, to answer you, and deletes it 90 days after it's resolved."; and "Under 18? Please ask a parent or guardian to write for you." | R§2.10 (E-Commerce Rules: name, 48 hours, one month); R§2.2 (DPDP notice). India's rules exempt some processing of children's data, but support email isn't on that list (my reading of [DPDP-S4] · SEEN, unofficial copy) |
| H6 | Privacy policy in the app | A link in About, opened in the browser | **The full privacy text is inside the app** (About → Privacy), with the web copy linked. It works offline, on any reviewer's phone | R§2.12 (Play accepts "a privacy policy link or text within the app"); H2 (no internet permission) |
| H7 | Institution names in the CM and PM tiers | Generic in v1; "get advice before the CM/PM tiers ship" | **Generic in every tier, for good:** "the Assembly", "the House", "the Upper House", "the Head of State". Never Parliament, Lok Sabha, Rashtrapati, Raj Bhavan, or a court's or secretariat's name. The Hindi pass follows the same rule | R§2.9 (Emblems and Names Act, items 9 and 17); your no-investment rule, so no lawyer |
| H8 | Packs and office themes | Pandemic Year, Budget Crisis, Monsoon Failure; office themes | **The first pack is Monsoon Failure or Budget Crisis. Pandemic Year comes last,** stays generic and educational, and is never promoted during a real outbreak. **No tricolour theme, chakra, emblem, seal or real building** in any theme, pack art or name | R§2.8 (sensitive events); R§2.9 (the flag, and "colorable imitation"); R§1 O7 |
| H9 | Achievements, leaderboards, cloud save | LATER, through Play Games Services | **Achievements stay on the phone. Play Games Services is parked.** It sends gamer identity, analytics and "engagement and spend statistics" to Google. That means new privacy-form entries and, for under-18 players, a DPDP problem | R§2.1, R§2.3, R§2.5 |
| H10 | Share card (LATER) | "No free-typed text on the image" | **Also list names only, and a printed "A fictional game" label,** so a card can't pass as a real politician's record | R§2.6; R§2.8 (misleading claims) |
| H11 | Explainer sources | "Every explainer carries a public source" | **Each source also has a "checked on" date.** The validator warns once a check is over 12 months old, and one pass a year re-checks them all | R§1 O2 (laws and rules change) |
| H12 | Options in a file | No rule | **No free win: every option costs something.** At least one meter falls, money is spent or a person is upset, unless the file is marked as a reward. The validator enforces it | R§1 O1 ("each option framed as a policy trade-off, never 'the good side'") |
| H13 | The Store (v1.1) | "Packs and themes priced in ₹, with pending, failed and restored states" | **Also:** prices come from Google Play and are never typed into the app; no countdowns, "sale" timers or struck-through prices; packs are mentioned once, neutrally, at the end of a term, at most once per career | R§2.7 (Dark Patterns Guidelines: false urgency, drip pricing, nagging) |
| H14 | Saves | "Autosave with a backup copy, and save versioning" | **Also a checksum and an atomic write** (write a new file, then swap). A save from a newer version is refused with "Update the game" and left untouched. Saves hold game state only: no typed text, no clock times. Android's own backup may copy the save to the player's Google account; we never see it | R§1 T4; §3 below; Play's rule on users' own cloud storage ([DS-FAQ] · SEEN) |
| H15 | Haptics | In Settings | **Later.** They need the VIBRATE permission, and v1 asks for none | H2 |
| H16 | Reminders | "If daily reminders are added later, a priming screen…" | **Not planned.** If they ever come: opt-in only, at most one a day, never guilt-worded | R§2.7 (nagging, confirm-shaming) |
| H17 | Paid advice | "A CA before the first payout"; "a legal consult before ads" | **No paid advice** (your rule). There are no ads, so no legal consult is needed. For tax: keep every Play payout statement, and use a CA only if earnings pay for one, with your yes | Your rule (2026-11-24); R§2.10, R§2.13 |

### 2. What we must now build that we had not planned

| # | Build | What it is | When | Sessions | Why |
|---|---|---|---|---|---|
| B1 | Legal pages on the web | A privacy policy written from the data table (§3), terms, and a grievance page, all on GitHub Pages (₹0). The terms say: fiction; no government link; purchases through Google Play and its refunds; report a wrong fact; Indian law; contact | v1 | +1 (slice 17) | R§2.12 |
| B2 | Privacy, contact and reporting inside the app | About → Privacy (the full text). Contact & grievance: your name, "Grievance Officer", the game's email, the 48-hour and one-month promises, and the notice and under-18 lines. "Report a wrong fact" (H4) | v1 | +1 (slice 11) | H4–H6 |
| B3 | Validator policy rules | The build fails on:<br>• a blocklisted real politician, party or symbol name (a list you can extend);<br>• a scheduled name or emblem word (Parliament, Lok Sabha, Rashtrapati, Raj Bhavan, Supreme Court, High Court, Secretariat, "Government of India", "Official", "Sarkari");<br>• religion, caste or communal terms;<br>• a missing source or checked-on date;<br>• a missing writer, reviewer or neutrality tick;<br>• a missing Hindi string;<br>• an option that costs nothing (H12);<br>• an unknown or withdrawn file ID | v1 | +2 (slice 3) | R§1 O1, O2, L3; R§2.9; your content rules |
| B4 | Content audit trail | Each file row records its source, checked-on date, writer, reviewer and neutrality tick. A withdrawn-files list records the ID, date and reason. Git history on GitHub keeps every change | v1 | inside B3 | R§1 O2; "push to GitHub regularly" |
| B5 | Build guards | (a) A permission allow-list: the build fails if the merged manifest gains any permission not on it (v1: none; v1.1: the billing permission).<br>(b) Developer shortcuts (jump to a day, unlock packs) and any logging of purchase data exist only in debug builds.<br>(c) Backup rules cover the save folder only.<br>(d) `.gitignore` keeps keystores, passwords and local settings off GitHub | v1 | +1 (slice 1) | H2, H14, E12, E15 |
| B6 | Purchase handling | Pending purchases never unlock. Each purchase is acknowledged at once (Play refunds it after three days otherwise). Owned items are re-read from Google Play at every launch and resume, so refunds lock again. An on-device signature check; Restore purchases; prices from Play | v1.1 | +1 (on top of 2) | [Billing] · SEEN; R§1 T7, T10 |
| B7 | Account security (your task) | 2-step verification on the Google account that owns Play Console, and on GitHub. Backup codes and the app's upload key kept offline, never in the repo | Before the first upload | 0 (about 30 minutes) | R§1 D1 (one personal account carries everything) |
| B8 | Support inbox routine (your task) | A separate free Gmail, with Gmail's vacation responder (no end date) as the automatic reply within 48 hours. Labels: open / answered / resolved. A 10-minute monthly pass deletes threads resolved more than 90 days ago. "What do you hold about me?" and "delete it" are answered from the thread within the month | Before the listing goes live | 0 (about 1 hour, then 10 minutes a month) | R§2.10; DPDP rights (R§2.4) |
| B9 | Release checklist (your task, with me) | Every release: re-check Data safety if any SDK changed; re-answer the content rating if content changed; target API and 16 KB checks; run on Android 15/16 and a 2–3 GB phone; sources and the "not a government" line in the listing. Before the first launch: a free public trademark search for "Desh Chalao" | Every release | 0 | R§3 #5, #6, #9, #12; R§2.13 |

**Cost:** v1 grows from 36 to **41 sessions**, about 82 hours, or ~11 weeks to public at 10 hours a week. v1.1 grows from 6 to **7 sessions**. The Business verdict (§3) uses these numbers.

**The template's list, and what we do about each:**
- **Legal pages:** built (B1, B2).
- **Report button:** built, for our own content (H4, B2). There is no user content to report.
- **Audit trail:** built, for content (B4). There is no server or admin to audit, and Play Console keeps the order and refund records.
- **Consent screens: not built.** Nothing is collected, so nothing needs consent. The only notices are the two lines above the email buttons (H5).
- **Account-deletion flow: not built.** There are no accounts (R§2.4). "Erase all progress" (v1) and uninstalling remove everything.
- **Data-export path: not built.** We hold no player data, because the save is on the player's phone. Email requests go through B8.
- **Moderation tooling: not built.** There is no user content and no typing (H3).
- **Age gate: not built.** The app collects nothing, so a gate would have no child data to protect. Play shows the declared 13+ audience and handles purchase controls. An age question would itself be personal data, and it stops nobody. Accepted as K3.

### 3. The data minimisation pass

**Field by field:**

| What we planned | Do we need it? | Decision |
|---|---|---|
| A typed player name | No: a list name does the job | **Cut.** List names only (H3); the save keeps a list number |
| State, tier, day, meters, fund, flags, people's morale and loyalty | Yes: this is the game | **Keep**, on the phone |
| Every decision ever made | Only the last N days (for the no-repeat rule) and the chain flags | **Cut the rest.** The later Leadership Report keeps a short summary per term |
| Settings | Yes | **Keep**, on the phone |
| Clock times ("last played", play time) | No: there are no timers | **Cut** |
| Device model, OS version, device IDs, advertising ID | No: no ads and no analytics, and Google's Android vitals cover crashes | **Cut.** The build guard (B5) blocks the advertising-ID permission |
| An analytics SDK, a crash-reporting SDK | No | **Cut** (accepted, K7) |
| Purchase tokens, order IDs, signatures | Only for a moment, to check and acknowledge | **Not stored.** Read from Google Play at each launch, held in memory, then dropped |
| Which packs are owned | Yes, to unlock them | **Not stored by us.** Google Play is asked at each launch |
| Payment details | We never need them | **Never touched.** Google collects them directly |
| Support emails | Yes: the law requires a grievance route | **Keep, briefly:** until 90 days after the issue is resolved |
| Device details in "Report a wrong fact" | No | **Cut.** Only the file ID, language and app version |
| Testers' email addresses | Yes, for Play's closed test | **Keep until production access,** then remove from the list |
| Testers' names on their feedback | No | **Cut.** Four answers per tester, nothing else |

**THE DATA TABLE.** The privacy policy (B1, B2) and Play's Data safety form are written from it. From 2026-11-24 it is kept current in [PRD.md](PRD.md) §8, not here.

| # | What | Why | Where it's kept | Who else receives it (by name; every SDK) | How long | What allows it |
|---|---|---|---|---|---|---|
| D1 | The career save: state, tier, day, meters, fund, flags, people's morale and loyalty, the last N days' files, the name's list number, difficulty, settings, and later the on-device achievements | To play and continue the game | On the phone, in the app's private storage, with one backup copy | **Nobody.** libGDX is code inside the app and sends nothing. If the player has Android backup on, **Google** keeps a copy in the player's own Google account under Google's terms; we never see it | Until the player erases progress or uninstalls. The Android backup follows the player's Google settings | **The service needs it.** It stays on the phone, so Play doesn't count it as collected (R§2.1). The backup falls under Play's rule for users' own cloud storage ([DS-FAQ] · SEEN) |
| D2 | Owned packs (v1.1): product IDs, plus the purchase token, order ID and signature in memory only | To unlock what was bought, and acknowledge it | **Nowhere by us.** Google Play holds the purchase, and we ask at each launch | **Google** (Google Play Billing Library and the Play Store app) holds orders under its own terms | We store nothing | **The service needs it:** the player asked for the purchase |
| D3 | Payment details: card or UPI, and the buyer's name and billing address | To take payment | Google | **Google** only (Google Play's billing). The app never sees them | Google's policy | Google's terms with the buyer. Not ours to declare, because the app never accesses them (R§2.1) |
| D4 | Support and grievance emails: the sender's address, any name in it, the message, and what "Report a wrong fact" fills in (file ID, language, app version) | To answer the person, and the law's grievance duty | The game's own Gmail inbox | **Google** (Gmail, our mail provider) | Deleted 90 days after the issue is resolved (B8) | **The person chose to write:** DPDP's "voluntarily provided" use (s.7(a), ASSUMPTION ⚖️), plus the E-Commerce Rules' grievance duty. Senders under 18: K5 |
| D5 | Testers' Google account emails (your 12 friends) | Play's closed test needs opted-in testers for 14 days | Play Console's tester list | **Google** (Play Console) | Removed once production access is granted | **Consent:** they agreed to test, and Play requires testers (R§3 #1) |
| D6 | Testers' answers: four per tester, no names | For the go/stop decision and to fix files | A Google Form with email collection switched off | **Google** (Google Forms) | Deleted once v1 is public | **Consent:** they answer voluntarily |

**Not ours, but named in the privacy policy:** Google collects its own install statistics and crash reports (Android vitals) from phones whose owners allow it. We see only totals and anonymised crash traces. Reviews and ratings are public and belong to Google Play.

**What the forms say:**
- **Data safety:** "No data collected" and "No data shared". D1 stays on the phone, Google takes D2 and D3 directly, and D4–D6 happen outside the app.
- **Data deletion questions:** answered as "no data collected", with "Erase all progress" in the app (R§2.4).

### 4. Where each rule is enforced

**There is no server of ours, and this pass doesn't add one.** A server would cost money and time, and it would break offline play. It would also receive purchase tokens and IP addresses from 13–17-year-olds, who are children under India's data law. So nothing moves to a server.
- Where a rule sits on the phone and someone could tamper with it, the table says who and how, and §5 records that we accept it.
- Google's servers do part of the job for free: payment, refunds, country availability and family controls.

**Where a rule is enforced:**
- **DEVICE:** our code on the phone.
- **GOOGLE:** Google's servers.
- **BUILD:** checks that fail the build on your PC.
- **YOU:** a routine you run.

| # | Rule | Enforced where | Who could get around it, and how | The test that proves it holds |
|---|---|---|---|---|
| E1 | A pack unlocks only when Google Play says PURCHASED (never PENDING) and the signature checks out | DEVICE, using Google Play's answer. Payment happens on GOOGLE | A player with a rooted phone or a modded APK can fake Play's answer or strip the check (**accepted, K1**) | Unit tests with a fake billing client: PENDING → locked; PURCHASED with a bad signature → locked; a good test signature → unlocked. On a phone: a licence-tester purchase |
| E2 | Every purchase is acknowledged at once | DEVICE | Nobody gains. A miss only refunds the buyer after three days ([Billing] · SEEN) | Unit test: every unacknowledged PURCHASED item is acknowledged on purchase and again at launch. Play Console shows the tester order as acknowledged |
| E3 | Refunded or revoked packs lock again | DEVICE, from GOOGLE's list, at each launch and resume | A player who stays offline keeps a refunded pack until the Play Store reconnects (**K1**) | Unit test: an item missing from the owned list locks. On a phone: refund a tester order in Play Console, relaunch, and the pack locks |
| E4 | Prices shown come from Google Play | DEVICE (the Store screen) | Only a modded copy, which is then the modder's app, not ours | Unit test: the Store shows the price Google Play returns. A code search finds no typed "₹" price |
| E5 | Who can buy: payment, family controls, country | GOOGLE (Play Billing, Family Link, Play's country settings) | A minor using a parent's payment method. A sideloaded APK abroad can't buy, because packs need Google Play | Release checklist (B9): the country list is India only. A licence-tester purchase works |
| E6 | The app collects nothing and makes no network calls | BUILD (permission allow-list) + DEVICE | Only us, by adding an SDK or a permission | The build fails on any permission outside the list. A code search finds no networking code of ours. Before each release, every screen works in airplane mode |
| E7 | No typing anywhere | DEVICE (no text field exists) | Nobody in the app. Editing the save can only change the name's list number | A code search finds no text-input widget. Unit test: a save with an out-of-range name number loads a default name |
| E8 | Content rules: blocklists, scheduled names and emblems, communal terms, sources with checked-on dates, writer/reviewer/neutrality fields, both languages, every option costs something | BUILD (validator) + YOU (neutrality review) | The writer, including me when I draft, through wording that slips past a blocklist. And no program can judge bias | The validator's tests include one failing sample per rule (e.g. "Lok Sabha", a blocklisted party name, an option with no cost, a source with no date), and each must fail the build. The closed test asks which file felt unfair or biased |
| E9 | A withdrawn file never shows again, and saves pointing at it still load | DEVICE (shipped content) + BUILD (withdrawn list) | Nobody, but it takes an app update (**K4**) | Unit test: a save that references a withdrawn ID loads and shows the "file withdrawn" dialog |
| E10 | Saves: version, checksum, atomic write, backup, refusal of newer versions | DEVICE | A player can edit their own save, which only cheats themselves (**K2**) | Unit tests: corrupt bytes → backup offered; a crash mid-write → the old save survives; a newer-version save → "Update the game", file untouched; a migration test for every old version |
| E11 | A crisis warning comes before every crisis ending, and no file repeats within N days | DEVICE (engine) | Someone editing their own save, which only affects them | Balance simulator, thousands of runs: zero crisis endings without a warning, zero repeats within N days |
| E12 | No developer shortcuts and no purchase logging in release builds | BUILD | Only us | A test that the release build can't reach the debug menu, and a search of the release package for the debug classes |
| E13 | 13+ audience, accurate content rating, India only, "not a government", sources in the listing | GOOGLE (Play Console declarations) + YOU | An under-13 installing anyway (**K3**) | Release checklist (B9); Play's pre-launch report |
| E14 | Grievances acknowledged within 48 hours and resolved within a month; emails deleted 90 days after resolution | YOU (inbox routine) + Gmail's automatic reply | Us, by forgetting | Before launch, a test email from another address gets the automatic reply. A monthly reminder, and nothing in "resolved" older than 90 days |
| E15 | Keys and passwords never reach GitHub | BUILD (`.gitignore`) + YOU | Us, by a careless commit to a public repo | Before each push, `git status` shows no keystore or password file. A search of the repo finds no keystore |

### 5. The things we are accepting

Each of these is a decision, not an accident.

| # | Risk | Why we accept it | What would make us revisit |
|---|---|---|---|
| K1 | **Pack piracy.** A modded APK or a rooted phone can unlock packs without paying, and a refunded pack stays open while the player stays offline | The fix is a server that checks purchases. It costs time, breaks offline play, and would receive purchase tokens and IP addresses from 13–17-year-olds, who are children under Indian law. People who pirate rarely pay anyway | Pack earnings big enough to pay for a free-tier server plus a lawyer's view on child data, with your yes |
| K2 | **Save editing.** Players can cheat by editing their own save | It only affects the cheater: there are no leaderboards and no shared economy, and nothing bought depends on the save | Leaderboards ever shipping |
| K3 | **Children install or buy.** Under-13s can install despite the 13+ declaration, and 13–17-year-olds can buy packs with a parent's payment method | The app collects nothing, so there is no child data to protect. Google's family controls cover purchases, and Google handles refunds. An age gate wouldn't stop anyone | Any feature that collects data: an SDK, accounts or a server |
| K4 | **Slow content fixes.** A wrong or offending file stays live until an update passes review, usually within seven days | Without a server or network there's no remote switch. That's the price of collecting nothing | A legal notice. The update is the fix |
| K5 | **Children's data in support email.** A 13–17-year-old may write to the game's email. From 13 May 2027, India's rules want a parent's verifiable consent before processing a child's data, and their exemptions don't cover support email ([DPDP-S4] · SEEN, unofficial copy) | The law requires a grievance route. We keep it minimal: the under-18 line, using the email only to answer, and deleting it after 90 days | Earnings that can pay for advice, or official guidance on support channels |
| K6 | **No paid advice** (your rule). Some grey areas stay grey: whether you count as an "e-commerce entity", whether an offline game is an "online game", and the GST and income tax on payouts | The design avoids every grey area it can: generic names, no ads, no data. What's left is tiny at this size. Keep every payout statement | Earnings that can pay a CA or a lawyer, with your yes, or a notice arriving |
| K7 | **No crash-reporting or analytics SDK.** Fewer details about crashes and how people play | Play Console's statistics, Android vitals and your testers cover v1. Collecting nothing is the design | Crashes in Android vitals that we can't reproduce |
| K8 | **Your name, address and email are public.** Your address is on the listing from v1.1; your name shows as grievance officer from v1 | Play requires them to sell, and so do the E-Commerce Rules. You accepted this (**FACT**) | — |
| K9 | **One personal Play account.** A policy strike or a hijacked login stops everything | 2-step verification (B7) and careful content lower the risk. A second account is not a fix | — |
| K10 | **A public repo.** Anyone can read the plan and the research, and later the code and the content files | You asked for regular GitHub pushes, and chose to keep the repo public (2026-11-24) | — |
| K11 | **Generic institution names.** The CM and PM tiers feel a little less real: "the House", not Lok Sabha | There's no budget for a legal check on the Emblems Act's grey area (R§2.9) | Earnings that can pay for advice, with your yes |
| K12 | **No trademark registration.** Someone else could register "Desh Chalao" | Registration costs money. A free public search before launch catches existing marks (B9) | The game growing |

[DPDP-S4]: https://www.dpdpa.com/schedule/schedule4.html
[DS-FAQ]: https://support.google.com/googleplay/android-developer/answer/10787469
[Billing]: https://developer.android.com/google/play/billing/integrate
