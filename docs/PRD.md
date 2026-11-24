# Desh Chalao: Product Requirements

**Version 1.0 · 2026-11-24.** This is the source of truth for what Desh Chalao is and does. Read it before touching code.
- **It stands alone.** [IDEA.md](IDEA.md), [RESEARCH.md](RESEARCH.md) and [COMPETITORS.md](COMPETITORS.md) are the background it was built from. Where a reason lives there, it's cited as I§, R§ or C§.
- **If they disagree, this file wins.** Change this file first, then the code.
- **What vs how:** this file holds the what and the why. How it is built belongs in the TRD.

**Who's who:**
- **The player:** the person playing.
- **The developer:** the one person who owns the app and its Google Play account. They are also its grievance officer.
- **v1:** the first public version.
- **v1.1:** the next version, which adds the first paid pack.

---

## 1. What this is

1. Desh Chalao is a free, offline, single-player Android card game in English and Hindi. The player starts as an MLA in an Indian state of their choice and governs it one decision a day, rising to Chief Minister and then Prime Minister only through results. v1 holds the MLA level, and the higher levels arrive as free updates.
2. It is for Indian players aged 13 and up who love politics but only get to watch it. It teaches how Indian government really works through short, sourced explainers. Every person and party in it is fictional, and it has no ads, timers or paywalls.
3. In the words a player would use: **"It's the game where you start as an MLA in your own state and actually govern. Do well and you rise to CM, then PM. It's in Hindi, and nothing makes you pay to keep going."** (C§U2)

---

## 2. The user

**Who they are:**
- Indian, 13 or older, and on Android, often a low-end phone (2–3 GB of memory) with patchy internet.
- They follow politics daily on YouTube, TV and WhatsApp, and argue about it, but have never run anything.
- Many would rather play in Hindi.

**The evidence:**
- They ask for this in their own words. 48 of the 418 reviews of Indian Election Game ask to govern after winning, and 10 ask for a career ladder: "Add carrer mode like going from party worker to MLA, MP, CM , PM…" (C§2.4).
- Global president sims draw "please add hindi language" reviews (C§2.4).

**The moment of need:** a few spare minutes on a commute, in a break or at night, with politics on their mind. Often it's right after a news story, and most of all in election-result weeks: searches for "election game" in India then peak at about 10× a normal week (C§2.2). They want to do something, not just watch: "PLEASEEE add the option of governing a state/country after winning the election." (C§2.4)

**What they do today instead** (C§1.7, C§2.1):
- **Watch and argue.** Political YouTube channels have tens of millions of subscribers, and news is shared on WhatsApp. This is the real competitor: a free daily habit.
- **Play election games that stop at the vote count.** Indian Election Game (50K+ installs) uses real parties and seat-by-seat results, with nothing to govern afterwards.
- **Play global president sims in English** (MA 2, Hidden Lake, Lapse, Reigns). Players complain about their timers, paywalls, ads and missing Hindi.
- **Study polity for exams** with Constitution apps and polity quizzes.

**Positioning** (C§U6): For Indian players who love politics but only get to watch it, Desh Chalao is the Hindi-and-English career game that lets you govern your own state as an MLA and earn your way to CM and then PM, unlike election games that stop at the vote count and global president sims that pause your term for a paywall.

---

## 3. The core loop

**As the player experiences it, one day at a time:**
1. **A file arrives.** Someone around you, an aide or a party senior, brings a short situation. The ladder strip reads "MLA ● — CM ○ — PM ○ · Day 3 of 48".
2. **You weigh it.** There are 2–3 options, and each shows arrows (↑/↓) on the meters it would move. Reading takes about 10–20 seconds.
3. **You decide.** One tap. The meters animate and a one-line consequence appears.
4. **Sometimes you learn.** A "How it really works" card explains the real institution behind the file, with its source.
5. **You're warned.** A meter close to its edge shows a warning in words.
6. **Next day.** You tap to go on. A sitting is about 5–10 files, roughly 2 minutes. Nothing runs on a clock: leave for a minute or a month and the same file is waiting.

**The longer loop:**
- You govern through the 48-day term, then face the election, a result screen that judges your record.
- Win, and you rise. In v1 the screen says the CM level arrives in an update, and your career is kept for it.
- Lose, or let a meter hit its edge, and the career ends. You can start again in any state.

---

## 4. Features: v1

**v1 is** the first version sized in the Business verdict (I§ Business verdict §3). It takes 41 build sessions, about 82 hours, which is about 11 weeks to public at 10 hours a week. It contains:
- the MLA level only: one 48-day term, 40 files plus a few recurring files, about 10 explainers and 3–4 crisis endings;
- 12 screens plus dialogs (§6);
- English and Hindi;
- offline play, with no ads, purchases, analytics, sign-in, notifications or permissions;
- availability in India only.

Each feature lists what it **does**, its **acceptance** checks (given / when / then, each checkable by hand on a phone), **when it fails** (what the player sees), and what it **does not** do.

### F1. Language: English and हिन्दी
- **Does:** on first run, the first screen offers "English" and "हिन्दी", before any other text. The choice applies to every screen, file and explainer, and Settings can change it at any time.
- **Acceptance:**
  - Given a fresh install, when the app opens, then the screen shows only the two language names, each in its own script.
  - Given Hindi is chosen, when any screen, file or explainer is shown, then every word is Hindi, and joined letters and vowel signs render correctly. The test strings प्रधानमंत्री, क्षेत्र and श्री show their conjuncts joined, and the ि sign sits before its consonant.
  - Given a career in progress, when the language is switched in Settings, then the same file returns in the new language with the same options. The day, meters and fund are unchanged.
- **When it fails:** Hindi that renders wrong never ships. If the Hindi check fails before release, v1 ships in English only and the Hindi choice is not shown. All store text that mentions Hindi changes with it (§8, C10).
- **Does not:** offer other languages (Tamil comes later), guess the language from the phone, or mix two languages on one screen. The only exception is the language names on the first screen.

### F2. First run and the welcome
- **Does:** after the language choice, one Welcome screen says, in the chosen language: "Fictional people and parties. Real institutions, explained with sources. Not affiliated with any government. No ads. No timers. Nothing to pay to keep going."
  - It has a single Continue button.
  - On first run, Continue goes straight to New career, skipping Home.
  - On Day 1, up to three one-line hints appear once each: how to decide, what the arrows mean, and "Tap the ladder to see how to become CM".
