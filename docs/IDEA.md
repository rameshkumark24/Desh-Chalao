# Desh Chalao: product definition

Version 0.3 · 2026-11-24 · v0.1 was agreed in chat on 2026-11-22/23. v0.2 folds in the research and competitor changes you accepted on 2026-11-24. v0.3 records that you're OK to show your address on Play ("okay to give address", 2026-11-24), which makes one-time purchases possible, and revises the Business verdict. Some assumptions are still open for correction.
Every later step reads this file, not the chat. Research is in [RESEARCH.md](RESEARCH.md) ("R§n" below). Competitors and the USP are in [COMPETITORS.md](COMPETITORS.md) ("C§n").

**Labels:**
- **FACT**: you said it.
- **ASSUMPTION**: I inferred it. Correct me before it becomes the product.
- **OPEN QUESTION**: nobody knows yet.

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
- Earns from one-time purchases: scenario packs (₹49–99 each) and office themes (₹49), with Restore purchases — **FACT** (original spec). Selling is possible because you're OK to show your address on Play — **FACT** ("okay to give address", 2026-11-24; R§2.10). No ads unless D3 allows them, and the recommendation is none (D3 (a)). Nothing bought ever changes the numbers, and nothing is worded as helping the real country — **FACT** (original spec).
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
- **Endings:** each crisis ending gets its own short story screen — **FACT**.
- **Correct Hindi text rendering** (complex-script shaping) — **FACT**; see D1. Hindi text is written or reviewed by a fluent speaker — **FACT** (accepted 2026-11-24).
- **Content pipeline** — **FACT**:
  - all content lives in data files;
  - cards are written in a CSV sheet and converted to JSON;
  - a validator rejects missing fields, broken links, impossible requirements and options with no effect.
- **Sources:** every explainer carries a public source. Uncertain facts go to a review list for you, and nothing is invented — **FACT**.
- **Fresh files:** no file repeats within N days, and chains and regional events keep the deck changing — **FACT** (accepted 2026-11-24).
- **Content rules:** no real politicians, parties or symbols; nothing on religion, caste or communal identity; no real tragedies; no map — **FACT**.

### EXPECTED: users will be annoyed if these are missing
- **Continue / New career,** where starting a new career warns that it ends the current one — **ASSUMPTION**.
- **First run:** choose a language, then one-line hints, with the first decision within 10 seconds — **FACT** for the hints and the 10 seconds, **ASSUMPTION** for asking the language first.
- **Settings** — **FACT** for the explainers toggle and the items your template lists; the rest are **ASSUMPTION**:
  - language, sound, music, haptics, text size;
  - "How it really works" on/off;
  - erase progress;
  - credits, privacy policy, terms, contact, app version.
- **Pause and resume** anywhere, made safe by autosave — **ASSUMPTION**.
- **Basic music and sound effects from v1** — **FACT** (accepted 2026-11-24; competitors' players complain when they're missing).
- **Three difficulty levels** — **FACT**.
- **Achievements** — **FACT**. Stored on the device first, Play Games Services later — **ASSUMPTION**; see R§2.3.
- **Purchases,** once money ships — **FACT** for restore, **ASSUMPTION** for the rest:
  - a pending state for payments that settle later (Play requires apps to handle these, R§1 T10);
  - failed and offline states;
  - restore purchases.
- **Offline play,** with the network used only for purchases and ads — **FACT**.
- **Accessibility basics** — **ASSUMPTION**:
  - larger text;
  - meters that work for colour-blind players;
  - no meaning carried by colour alone.
- **Contact & grievance,** plus "Report a wrong fact", which opens an email carrying the file's ID — **ASSUMPTION** (R§2.10).
- **Credits and licences** — **ASSUMPTION** (R§2.11).

### DIFFERENTIATING: why someone picks this over the alternatives
- **One career from MLA to PM** — **FACT**. Whether any competitor already does this gets checked in the competitors step — **OPEN QUESTION**.
- **Real Indian institutions explained, with sources** — **FACT**.
- **Hindi from day one** — **FACT**.
- **"My state, my career":** regional events by state type — **FACT** for the state choice, **ASSUMPTION** for the regional events.
- **People who remember** — **FACT**:
  - ministers and aides carry morale and loyalty;
  - low morale brings resignation threats, low loyalty brings leaks and rebel votes.
- **Leadership Report at term end,** plus a share-card image sent through Android's share sheet — **FACT**.
- **Neutral and safe:** fictional people and no real parties, so it can be shared at school and at home — **ASSUMPTION**.