- **Acceptance:**
  - Given a fresh install on a 2–3 GB phone, when a tester taps straight through (language → Continue → pick a state → keep the suggested name → Start → the intro), then the first file is on screen within **10 seconds** of the language screen appearing. Time it with a stopwatch.
  - Given the Welcome has been seen once, when the app launches again, then it opens on Home. The welcome text stays readable in About.
  - Given a hint has been shown, when the same situation comes up again, then the hint does not reappear, in this career or later ones.
- **When it fails:** nothing to fail beyond F11's save errors.
- **Does not:** ask for sign-in, an account, permissions, an age, typed text or consent. Nothing is collected, so there is nothing to consent to. There is no tutorial longer than the one-line hints.

### F3. Home
- **Does:** shows Continue (only when there is a career to continue), New career, Settings and About.
- **Acceptance:**
  - Given no career, then Continue is absent and New career is the main button.
  - Given a career in progress, when Continue is tapped, then the Desk shows the same day and the same file.
  - Given a won career waiting for the CM level, when Continue is tapped, then the "To be continued" screen shows.
  - Given a career that ended (in a crisis or a lost election), then Continue is absent.
- **Does not:** show news, offers, ads, a Library or achievements. Those come later, and ads never.

### F4. New career and the career intro
- **Does:** the player picks one of India's **28 states** from an alphabetical list with a letter index (no map, and no search box, because nothing in the app takes typed text). They pick a name from a list of fictional names, with one suggestion pre-selected, then tap Start. An intro card follows: "You've won your Assembly seat in ‹state›. Now the work begins."
- **Acceptance:**
  - Given the state list, then it holds exactly the 28 states, in the chosen language, and tapping a letter jumps to it.
  - Given the name list, then one name is already selected, and the player can pick any other in one tap.
  - Given a career already exists, when Start is tapped, then a confirmation names it ("Your career in ‹state›, Day 31, will end. This can't be undone."), with Cancel as the default. Only "End it and start" goes on.
  - Given Start, then the intro shows the chosen state and name, and one tap opens Day 1.
- **Does not:**
  - offer union territories in v1;
  - let the player type a name;
  - let the state or name be changed after Start;
  - offer difficulty levels (later).

### F5. The Desk (a day)
- **Does:** shows:
  - the day's file: who brings it, the situation, and its 2–3 options;
  - an arrow (↑/↓) on each option for every meter and for the fund that option changes;
  - the four meters as bars with icons;
  - the constituency fund;
  - the ladder strip "MLA ● — CM ○ — PM ○ · Day N of 48";
  - a pause button.
- **Acceptance:**
  - Given any file, then it shows 2 or 3 options. Each option has arrows for exactly the meters and fund it changes, and no arrow on anything it leaves alone.
  - Given an option is tapped, then the meters animate to their new values, a one-line consequence shows, and the decision is saved before the next file can appear.
  - Given two fast taps (on one option or two), then only the first counts.
  - Given an option costs more than the fund holds, then it is shown as unavailable with "Not enough in the fund" and can't be chosen. At least one option is always available.
  - Given the player leaves the app mid-file and returns, minutes or weeks later, then the same file and options are on screen.
- **When it fails:** if the decision can't be saved (for example, the phone's storage is full), the Desk says "Couldn't save your decision. Free some space and tap to try again." The decision doesn't count until it is saved.
- **Does not:**
  - show how big an effect is (direction only);
  - show future files;
  - undo a decision;
  - run any timer;
  - ever show an ad or "watch to continue".

### F6. Daily files
- **Does:** draws one file a day by the rules in §7.2, so files stay fresh, chains follow from choices, and regional files fit the state.
- **Acceptance** (checked on a phone and with the balance simulator across thousands of careers):
  - Given a full 48-day career, then no file appears twice within N days, and no one-off file or chain step appears twice in the career.
  - Given a choice unlocks a follow-up, then the follow-up appears on a later day of that career. It never appears before the choice, and never in a career where the choice wasn't made.
  - Given a state without a regional tag (for example, no coastline), then files carrying that tag never appear.
  - Every day of every simulated career has an eligible file.
- **Does not:** invent or download content. Every file is written, sourced and reviewed before it ships.

### F7. Meters, warnings and crisis endings
- **Does:** tracks four meters (Development, Public Approval, Party Standing, Reputation), each a whole number from 0 to 100, plus the constituency fund.
  - A meter inside its warning zone shows a warning in words, plus an icon.
  - A meter that reaches 0 or 100 ends the career in a crisis ending, which has its own story screen. v1 has 3–4 endings.
- **Acceptance:**
  - Given a meter enters its warning zone, then the Desk shows a line naming the meter and the edge it's near (e.g. "Public Approval is dangerously low"), and the line is readable without colour.
  - Given a meter outside its warning zone, when any option is chosen, then that meter cannot reach 0 or 100 that day. It stops inside the zone, and the warning shows.
  - Given a meter reaches 0 or 100, then the matching ending shows, the career is over, and Home offers New career.
  - Across thousands of simulated careers, no crisis ending happens without a warning the day before or earlier.
- **Does not:** end a career without warning. Whether an empty fund ends a career is open (§10). Until it's decided, an empty fund only makes costly options unavailable.

### F8. Next-rung goal panel
- **Does:** tapping the ladder strip opens a panel: "To become CM: ‹the rule›", plus where the player stands against it today.
- **Acceptance:**
  - Given any day, when the strip is tapped, then the panel shows the exact rule the election will apply and the player's current standing.
  - Closing the panel returns to the same file.
- **Does not:** hide any factor the election uses, or change the rule during a career. The rule's content is open (§10).

### F9. Explainers ("How it really works")
- **Does:** after about 10 of the v1 files, a card explains the real institution or process behind the file. It shows a source line (the publisher and title), "Checked on ‹date›", and a "Report a wrong fact" button. Settings can turn explainers on or off.
- **Acceptance:**
  - Given explainers are on, when a file with an explainer is decided, then its card shows once in that career, with the source and checked-on date.
  - Given explainers are off, then no explainer card shows.
  - Given "Report a wrong fact" is tapped, then the player's email app opens, addressed to the game's email, with the subject "Wrong fact: ‹file ID›". The body holds only the file ID, the language and the app version.
  - Given the source line is tapped, then the source opens in the phone's browser.
- **When it fails:**
  - **No email app:** a dialog says "No email app found. Write to ‹address› and mention ‹file ID›", with a Copy button.
  - **No browser:** the link is shown as text with a Copy button.
- **Does not:**
  - state anything without a source;
  - mention current events, real politicians or parties;
  - teach to an exam syllabus;
  - send anything by itself.

### F10. Election and "To be continued"
- **Does:** after day 48 is decided, the Election screen judges the record against the goal-panel rule. It shows win or lose, plus the numbers the rule used.
  - **Win:** the "To be continued" screen says "You've been re-elected. The CM level arrives in a free update, and your record carries over." The career is kept for that update.
  - **Lose:** the career ends with a defeat screen.
- **Acceptance:**
  - Given day 48 is decided, then the Election screen appears at once and shows the result and the numbers behind it.
  - Given the same record, then the result is always the same: no hidden dice.
  - Given a won career, when the app is relaunched, then Home's Continue leads to "To be continued". New career warns that starting one ends this career, which would otherwise carry into the CM level.
- **Does not:**
  - simulate seats, campaigns or real elections;
  - let the player re-run an election;
  - sell the next level;
  - promise a date for the CM level.

### F11. Saving, recovery and pause
- **Does:**
  - saves after every decision;
  - keeps one backup copy;
  - checks each save for damage;
  - carries older saves forward through updates;
  - refuses a save made by a newer version;
  - lets the player pause anywhere: Resume, Settings, or Quit to Home, and the career is kept.
- **Acceptance:**
  - Given the app is killed right after an option is tapped, when it relaunches, then the career is either just before that decision (same file, same options) or just after it (the next day). Effects are never applied twice or half.
  - Given the save is damaged, when the app opens, then it asks "Your save couldn't be read. Restore the last good save (Day ‹N›)?", with Restore and Start over. Restore loads the backup.
  - Given a save from a newer version of the app, then the app says "This save is from a newer version of Desh Chalao. Update the game to continue." The save is left untouched.
  - Given an update withdrew today's file, then the app says "This file was withdrawn; your career continues." Another file is drawn for the same day, and past effects stay.
  - Given a v1 career, when a later update installs over it, then the career opens where it was.
- **Does not:** sync to any server or account, keep more than one career, or store typed text, clock times or device details.

### F12. Settings
- **Does:** offers:
  - language;
  - sound on/off and music on/off;
  - text size (Normal / Large);
  - "How it really works" on/off;
  - Erase all progress;
  - links to Privacy, Terms, Credits and Contact;
  - the app version.
- **Acceptance:**
  - Given any toggle is changed, then it takes effect at once and survives a restart.
  - Given Large text, then the text in files and options is at least 25% bigger, and nothing is cut off or overlapping on the smallest test phone.
  - Given Erase all progress, then a confirmation says "Erase your career and settings? This can't be undone.", with Cancel as the default. Confirming returns the app to its first-run state, so the language screen shows on the next launch.
- **Does not:** offer haptics (later; they need a phone permission), notifications, an account or cloud sync.

### F13. About, contact and grievance
- **Does:** shows, each working offline:
  - the full privacy text inside the app, plus a link to the web copy;
  - a link to the Terms;
  - credits and licences;
  - the welcome text;
  - "Report a wrong fact", with the same email as F9 but no file ID;
  - the app version;
  - **Contact & grievance:** the developer's name; the designation "Grievance Officer"; the game's own email address; and "We acknowledge within 48 hours and resolve within one month."
    - Above its buttons: "Opens your email app. Only the developer reads it, to answer you, and deletes it 90 days after it's resolved."
    - Also above them: "Under 18? Please ask a parent or guardian to write for you."
- **Acceptance:**
  - Given airplane mode, when Privacy is opened, then the full text shows.
  - Given Contact & grievance, then the name, designation, email, both timelines and both notice lines are visible without scrolling past anything else.
  - Given Credits, then every library, font, icon set and sound used is listed with its licence: libGDX (Apache-2.0), each game-icons.net author (CC BY 3.0), Noto fonts (OFL), and so on.
- **When it fails:** with no email app or browser, the address or link shows as text with a Copy button.
- **Does not:** contain a form, or collect anything. Writing happens in the player's own email app.

### F14. v1 content
- **Does:** ships in English and Hindi:
  - 40 files with chains, plus recurring constituency files;
  - about 10 explainers;
  - 3–4 crisis endings;
  - the intro, the election texts and the defeat text.
- **Acceptance:**
  - The content validator passes with zero errors (its rules are §7.7).
  - The counts above are met.
  - Every Hindi string has a fluent reviewer recorded against it.
  - Every file carries a writer, a reviewer and a neutrality tick.
  - Before public launch, no file named in the closed test as "unfair or biased" is left unresolved.
- **Does not:** contain anything §7.7 forbids.

### F15. Sound and music
- **Does:** plays background music and simple effects: a tap, a meter change, a warning, an ending.
- **Acceptance:** Given music or sound is turned off in Settings, then it stays off after a restart. Music pauses when the app goes to the background.
- **Does not:** use any audio without a licence that allows commercial use (§8, C12).

### F16. Accessibility, phones and size
- **Does:**
  - offers larger text;
  - gives meters and warnings words and icons, so colour is never the only signal;
  - runs portrait-only on phones;
  - lays out edge-to-edge on Android 15/16;
  - keeps the download small.
- **Acceptance:**
  - Given the phone's greyscale mode is on, then every meter level and warning can still be read.
  - Given Android 15 or 16, then nothing sits under the status bar or the navigation bar.
  - Given a 2–3 GB phone, then a full 48-day career plays with no crash and no visible stutter while the meters animate.
  - The Play download is **under 40 MB**.
- **Does not:** rotate to landscape, or have a tablet-specific layout.

### F17. Offline, with nothing collected
- **Does:** plays completely without internet. The app asks for no permissions, and our code never touches the network.
- **Acceptance:**
  - Given airplane mode from install onward, then every v1 screen and a whole career work.
  - Given Android's app info for Desh Chalao, then it lists no permissions.
  - Play's Data safety form says "No data collected" and "No data shared" (§8).