### LATER: real ideas, deliberately deferred
- **Tamil, then other state languages** — **FACT** that Tamil is later.
- **Scenario packs** (Pandemic Year, Budget Crisis, Monsoon Failure) and office themes, each sold once: ₹49–99 a pack, ₹49 a theme — **FACT** (original spec). The first pack is the money in v1.1 (Business verdict). Packs sit beside the ladder and never block it — **ASSUMPTION**.
  - "Pandemic Year" must stay generic: R§2.8.
- **Rewarded ads** for a second chance, only if D3 allows them. The paid advisor hint is **dropped**, because effect direction is free for everyone — **FACT** (accepted 2026-11-24).
  - "Remove ads ₹99" only makes sense once ads exist — **ASSUMPTION**.
- **Play Games achievements, leaderboards and cloud save** — **ASSUMPTION**.
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
| Permission priming | **Not needed.** The app asks for no runtime permissions. If daily reminders are added later, a priming screen must come before the OS notification prompt, because a denial is permanent. | ASSUMPTION | — |
| Offline | **Not a screen.** The game is offline. Store and ad buttons show an inline "needs internet" note. | ASSUMPTION | later |
| Force-update | **Not needed** for an offline game. Later, if a save-format break requires it, use Play's In-App Updates. | ASSUMPTION | — |
| "This no longer exists" | **No push notifications or deep links.** The same problem appears differently: a saved career points at a file that an update removed. The dialog says "This file was withdrawn; your career continues." | ASSUMPTION | dialog |
| Session expired | **Not needed:** no accounts. | — | — |
| Empty states | **"Never had any":** Library ("Decide files to unlock explainers"), Achievements, Reports, Purchases. **"Filtered to zero":** a Library topic filter that finds nothing ("Nothing in this topic yet — clear filter"). | ASSUMPTION | — |
| In-app account deletion | **Not needed:** no accounts (R§2.4). The equivalent is Settings → Erase all progress, with a confirmation. | ASSUMPTION | yes |
| Restore purchases | In the Store and in Settings, once purchases exist. | FACT | later |
| Privacy policy and terms inside the app | Links in About. Play requires the privacy policy link in the app (R§2.12). | FACT | yes |
| App version in Settings | Shown in Settings and About. | FACT | yes |

### Screens this app needs

| Screen | What it is for | Label | v1 |
|---|---|---|---|
| Launch | Loads fonts and warms the text cache. No ad may show before it (R§3). | ASSUMPTION | (part of start) |
| Language choice | English / हिन्दी, chosen before any other text. | ASSUMPTION | yes |
| Welcome & disclaimer | "Fictional people. Real institutions, explained with sources. Not affiliated with any government." (R§2.8) | ASSUMPTION | yes |
| Title / Home | Continue, New career, Library, Settings. | ASSUMPTION | yes |
| New career | Pick a state from a list with search (no map), pick a name from a curated list, pick difficulty (later). | FACT / ASSUMPTION | yes (no difficulty) |
| Career intro | The tier's opening story card. | ASSUMPTION | yes |
| Desk (the day) | The file card and its options, each showing effect arrows (↑/↓) free. The meters, with a warning near 0 or 100. The ladder strip ("MLA ● — CM ○ — PM ○ · Day 3 of 48"). The date and the money. A tap animates the meters. | FACT | yes |
| Next-rung goal panel | Opened by tapping the ladder strip: what it takes to reach the next rung, e.g. "To become CM: …". | FACT | dialog |
| Explainer card | "How it really works" with a source line, shown after relevant files. | FACT | yes |
| Pause | Resume, Settings, Quit to title. | ASSUMPTION | dialog |
| Election | Campaign summary and result at term end. | FACT | yes |
| Crisis ending | One story screen per ending. | FACT | yes |
| To be continued | The end of v1 content: "The CM tier arrives in an update." | ASSUMPTION | yes |
| Promotion | MLA → CM and CM → PM: the ceremony, then the new desk. | FACT / ASSUMPTION | later |
| House vote | A bill, the support count, the result. | FACT | later |
| Budget session | Several files in a row that split the budget. | FACT | later |
| No-confidence motion | The vote that can end the run, with an optional "second chance" offer once ads exist. | FACT | later |
| People list / person detail | Morale, loyalty, portfolio, pending files, recent decisions. | FACT | later |
| Reshuffle | Change portfolios, a limited number of times per term. | FACT | later |
| Leadership Report | Decision style, best and worst calls, a meters chart. | FACT | later |
| Share card | Preview, then Android's share sheet. No free-typed text on the image (R§2.6). | FACT / ASSUMPTION | later |
| Library | Unlocked explainers, filterable by topic and tier. | ASSUMPTION | later |
| Achievements | — | FACT | later |
| Store | Packs and themes priced in ₹, with pending, failed and restored states. | FACT | later |
| ~~Advisor-hint offer~~ | **Dropped** (accepted 2026-11-24). Every option shows its effect direction free, on the Desk. | FACT | — |
| Save recovery | A corrupt save is replaced by offering the last good backup. | ASSUMPTION | dialog |
| Settings | Language, sound, music, haptics, text size, explainers on/off, erase progress, links, version. | FACT / ASSUMPTION | yes |
| About | Privacy policy and terms (opened in the browser), credits and licences, contact & grievance, "Report a wrong fact", version. | ASSUMPTION | yes |