- **Does not:** include any ad, analytics, crash-reporting or sign-in SDK.

---

## 5. Not in v1

| Item | Why it waits | What brings it in |
|---|---|---|
| **v1.1: the first paid pack.** This brings the Store screen, Google Play billing, and Restore purchases. The pack is one scenario pack of about 15 files at ₹99, either Monsoon Failure or Budget Crisis | v1 must first show that people play. Selling needs payment handling and puts the developer's address on the listing, which has been accepted | v1 is public. It's built during the 60 days of waiting for the go result, and ships about 2 months after launch |
| **The CM level:** the state government desk, six meters and a state treasury, a state cabinet with morale and loyalty, the promotion ceremony, People screens, reshuffles, House votes and a state budget session | Content volume is the main cost. It's built only if v1 finds players | The go result (I§ Business verdict §7): within 60 days of public launch, 1,000+ organic installs a month and a D7 of 6% or more. D7 can't be measured yet (§10 #7) |
| **The PM level:** the Union desk, Treasury, six ministers, the general election and a no-confidence motion | It comes after the CM level | The CM level ships and holds players |
| **A free "second chance", once per term**, replacing the dropped ad | It belongs to the no-confidence motion | The CM level |
| **More scenario packs and office themes** (₹49–99 a pack, ₹49 a theme; Pandemic Year comes last) | They depend on the first pack | The money check: at least 1% of new installs buy the first pack within 60 days of it going on sale |
| **The Leadership Report and share card** | They're a growth feature, and need a full term of data | Soon after v1 launch, as the first growth feature, because reaching players is the top risk (R§1 A1) |
| **Library** of explainers seen | v1 has only about 10 explainers | The CM level adds enough explainers to browse |
| **On-device achievements** | They aren't needed to prove the loop | After the CM level |
| **Three difficulty levels** | v1 tunes one fair difficulty first | The closed test confirms that the default difficulty is fair |
| **Monthly content updates and replies to reviews within 48 hours** | These are operating promises, not code (C§U1 #7) | They start at launch. Depth and update speed are the only moat (C§U3) |
| **Tamil, then other state languages** | Each needs its own fluent reviewer | Hindi proves out, and a reviewer exists |
| **A minister rung between MLA and CM, and a comeback after losing** | They're ideas, not plans | After the PM level |
| **Haptics** | They need the VIBRATE permission, and v1 asks for none | A conscious change to the permission list (§8, C3) |
| **Reminders** | Not planned | If they ever come: opt-in only, at most one a day, never guilt-worded |
| **Google Play Games** (achievements, leaderboards, cloud save) | Parked: it sends player identity and play statistics to Google, which creates a problem with under-18 data | Only with a data-table change (§8) and a decision on children's data |
| **iOS** | Apple charges $99 a year | Earnings pay for it |
| **A classroom edition** | It's a different product | A school or NGO that wants to pay for it |
| **A map** | Legal risk | Only a map that matches Survey of India boundaries exactly; in practice, never |

**Never, by design** (C§U5, I§1):
- ads of any kind, including rewarded ads and "Remove ads";
- timers, energy, mid-story paywalls or paid hints;
- loot boxes or real money;
- real parties, leaders, symbols or lookalikes;
- satire of real politicians;
- news or content about real elections;
- a seat-by-seat election simulation;
- war, conquest or other countries;
- multiplayer, chat or online play;
- accounts or sign-up;
- typed names or any other typed text;
- unsourced or invented facts.

---

## 6. Screens

**v1 screens:**

| # | Screen | Purpose | What it shows with no data |
|---|---|---|---|
| 1 | Language | Choose English or हिन्दी before any other text | Always the same: the two language names |
| 2 | Welcome | Fiction and no-government statement; the no-ads, no-timers promise | Fixed text |
| 3 | Home | Continue · New career · Settings · About | No career: no Continue, and New career is the main button |
| 4 | New career | Pick a state (28, A–Z with a letter index) and a name (from the list), then Start | Never empty, because the lists ship with the app. A suggested name is pre-selected |
| 5 | Career intro | "You've won your Assembly seat in ‹state›. Now the work begins." | Never empty; it always has a state and a name |
| 6 | Desk | The day's file, options with arrows, meters and warnings, the fund, the ladder strip, pause | Can't be empty, because every day has a file. On Day 1 it shows the first-run hints |
| 7 | Explainer | "How it really works" with source, checked-on date and Report a wrong fact | Shown only with content |
| 8 | Election | Win or lose, with the numbers behind it | Shown only at term end |
| 9 | Crisis ending / defeat | The ending's story; the career is over; New career | Shown only at an ending |
| 10 | To be continued | Won. The CM level comes in an update, and the career is kept | Shown only after a win |
| 11 | Settings | Language, sound, music, text size, explainers, Erase, links, version | Defaults: sound on, music on, Normal text, explainers on |
| 12 | About | Privacy text, Terms, Credits, Contact & grievance, Report a wrong fact, version, welcome text | Fixed text |

**v1 dialogs:**

| Dialog | Purpose |
|---|---|
| Pause | Resume · Settings · Quit to Home (the career is kept) |
| Next-rung goal | "To become CM: ‹rule›", plus today's standing |
| New career confirm | Names the career that will end. Cancel is the default |
| Erase confirm | "Erase your career and settings? This can't be undone." Cancel is the default |
| Save recovery | Offers the last good save |
| Newer save | "Update the game to continue." The save is untouched |
| File withdrawn | "This file was withdrawn; your career continues." |
| Couldn't save | "Free some space and tap to try again." |
| No email app / no browser | Shows the address or link as text, with Copy |

**Later screens** (see §5):
- Store, Restore purchases (v1.1);
- Promotion, People list, Person detail, Reshuffle;
- House vote, Budget session, No-confidence motion;
- Leadership Report, Share card;
- Library, Achievements.

Their empty states:
- **Library:** "Decide files to unlock explainers".
- **Achievements:** "None yet".
- **Store when offline:** "Needs internet to buy. Everything you own still works."

---

## 7. The rules of the domain ⭐

### 7.1 Career, time and levels
1. **One career at a time.** Starting a new career ends the current one for good, after a confirmation that names its state and day.
2. **The state and name are fixed at Start.** They never change.
3. **Time moves only by deciding:** one decided file is one day. Nothing happens in real time and nothing waits on a clock. Leaving the app changes nothing.
4. **The v1 term is 48 days** (two in-game years of 24 days). The election follows day 48 at once.
5. **Levels go MLA → CM → PM, in order, earned only by results.** No skipping, and no level is ever sold. v1 holds the MLA level.
6. **A won MLA career is kept unchanged** and continues in the CM level when that update ships. The record carries upward, which is the USP's distinctive part. A crisis ending or a lost election ends a career for good.
7. **The goal panel and the election use the same rule.** The rule never changes during a career, and the election result depends on nothing else. (The rule itself is open, §10.)
8. **If day 48's decision causes a crisis, the crisis ending shows** and there is no election.

### 7.2 Files and options
9. **Every file has 2 or 3 options.** Every option changes something, and every option costs something: a meter falls, money is spent or a person is upset. The only exception is a file marked as a reward. No option is a free win.
10. **At least one option in every file costs no money,** so the player is never stuck.
11. **An option that costs more than the fund holds can't be chosen,** and says why. The fund never goes below 0.
12. **Arrows:** each option shows ↑ or ↓ for every meter and for the fund it changes, giving direction only, never size. No arrow means no change. Arrows are always shown, for everyone, and never sold.
13. **A decision is final.** There is no undo and no replaying a day.
14. **A tap on an option counts once.** Double taps, taps during the animation, and a crash right after a tap never apply a decision twice or half.
15. **Drawing the day's file:** a chain follow-up that is due comes first. Otherwise the file is drawn at random from the eligible files. A file is eligible when:
    - its required choices were made;
    - its regional tag matches the career's state, or it has no tag;
    - it hasn't appeared in the last N days;
    - if it's a one-off, it hasn't appeared in this career at all.
16. **One-off files and chain steps appear at most once per career.** Recurring files can return after N days. A follow-up never appears without the choice that unlocks it.
17. **A withdrawn file never appears again.** A save that points to it still loads: the player sees the "withdrawn" line, gets another file for the same day, and keeps every past effect.
18. **The state changes only names, flavour and regional files.** It never changes the rules.

### 7.3 Meters, money and endings
19. **Meters are whole numbers from 0 to 100:** Development, Public Approval, Party Standing and Reputation. The constituency fund is in-game ₹ only and is never real money.
20. **Within W points of 0 or 100, a meter is in its warning zone** and shows a warning in words.
21. **No crisis without a warning.** A meter can reach 0 or 100 only from inside its warning zone. A change that would carry it from outside the zone to the edge in one step stops inside the zone instead.
22. **A meter at 0 or 100 ends the career** with that edge's ending. Which edges end the career, and how the 3–4 v1 endings are shared among them, is open (§10).
23. **Two meters hitting an edge on the same decision:** the ending is the one for the meter that overshot furthest (measured before stopping at the edge). A tie goes to a fixed order kept in the content data.
24. **An empty fund only blocks costly options** (rule 11). This is provisional, because whether it ends the career is open (§10).
25. **Nothing bought ever changes** a meter, the fund, the election rule or a file's options.

### 7.4 Saves and irreversible actions
26. **Two actions can't be undone, and each needs a confirmation with Cancel as the default:**
    - **New career** ends the current one.
    - **Erase all progress** removes the career, the backup and the settings, and returns the app to its first-run state.

    Decisions need no confirmation: deciding is the game.
27. **The game saves after every decision, before the next file shows.** The old save stays until the new one is complete. Every save is checked for damage, and one backup is kept.
28. **A damaged save is never silently replaced.** The player is offered the backup.
29. **An older app never opens or overwrites a save from a newer one.**
30. **Updates always carry older saves forward.** No update may make an existing career unplayable.
31. **Saves hold game state only.** That includes the list number of the name and the first-run flags (welcome seen, hints shown). They never hold typed text, clock times or device details.

### 7.5 Who sees what
32. **The player sees** their own meters, fund, day, the election rule and their past explainers. They never see future files or the size of an option's effects.
33. **Nobody else sees anything,** because the app sends nothing anywhere. The developer sees only emails a player chooses to send, plus Google Play Console's totals: installs, ratings and crash reports.
34. **A "Report a wrong fact" email carries only** the file ID, the language and the app version.
35. **Anything shareable** (later, the share card) uses list names only and prints "A fictional game".

### 7.6 Language
36. **One language at a time, everywhere.** Switching never changes the career.
37. **Every string ships in both languages, or the build fails.** If Hindi can't render correctly, Hindi isn't offered at all.
38. **Hindi addresses the player as आप.**

### 7.7 Content (what may exist)
39. **People and parties are fictional.** The only party names are "Your Party", "Ruling Alliance" and "Opposition". No real politician, party, symbol, party colour scheme or lookalike appears.
40. **Decisions are about policy,** never religion, caste or communal identity. There are no real tragedies, real events, current affairs or maps.
41. **Institutions are generic in every level, in both languages.** The never-use list is in §9.
42. **Every explainer names a public source and the date it was checked.** Before each release, any check older than 12 months is re-done. Uncertain facts don't ship.
43. **Every file records its writer, its reviewer and a neutrality check.** Hindi is written or reviewed by a fluent speaker.
44. **Disasters and epidemics stay generic and educational,** never tied to a real event. Nothing is promoted during a real disaster.
45. **None of these appears anywhere:**
    - the national flag, the Ashoka Chakra, an emblem or a seal;
    - a picture of a real government building;
    - a tricolour theme.

    "Anywhere" covers the title, icon, store art, game art, themes and purchase names.

### 7.8 Money (from v1.1)
46. **One-time purchases only,** sold only through Google Play: scenario packs (₹49–99) and office themes (₹49). Never ads, subscriptions, consumables, loot boxes or real-money play.
47. **A purchase unlocks only when Google Play reports it as bought** and its signature checks out. A pending purchase never unlocks; it says it's waiting.
48. **Owning is a state, not a count.** Buying, restoring and relaunching all lead to the same "owned", and an item is never granted twice. Every purchase is acknowledged as soon as it's granted, because Google refunds unacknowledged purchases after three days.
49. **Ownership is read from Google Play at every launch and resume,** and the app stores none of it. A refunded or revoked item locks again.
50. **Prices are Google Play's, in ₹,** shown in full before buying.
    - There are no countdowns, "sale" timers, struck-through prices, guilt-wording or repeated prompts.
    - Packs are mentioned at most once per career, neutrally, at the end of a term.
51. **Packs never block the ladder.** MLA → CM → PM is free, always.
52. **No purchase is worded as helping, donating to or supporting the real country.**
53. **Purchases come back with the same Google account,** on a new phone or after a reinstall.

### 7.9 Limits at a glance

| Thing | Limit |
|---|---|
| Options per file | 2–3 |
| Files per day | 1 |
| MLA term | 48 days |
| Careers at once | 1 |
| Backup copies | 1 |
| Meter range | 0–100, whole numbers |
| Fund | never below 0 |
| First-run hints | 3, each shown once |
| Explainer per file | 1, shown once per career |
| Pack mentions | 1 per career |
| Text sizes | 2 |
| Download size | under 40 MB |
| Grievance | acknowledged within 48 hours, resolved within one month |
| Support email kept | until 90 days after the issue is resolved |

### 7.10 Tuning values

These are set with the balance simulator before the closed test, not guessed, and recorded here once set.

| Value | What it is | Status |
|---|---|---|
| N | Days before a file may repeat | Open |
| W | Width of the warning zone, in points | Open |
| Starting values | The four meters and the fund on Day 1 | Open |
| Effect sizes | How far each option moves each meter | Set file by file in the content |

---

## 8. Compliance requirements

These are product requirements. Each is checked before every release unless it says otherwise.

| # | Requirement | From | How it's checked |
|---|---|---|---|
| C1 | Offered in India only | R§2.0 | Play Console country list |
| C2 | The target audience is 13+. The game is not designed for children, and the art doesn't look childish. The content rating questionnaire is answered accurately, and again whenever content changes | R§2.5, R§3 #9 | Play Console declarations; art review |
| C3 | **Nothing is collected.** No ad, analytics, crash-reporting or sign-in SDK. No permissions in v1; v1.1 adds only Google Play's billing permission. Our code never uses the network | R§2.1, R§2.3 | The build fails on any other permission. The airplane-mode test (F17). The data table below |
| C4 | A privacy policy at a public web address and in full inside the app, written from the data table, with an effective date and a note on how changes are announced | R§2.12 | About → Privacy offline; the web page; the Play Console link |
| C5 | "Erase all progress" is the deletion path, and Play's data-deletion questions say no data is collected | R§2.4 | Play Console form |
| C6 | **Contact & grievance**, in the app and on the web: the developer's name, the designation "Grievance Officer", and the game's own email. Acknowledge within 48 hours and resolve within one month. Support email is deleted 90 days after resolution. The notice line and the under-18 line are shown | R§2.10, R§2.12 | Before launch, a test email gets the automatic reply. A monthly inbox check |
| C7 | **Government information:** sources are named in the store description. "This app does not represent any government or political entity" appears in the listing and the app. Play's government-apps declaration is filed | R§2.8 | Listing review; Play Console |
| C8 | Never "Official". No false election content. Every explainer is sourced (rule 42) | R§2.8 | Content validator; listing review |
| C9 | The Emblems and Names Act: rules 41 and 45 cover the title, icon, screenshots, art and purchase names | R§2.9 | Art and listing review; content validator |
| C10 | **Store listing:**<br>• the title is 30 characters or fewer: "Desh Chalao: MLA to PM";<br>• no keyword lists, emojis, capitals, "best" or "#1", and no real person's name;<br>• the first screenshot caption is "Start as an MLA in your state. Govern. Rise to CM, then PM.";<br>• the short description opens "Offline · No ads · हिन्दी";<br>• every claim is true for the version shipped (drop "हिन्दी" if Hindi isn't in it) | R§3 #2, C§U4 | Listing review |
| C11 | Sensitive events: rule 44 | R§2.8 | Content review |
| C12 | **Licences:** every library, font, icon and sound is credited under its licence. Nothing licensed NC, SA, GPL or AGPL. No AI-generated art | R§2.11 | The Credits screen against the asset list |
| C13 | **Technical gates:** target API 36; 16 KB memory pages; edge-to-edge layout. Tested on Android 15/16 and on a 2–3 GB phone | R§0 #9, R§3 #6, #12 | Play Console upload checks; the device test |
| C14 | Before production: a closed test with 12 testers opted in for 14 days in a row | R§3 #1 | Play Console |
| C15 | **v1.1 payments:**<br>• Google Play billing only;<br>• enrolled in the 15% service-fee tier;<br>• pending purchases handled;<br>• a current Billing Library version;<br>• refunds follow Google Play's policy, with one line saying so in the Terms;<br>• rules 46–53 hold;<br>• the developer's address shows on the listing, which is accepted | R§2.7, R§2.10 | Billing tests; Play Console |
| C16 | **Terms** (web): the game is fiction; it has no government link; purchases go through Google Play under its refund policy; how to report a wrong fact; Indian law; contact details | R§2.12 | The web page |
| C17 | **Accounts:** 2-step verification on the Google account that owns Play Console and on GitHub. The upload key and passwords never go into the public repo | R§1 D1 | Before the first upload, and before every push |
| C18 | A free public trademark search for "Desh Chalao" before the first launch | R§2.13 | Once |

### The data table

**This table is kept current here from now on.** Any change to what the app or the developer collects updates this table first, then the privacy policy, then Play's Data safety form.

| # | What | Why | Where it's kept | Who else receives it (by name; every SDK) | How long | What allows it |
|---|---|---|---|---|---|---|
| D1 | The career save: state, level, day, meters, fund, choices made, recent files, the name's list number. Also the settings and first-run flags, and later the on-device achievements | To play and continue the game | On the phone, in the app's private storage, with one backup copy | **Nobody.** libGDX is code inside the app and sends nothing. If the player has Android backup on, **Google** keeps a copy in the player's own Google account under Google's terms. We never see it | Until the player erases progress or uninstalls. The Android backup follows the player's Google settings | **The service needs it.** It never leaves the phone through us, so Play doesn't count it as collected. The player's own backup isn't counted either |
| D2 | Owned packs (v1.1): product IDs. The purchase token, order ID and signature are held in memory only | To unlock what was bought, and acknowledge it | **Nowhere by us.** Google Play holds the purchase, and the app asks at each launch | **Google** (Google Play Billing Library and the Play Store app) | We store nothing | **The service needs it:** a purchase the player asked for |
| D3 | Payment details: card or UPI, the buyer's name and billing address | To take payment | Google | **Google** only (Google Play's billing). The app never sees them | Google's policy | Google's terms with the buyer. The app never accesses them |
| D4 | Support and grievance emails: the sender's address, any name in it, and the message. Reports also carry the file ID, language and app version | To answer the person; the grievance duty | The game's own Gmail inbox | **Google** (Gmail, the mail provider) | Deleted 90 days after the issue is resolved | **The person chose to write.** This is a "voluntarily provided" use under India's data law (an assumption), plus the e-commerce grievance duty. For senders under 18, see accepted risk K5 |
| D5 | The testers' Google account emails (12 people) | Play's closed test needs testers who stay opted in | Play Console's tester list | **Google** (Play Console) | Removed once production access is granted | **Consent:** they agreed to test |
| D6 | The testers' answers: four per tester, with no names | The go/stop decision and fixing files | A Google Form with email collection off | **Google** (Google Forms) | Deleted once v1 is public | **Consent:** they answer voluntarily |

**Not ours, but named in the privacy policy:** Google's own install statistics and crash reports (Android vitals), which Google collects from phones whose owners allow it. We see only totals and anonymised crash traces. Reviews and ratings are public and belong to Google Play.

**What the forms say:**
- **Data safety:** "No data collected" and "No data shared". D1 stays on the phone, Google takes D2 and D3 directly, and D4–D6 happen outside the app.
- **Data deletion questions:** answered as "no data collected", with "Erase all progress" in the app.

---

## 9. Vocabulary

**Use exactly these words, in every screen, file, store text and doc.** The Hindi column is the starting wording; the fluent reviewer confirms it once, and it is then fixed.

| Use | Hindi | Meaning | Never use instead |
|---|---|---|---|
| file | फ़ाइल | The situation decided each day | card, case, event, mission, quest |
| option | विकल्प | One of the 2–3 ways to decide a file | answer, move, action |
| meter | (each by its name) | One of the four 0–100 measures | stat, score, health, bar |
| Development · Public Approval · Party Standing · Reputation | विकास · जनसमर्थन · पार्टी में साख · छवि | The four MLA meters | any other names for them |
| constituency fund | क्षेत्र निधि | The MLA level's in-game money | budget, wallet, coins, real scheme names. "Treasury" is the PM level's only |
| career | करियर | One playthrough from MLA upward | run, game, save, profile, account |
| level | स्तर | MLA, CM or PM: one step of the ladder | tier and rung (older docs only), stage, chapter |
| MLA · Chief Minister (CM) · Prime Minister (PM) | विधायक · मुख्यमंत्री · प्रधानमंत्री | The three levels | "Prime Minister of India", "CM of ‹real state›" as a title |
| term | कार्यकाल | The 48 days ending in an election | season, round |
| day | दिन | One decided file | turn |
| election · re-elected · defeated | चुनाव · फिर से चुने गए · हार | The term-end judgement | vote count, seats |
| crisis ending | (each ending has its own title) | A meter at its edge ends the career. Player-facing line: "Your career ends here." | death, die, killed, game over |
| warning | चेतावनी | A meter inside its warning zone | danger flash with no words |
| How it really works | असल में कैसे होता है | The explainer card's title | lesson, quiz, fact |
| source · checked on | स्रोत · जाँच की तारीख | The explainer's citation | — |
| Report a wrong fact | गलत तथ्य बताएं | The report button | report a bug, feedback (for this) |
| Your Party · Ruling Alliance · Opposition | आपकी पार्टी · सत्तारूढ़ गठबंधन · विपक्ष | The only party names | any invented or real party name or initials |
| the Assembly · the House · the Upper House · the Head of State · the Governor | सदन · उच्च सदन · राष्ट्राध्यक्ष · राज्यपाल. "The Assembly" and "the House" share सदन unless the reviewer finds a generic word that isn't an institution's official name | Generic institutions | see the never-use list below |
| scenario pack · office theme (v1.1) | परिदृश्य पैक · ऑफिस थीम | The things for sale | "unlock the next level", donation, support |