---

## 5. What you have not thought about

Each item has its detail in RESEARCH.md.

- **Indic text.** Your spec says libGDX's normal font path draws Hindi wrong — **FACT**. That isn't proven yet; the M0 spike settles it (D1, R§1 T1).
- **Content is the real build.** Three tiers × ~200 sourced files × two languages, each checked for accuracy and neutrality. That is far more work than the code (R§1 T5).
- **"Any state" with one content set.** Every file must be true for every state or carry a regional tag. State-specific legal claims are a trap (D2, R§1 T6).
- **Saves must survive updates** that add tiers and change files. That takes stable file IDs, a save version, a "file withdrawn" path and a backup copy (R§1 T4).
- **Play's yearly deadlines.** Apps must target API 36 now, native code must support 16 KB memory pages, and Billing Library versions expire every year. libGDX has to keep up (R§1 T2, D2).
- **Twelve testers first.** Before the public can install the app, 12 testers must stay opted in for 14 days in a row (R§3 #1). Your friends are ready (**FACT**, 2026-11-23). Keeping them opening it daily for 14 days is the part to plan.
- **In India, under 18 is a child for data law.** Ads plus a 13+ audience collide from 13 May 2027 (R§2.5).
- **Selling shows your address.** Selling anything puts your full payments-profile address on your Play listing (R§2.10). You're OK with that — **FACT** (2026-11-24).
- **Earnings bring tax questions.** GST, withholding tax and tax collected at source (TCS) are a chartered accountant's job (R§2.10).
- **National symbols, government buildings and institution names are restricted for trade use.** The art direction has to be fictional (R§2.9).
- **No analytics means limited numbers.** Without an analytics SDK you get only Play Console figures and tester feedback, so measuring the loop needs a plan (§7).
- **Offline purchases can be cracked.** Accept it.
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

**Your yes makes (a) a FACT.**

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
- **No ads, purchases, analytics, sign-in, notifications or permissions.**
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
12. About (privacy policy and terms links, credits, contact & grievance, version)

Plus dialogs: pause, erase confirm, save recovery, file withdrawn, next-rung goal.

**Of the screens most apps forget, v1 keeps only what a store rule demands from the first user:**
- the privacy-policy link inside the app (Play User Data policy);
- the "does not represent a government" statement (Play's government-information rule).

Credits stay because a licence requires them. Everything else on that list doesn't apply to v1: no accounts, permissions, push notifications or purchases.

**Out** (these are where the app is headed, not the first build): the CM and PM tiers, people screens, House votes, budget session, Leadership Report, share card, Library, achievements, difficulty, Store, ads and Tamil.

**Before the public:** a closed test with 12 testers opted in for 14 straight days, collecting:
- the day each tester's career fell;
- the file that felt most real;
- any file that felt unfair or biased;
- the file they saw too often (the repetition check) — **FACT** (accepted 2026-11-24).

**Effort** — **ASSUMPTION**: 3–5 weeks of building with an AI coding agent at your hours, plus the 14-day test. Writing and sourcing the 40 files is the slowest part. Your hours are an **OPEN QUESTION**.

---

## 9. My bar

| Item | Your answer | Label |
|---|---|---|
| What I want back | Users and money | FACT |
| Which comes first | Users first; users bring the money ("user who let us come money", 2026-11-24) | FACT |
| How many users, how much money, by when | Not given on 2026-11-24. The Business verdict uses example targets | OPEN QUESTION |
| What I can put in: time | "Time is okay, let it take"; no deadline | FACT |
| What I can put in: hours a week | Not given on 2026-11-24. The Business verdict assumes 10 | OPEN QUESTION |
| What I can put in: money | Nothing beyond the Play developer account | FACT |
| What I already have: account | A personal Google Play developer account, already created | FACT |
| What I already have: account date | Created after 13 Nov 2023? If so, the 12-tester rule applies | OPEN QUESTION (assumed yes) |
| What I already have: experience | This is your first game | FACT |
| What I already have: skills | Java and full-stack (from your public GitHub) | ASSUMPTION |
| What I already have: 12 testers | Your friends; ready (said 2026-11-23) | FACT |
| What I already have: an audience beyond friends for the first 100 players | Friends only ("communicate with my friends", 2026-11-24). Every other player must come from Play search | FACT |
| Where I sell first | Google Play (**FACT**, 2026-11-24), in India (**ASSUMPTION**: Indian theme, ₹ prices; research recommends India-only for v1) | FACT / ASSUMPTION |
| Showing your address on Play so you can sell | OK ("okay to give address", 2026-11-24; earlier that day it was not OK). One-time purchases are possible from v1.1, and your full payments-profile address will show on your Play listing | FACT |
| What it may cost | Free tools and free tiers only; anything paid needs your yes with its price and a free option | FACT |
| Fixed costs | Play account paid. Apple's $99 a year is not planned, so Android only | FACT |
| Legal stance | "Legal free is important": choose the conservative option when unsure | FACT |

---

## Open questions (one batch, whenever you're ready)

1. Testers: answered. Your friends are ready (**FACT**, 2026-11-23). Still open: who beyond friends can you reach for the first 100 players? A college, a workplace, WhatsApp or Telegram groups, an audience?
2. Which languages can you, or someone you trust, fact-check cards in?
3. Who writes and checks the cards? You, a helper who knows civics, or me drafting while you verify every source?
4. How many hours a week? What user and money numbers by what date would make this a success?
5. When was your Play developer account created: before or after 13 Nov 2023?
6. Is the idle game ("App") on Play, and can I get access to its code for Milestone 0? (Its GitHub repo returned 404.)
7. Did "user get update" mean promotion rung by rung, new tiers arriving as app updates, or both?
8. Answered: you said "yes to all changes" and "yes to both additions" on 2026-11-24, so all 19 changes at the top are accepted.
9. D3: yes to (a), 13+ with one-time purchases and no ads? It's the recommendation (§6).

---

## Business verdict

**DO IT, with a stop rule.** Users and a first payout both need only ORDINARY numbers. A salary-sized income needs RARE ones. **This verdict rests on ASSUMED numbers** (installs, retention, how many players buy); each is labelled below.

- **Written:** 2026-11-24, from IDEA.md, [RESEARCH.md](RESEARCH.md) and [COMPETITORS.md](COMPETITORS.md), including the USP.
- **Revised:** the same day, after you said "okay to give address". The first version found money RARE because nothing could be sold. Now one-time purchases are possible, so the money below comes from them.
- **Labels:**
  - **SEEN**: opened on 2026-11-24 and linked.
  - **DERIVED**: worked out from seen numbers, with the arithmetic shown.
  - **ASSUMED**: a guess, with what would confirm it.
- **Exchange rate:** $1 = ₹92.92 (ECB rate of 2026-11-23, [FX] · SEEN).

### Before the arithmetic

**Your bar** (§9, plus your answers of 2026-11-24):
- **What you want back:** users first; users bring the money (**FACT**).
  - You gave no number or date (OPEN). So I judge users and money against example targets.
  - The smallest real money milestone is **your first payout**. Google pays Indian developers by wire transfer in US dollars, and only once your balance reaches **US$100** ([Play-wire] · SEEN).
- **What you can put in:** no cash beyond the Play account, and time "let it take" (**FACT**).
  - Hours a week weren't given, so I use **10 hours a week** (ASSUMED). Tell me your real number and I'll redo the weeks.
  - No price is put on your hours (your rule).
- **What you have:** a personal Play account; 12 friends as testers, who are also your only reach (**FACT**).
- **Where you sell:** Google Play (**FACT**), in India (ASSUMPTION).
- **Address on Play: OK** (**FACT**, "okay to give address", 2026-11-24). Accounts that sell "must show their full address on Google Play", taken from your payments profile ([Play-address] · SEEN). From v1.1, anyone can see it on your listing.

**What is judged here** (§8 and D3):
- **The first version:** the MLA tier only, one 48-day term, 40 files, 12 screens; English and Hindi; no ads, purchases or sign-in; India only.
- **v1.1, the first money:** one scenario pack sold once through Google Play, with no ads. This is D3 option (a): recommended, but it still needs your yes.

### 1. Who pays

**The player, once.** Scenario packs at ₹49–99 each and office themes at ₹49 are your own plan (**FACT**, original spec). For the arithmetic I use **one ₹99 scenario pack in v1.1**, such as Monsoon Failure (ASSUMED: the top of your range).
- The packs sit beside the ladder and never block it. MLA → CM → PM stays free, so the USP still holds: "nothing makes you pay to keep going" (C§U2).
- Nothing bought changes the meters (**FACT**).
- Digital items must be sold through Google Play's billing (R§2.7).

**What reaches you from one ₹99 sale: ₹84.15** (DERIVED: 99 × 0.85).
- Google keeps 15% if you enrol in the 15% tier, which is free ([Play-fees] · SEEN). Without enrolling it keeps 30% (R§2.7).
- **Tax is yours to settle.** Google says India-based developers "must determine any tax obligation themselves and pay GST as applicable". That includes GST "under reverse charge on service fee charged by Google" ([Pay-India] · SEEN). Google also takes TDS/TCS out of payouts (R§2.10).
  - The figures below assume no GST is due at this size (ASSUMED). A CA confirms that before your first payout (R§2.10).
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

**To build: 18 slices, at 2 sessions each (I build, then you review) = 36 sessions.**

| # | Slice | Sessions |
|---|---|---|
| 1 | Project skeleton: libGDX + Android (API 36), desktop runner, and a first internal-test upload to check 16 KB alignment | 2 |
| 2 | Hindi text spike (D1a: Android draws text into textures), plus a desktop fallback | 2 |
| 3 | Content schema, CSV → JSON importer, validator | 2 |
| 4–5 | Engine: meters, effects, flags, chains, the no-repeat rule, crisis warnings, endings | 4 |
| 6 | Saves: autosave, backup, versions, migration tests | 2 |
| 7 | Screens: language, welcome and disclaimer, title, new career (state list) | 2 |
| 8–9 | Desk: the card, effect arrows, meter animation, ladder strip, goal panel | 4 |
| 10 | Explainer card, election result, crisis ending, "to be continued" | 2 |
| 11 | Settings; About (privacy, terms, credits, contact and grievance, version); music and sound | 2 |
| 12 | Tall phones and edge-to-edge layout; a pass on a 2–3 GB phone | 2 |
| 13 | Balance simulator (runs without screens) to check fairness | 2 |
| 14–16 | Content: 40 files, recurring files and about 10 sourced explainers (2 slices), then a Hindi pass with a fluent reviewer (1 slice) | 6 |
| 17 | Store listing in English and Hindi, icon, screenshots, privacy page, and the Play forms (Data safety, content rating, target audience, government declaration) | 2 |
| 18 | Release: signing, app bundle, internal test, then the closed test | 2 |

At about 2 hours of your time per session (ASSUMED), that is **72 hours** (DERIVED).

| Your hours a week | Build weeks | Fixed waits | To public |
|---|---|---|---|
| 5 | 14.4 | +3 | ~17–18 weeks |
| **10 (ASSUMED)** | **7.2** | **+3** | **~10 weeks** |
| 20 | 3.6 | +3 | ~7 weeks |

**The fixed waits nobody can shorten** ([Play-testing] · SEEN):
- the closed test, with 12 testers "opted in continuously for at least 14 days";
- then Play's production review, which "usually takes seven days or less".

**Then v1.1, the first money** (ASSUMED):
- Play Billing with Restore purchases: 2 sessions.
- One scenario pack of about 15 files, with its Hindi pass: 4 sessions.
- That's 6 sessions, about 12 hours, plus Play's review. You can build it during the 60 days you wait for the go result (§7).

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
- **A CA (chartered accountant)** before the first payout, for GST, TDS/TCS and income tax (RESEARCH §2.10). Price not looked up; it needs your yes when the time comes.
- **A legal consult** only if you ever add ads (India's under-18 data rules, RESEARCH §2.13). D3 (a) needs none.

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

The deciding number, organic installs a month, only exists once the app is live on Play. Play won't open production until the 14-day closed test ends ([Play-testing] · SEEN). **No one-week test can measure it. The first version IS the test**: ₹0 cash, about 10 weeks at 10 hours a week.

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
- The first version fits what you can put in: ₹0 cash and about 72 hours of your time (§3). The first money adds about 12 hours.
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

SCORE — first version: ~10 weeks (₹0 cash; at 10 h/week, ASSUMED) · likely at month 12: ~100 daily players, ~₹1,000/month earned from one ₹99 pack (first $100 payout ~month 16) · needs: organic Play installs ≥1,600/month (ORDINARY; new entrants show ≥2,500) · DO IT (with a stop rule; rests on ASSUMED numbers)