**Never use, anywhere, in English or Hindi:**
- **Institution names:**
  - Parliament (संसद), Lok Sabha (लोकसभा), Rajya Sabha (राज्यसभा);
  - Vidhan Sabha (विधानसभा), Vidhan Parishad (विधान परिषद);
  - Rashtrapati (राष्ट्रपति), Rashtrapati Bhavan, Raj Bhavan (राजभवन);
  - Supreme Court, High Court, Secretariat (सचिवालय).
- **Words that suggest government backing:** "Government of India", "Republic of India", "Union of India", "Official" (आधिकारिक), "Sarkari" (सरकारी), "Govt".
- **Real politics:** real people's or parties' names, initials, symbols or colours.
- **Religion, caste and community:** words for religions, castes or communities, as a choice or a label.
- **Purchase wording:** "donate", "help India", "support the nation", "for the country", "patriot", and anything that suggests buying helps the real country.
- **Ads:** "ad" and "watch to continue". There are no ads.
- **Store text:** "best", "#1", "No. 1".
- **The player in Hindi:** तुम or तू. Always use आप.

---

## 10. Open questions

These are genuinely undecided. Don't guess them in code: ask, then record the answer here.

1. **The election rule:** what wins re-election at the end of the MLA term, which is also what the goal panel says. Decide before writing the content, with the balance simulator.
2. **Endings:** which meter edges (four meters × two edges) end the MLA career, and how the 3–4 v1 crisis endings are shared among them.
3. **The fund:** does an empty constituency fund end the career, as the PM Treasury does? For now it only blocks costly options (rule 24).
4. **Hindi and the player's gender:** Hindi verbs agree with gender, and each list name implies one. Either each name carries a grammatical gender and the text has variants where needed, or every player-facing Hindi line is written in forms that suit anyone. Decide before the first file is written.
5. **People:** who writes the files, who checks the facts, and who is the fluent Hindi reviewer.
6. **Tuning values:** N, W and the starting values (§7.10), set by the balance simulator before the closed test.
7. **Measuring "D7" without analytics.** The stop rule and the go result use D7: the share of players who play on day 7. With no analytics SDK, Play Console doesn't report it. It reports installs, how many people still have the app installed after 7 and 30 days, and 30-day active users. Choose one:
   - use "still installed after 7 days" in its place, with new thresholds;
   - judge on installs alone;
   - accept an analytics tool, which would change the data table, the privacy promise and the children's-data position.
8. **The Play account's creation date.** If it was created after 13 Nov 2023, the 12-tester, 14-day closed test applies (assumed yes).
9. **The pack format (v1.1):** is a scenario pack its own short scenario, or extra files mixed into the career?
10. **Updates:** "user get update" was read as two things: promotion level by level, and new levels arriving as Play updates. Both are designed in. Confirm.

---

## 11. Accepted risks

Each of these is a decision, not an accident.

| # | Risk | Why it's accepted | Revisit when |
|---|---|---|---|
| K1 | **Pack piracy.** A modded app or a rooted phone can unlock packs without paying. A refunded pack stays open while the player stays offline | The fix is a server that checks purchases. It costs time, breaks offline play, and would receive purchase tokens and IP addresses from 13–17-year-olds, who are children under Indian law. People who pirate rarely pay anyway | Pack earnings can pay for a free-tier server plus advice on children's data, with the developer's yes |
| K2 | **Save editing.** Players can cheat by editing their own save | It only affects the cheater. There are no leaderboards and no shared economy, and nothing bought depends on the save | Leaderboards ever ship |
| K3 | **Children install or buy.** Under-13s can install despite the 13+ declaration, and 13–17-year-olds can buy with a parent's payment method | The app collects nothing, so there is no child data to protect. Google's family controls cover purchases, and Google handles refunds. An age gate would stop nobody | Any feature starts collecting data |
| K4 | **Slow content fixes.** A wrong or offending file stays live until an update passes review, usually within 7 days | Without a server or network there is no remote switch. That's the price of collecting nothing | A legal notice arrives. The update is the fix |
| K5 | **Children's data in support email.** From 13 May 2027, India's data rules want a parent's verifiable consent before a child's data is processed, and their exemptions don't cover support email | The law requires a grievance route. It is kept minimal: the under-18 line, using the email only to answer, and deleting it after 90 days | Earnings can pay for advice, or official guidance covers support channels |
| K6 | **No paid advice.** Grey areas stay grey: whether the developer is an "e-commerce entity", whether an offline game is an "online game", and the GST and income tax on payouts | The design avoids every grey area it can: generic names, no ads, no data. What's left is tiny at this size. Every payout statement is kept | Earnings can pay for an accountant or a lawyer, with the developer's yes, or a notice arrives |
| K7 | **No crash or analytics SDK.** Fewer details about crashes and play | Play Console's statistics, Android vitals and the testers cover v1. Collecting nothing is the design | Android vitals shows crashes we can't reproduce |
| K8 | **The developer's name, address and email are public.** The address is on the listing from v1.1, and the name shows as grievance officer from v1 | Play and India's e-commerce rules require them in order to sell. The developer accepted this | — |
| K9 | **One personal Play account.** A policy strike or a hijacked login stops everything | 2-step verification and careful content lower the risk | — |
| K10 | **A public repo.** Anyone can read the plan, the research, and later the code and the content | The developer chose to keep it public (2026-11-24) | — |
| K11 | **Generic institution names.** The CM and PM levels feel a little less real: "the House", not Lok Sabha | There is no budget for a legal check on the Emblems Act's grey area | Earnings can pay for advice, with the developer's yes |
| K12 | **No trademark registration.** Someone else could register "Desh Chalao" | Registration costs money. A free public search before launch catches existing marks | The game grows |

---

## 12. Success

**The three checks that say v1 worked,** one month after public launch (from I§7):

| Check | Passes when | How it's measured |
|---|---|---|
| **People come back** | At least 15% of installers still have the game 7 days after installing, and at least 7% after 30 days | Play Console → acquisition reports → retained installers (7 and 30 days). Note: this counts phones where the game is still installed, not people who played |
| **People finish a term** | At least 40% of closed-test players reach the first election. Then there are 25 or more public reviews averaging 4.2★ or more | The closed-test form asks each tester four things: the day their career ended (or that they reached the election), the file that felt most real, any file that felt unfair or biased, and the file they saw too often. Reviews are read in Play Console |
| **It stayed clean** | Zero policy warnings, and zero takedown or legal notices | The Play Console inbox and policy status; the game's email |

**The stop rule, word for word from the Business verdict** (I§ Business verdict §8):

> **Stop rule:**
> - **Users:** at **launch + 90 days**, if organic installs are **below 300 a month** and D7 is **below 4%** (the industry median, [GA] · SEEN), stop building new tiers.
>   - That is about May 2027 if you start in early December (ASSUMED).
>   - Leave the app live, since it costs ₹0 a month, as a portfolio piece, and move to your next idea.
> - **Money:** 60 days after the pack goes on sale, if fewer than **0.5% of new installs** buy it, make one change: drop to ₹49, the bottom of your range, or offer a different pack.
>   - If it is still below 0.5% after another 60 days, stop making paid packs and keep the game free.

**How its numbers are read:**
- **Organic installs:** Play Console's acquisition report, counting the sources Google Play search and explore.
- **Pack buyers:** pack orders in Play Console, divided by new installs over the same 60 days.
- **D7: no source exists yet** (§10 #7). Until that's decided, the users half of the stop rule can't fully be applied.

[GA]: https://gamedevreports.substack.com/p/gameanalytics-mobile-and-pc-game

---

## Change log

| Version | Date | What changed |
|---|---|---|
| 1.0 | 2026-11-24 | First version, built from IDEA.md v0.4 (including the Business verdict and the Hardening decisions), RESEARCH.md and COMPETITORS.md. It resolves the clash between "state list with search" and "no typing anywhere" with a letter index, and opens the D7-measurement question |
