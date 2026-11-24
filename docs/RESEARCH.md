# Desh Chalao: research on risks, legal and compliance, and store rejection

Date: 2026-11-23 · Product: [IDEA.md](IDEA.md) v0.1 · Competitors are the next step and are not covered here.

**Background document.** Since 2026-11-24, [PRD.md](PRD.md) is the source of truth; its compliance requirements (§8) were built from this research.

**How to read this**
- **I am not a lawyer.** ⚖️ marks an item where you need advice, with WHEN. ✅ marks standard practice that needs no advice.
- **Tiers:**
  - **T1:** the rule itself (law text, a regulator's text, the store's current policy page, official docs).
  - **T2:** a reputable summary (a law firm, an official explainer, the vendor's own blog).
  - **T3:** what people report.
  - **T4:** my memory, "from memory, not checked".
- **Verification:** a finding that changes the design needs T1 or T2. Anything resting only on T3/T4 is marked **UNVERIFIED**, with what would confirm it.
- **Sources:** every [S#] is a link. §4 lists each source's tier, its own date where shown, and the day I opened it (22 or 23 Nov 2026).
- **Facts this rests on** (from IDEA.md): you sell first in India (**ASSUMPTION**: IDEA §9 doesn't state it). The app is Android only, offline, with no accounts and no server, from a personal Play developer account (**FACT**).

---

## 0. What this research forces: the short list

**Distribution and data**
1. **Offer v1 in India only.**
   - GDPR reaches a developer outside the EU only when they offer goods or services to people in the EU ([S44] T1, Art. 3(2)).
   - AdMob's certified-consent requirement covers the EEA, UK and Switzerland ([S30] T1).
   - Restricting countries in Play Console keeps both out of scope. ✅
2. **v1 collects no personal data:** no ads, analytics, sign-in or purchases.
   - Play's Data safety form then says "no data collected", because data that never leaves the device isn't disclosed ([S9] T1).
   - A privacy policy is still required, both in Console and inside the app ([S8] T1). ✅

**Money**

3. **Selling publishes your address.** Accounts that "monetize via paid apps or in-app purchases must show their full address on Google Play". The address comes from your payments profile ([S20] T1).
   - On a personal account that is usually your home. Decide before v1.1 (IDEA D3).
4. **Under 18 is a child in Indian data law** ([S33] T1, DPDP Act s.2(f)).
   - Section 9(1) requires verifiable parental consent.
   - Section 9(3) bans "tracking or behavioural monitoring of children or targeted advertising directed at children".
   - These children's provisions apply from **13 May 2027** ([S35] T2).
   - Breaching the obligations on children can cost up to ₹200 crore ([S34] T2).
   - So ads with a 13+ audience need advice ⚖️ before any ad SDK goes in.

**Store listing and branding**

5. **Store title is 30 characters or fewer.** Also: no repetitive keywords, no celebrity names, no "Official" ([S6] T1, [S5] T1). "Desh Chalao: Run India for a Day" is 32 characters. ✅
6. **Emblems and Names Act 1950** ([S39] T1, text via an unofficial copy). Trade use of any of the following needs Central Government permission:
   - the national flag, the Ashoka Chakra, any government emblem or seal;
   - names that suggest government patronage;
   - the PM of India's or Rashtrapati's name or picture, and Raj Bhavan's;
   - the name or picture of Parliament, a State Legislature, the Supreme Court, a High Court, a secretariat or any government office building.

   That means fictional art, plus generic institution names in v1. ✅ to avoid; ⚖️ only if you want to use any of these.
7. **Government-information rule.** Name your sources in the store listing, say in the app and the listing that the app "doesn't represent a government", and complete Play's Government apps declaration ([S2] T1). ✅

**Selling, technical and content**

8. **Grievance contact.** Once you sell, show a grievance officer (you) with name, designation and email; acknowledge complaints within 48 hours and resolve them within a month ([S40] T1, copy).
   - The same screen covers the gaming Rules' grievance system ([S37] T2) and the DPDP point of contact ([S34] T2). ✅, with whether the rules apply to you as ⚖️.
9. **Technical gates in Milestone 0:**
   - target API 36 ([S22] T1);
   - 16 KB memory-page support in every native library ([S23] T1), which is **UNVERIFIED** for libGDX 1.14.2 ([S48] T1);
   - edge-to-edge insets ([S24] T1);
   - Billing Library 8 or later once purchases ship ([S25] T1). ✅
10. **Licences.** game-icons.net is CC BY 3.0, so it needs credit ([S53] T1). FreeType's FTL licence has a credit clause ([S50] T1). Never use NC, SA or AGPL material. ✅
11. **No party names.** The Election Commission delisted 334 registered parties in August 2025 alone ([S42] T2). The register holds thousands, and any invented name may be real. ✅
12. **Sensitive events.** The "Pandemic Year" pack and disaster files stay generic and educational. Never market around a real disaster ([S7] T1). ✅
13. **Dark patterns** banned in India: false urgency, confirm-shaming, nagging, trick questions, disguised ads, interface interference ([S41] T1, copy). ✅
14. **12 testers × 14 continuous days** before production access ([S1] T1). Recruit them now. ✅

**Bottom line:** I found nothing that stops the product. Three things stop specific variants (§1.3). With the recommended v1, **no legal advice is needed before the first user** (§2.13).

---

## 1. Risk register

**Scales:**
- Likelihood (L) and Damage (D) run 1–5; Score = L×D.
- **Class:** STOPS IT · COSTS · ROUTINE.
- **Design** says whether the risk changes IDEA.md.

### 1.1 Ranked

**Types:** A = adoption, L = legal/store, T = technical, D = dependency, O = operational.

| # | Risk | Type | L | D | Score | Class | Design | Source (tier) |
|---|---|---|---|---|---|---|---|---|
| A1 | No way to reach the first players; store search for the obvious keywords is crowded | Adoption | 5 | 5 | **25** | COSTS | yes | [S57] T1 data, [S1] T1 |
| L1 | Ad/SDK data from under-18s (DPDP s.9) if 13+ with ads | Legal | 4 | 5 | **20** | COSTS, and STOPS IT for personalised ads to under-18s | yes (D3) | [S33] T1, [S35] T2, [S34] T2, [S29] T1 |
| T5 | Content volume and accuracy: 3 tiers × ~200 sourced files × 2 languages | Technical | 5 | 4 | **20** | COSTS | yes (v1 = MLA tier) | T4, UNVERIFIED |
| T1 | Hindi renders wrong in libGDX's default font path | Technical | 4 | 4 | **16** | COSTS | yes (D1) | FACT (your spec) + T4, UNVERIFIED |
| T4 | Saves break when updates add tiers or change files | Technical | 4 | 4 | **16** | COSTS | yes | T4, UNVERIFIED |
| A2 | Closed-test gate: 12 testers × 14 continuous days | Adoption | 4 | 4 | **16** | COSTS | no | [S1] T1 |
| A3 | Churn once files start repeating | Adoption | 4 | 4 | **16** | COSTS | yes | T4, UNVERIFIED |
| T2 | Native libraries not 16 KB-aligned, so uploads get blocked | Technical | 3 | 5 | **15** | COSTS | yes (M0 gate) | [S23] T1, [S48] T1, [S49] T3; UNVERIFIED for 1.14.2 |
| D2 | Play's yearly technical deadlines (target API, Billing Library, 16 KB) | Dependency | 5 | 3 | **15** | ROUTINE | no | [S22] [S25] [S23] T1 |
| L2 | Selling publishes your full address on Play | Legal | 5 | 3 | **15** | COSTS | yes (v1 sells nothing) | [S20] T1 |
| O1 | Bias complaints and review-bombing from political players | Operational | 4 | 3 | **12** | COSTS | yes | [S42] T2; rest T4, UNVERIFIED |
| O2 | A wrong fact in a civic explainer | Operational | 3 | 4 | **12** | COSTS | yes | [S5] [S2] T1 |
| D3 | libGDX lags behind Android's requirements | Dependency | 3 | 4 | **12** | COSTS | no | [S47] [S48] T1 |
| A4 | Games set in Indian politics have stayed small | Adoption | 4 | 3 | **12** | COSTS | no | [S58] T1 data |
| A7 | Weak money in India: low ad yield, $100 payout threshold | Adoption | 4 | 3 | **12** | COSTS | yes (D3) | [S32] T1, [S59] T2 |
| L3 | Emblems and Names Act in the title, icon, art or names | Legal | 3 | 4 | **12** | ROUTINE once avoided | yes | [S39] T1 (copy) |
| L4 | Tax on Play earnings: GST registration, withholding tax, TCS | Legal | 5 | 2 | **10** | COSTS (a CA) | no | [S19] T1 |
| D1 | One store and one personal account, so a policy strike hurts | Dependency | 2 | 5 | **10** | ROUTINE | no | [S3] [S5] T1 |
| T3 | Target API 36 and edge-to-edge: UI drawn under the system bars | Technical | 3 | 3 | **9** | ROUTINE | yes (safe-area layout) | [S22] [S24] T1 |
| T6 | "Any state" content is wrong for some states | Technical | 3 | 3 | **9** | COSTS | yes (D2) | T4, UNVERIFIED |
| A5 | The political theme puts off some players and parents | Adoption | 3 | 3 | **9** | COSTS | no | T4 |
| D4 | AdMob, if used: policy strikes, invalid traffic, slow payouts | Dependency | 3 | 3 | **9** | COSTS | no | [S31] [S32] T1 |
| O3 | A legal notice, e.g. defamation or personality rights | Operational | 2 | 4 | **8** | COSTS | no (already no real people) | [S43] T2 |
| O7 | A real disaster or pandemic coincides with a file or pack | Operational | 2 | 4 | **8** | COSTS | yes (generic events) | [S7] T1 |
| T7 | Offline purchases get cracked | Technical | 4 | 2 | **8** | ROUTINE | no | T4 |
| T8 | Weak accessibility support in libGDX | Technical | 4 | 2 | **8** | ROUTINE | yes (text size, colour-safe) | T4, UNVERIFIED |
| T10 | Pending purchases mishandled | Technical | 2 | 3 | **6** | ROUTINE | yes (pending state) | [S26] T1 |
| O4 | Support and grievance timelines once selling (48 h / 1 month) | Operational | 3 | 2 | **6** | ROUTINE | yes (contact screen) | [S40] T1 (copy) |
| O6 | Every content fix needs a Play release, since there is no server | Operational | 3 | 2 | **6** | ROUTINE | no | T4 |
| A6 | Only English and Hindi, while "any state" invites everyone | Adoption | 3 | 2 | **6** | ROUTINE | no | T4 |
| D5 | Play service fees change | Dependency | 3 | 2 | **6** | ROUTINE | no | [S12] T1 |
| T9 | Low-RAM phones and text-texture memory | Technical | 2 | 3 | **6** | ROUTINE | no | T4 |
| D6 | Play Games Services, if used | Dependency | 2 | 2 | **4** | ROUTINE | no (on-device achievements first) | [S27] T1 |
| L5 | How India's online-gaming law classifies the app | Legal | 1 | 3 | **3** | ROUTINE | no | [S36] [S37] T2 |
| D7 | GitHub Pages rules for the privacy-policy site | Dependency | 1 | 2 | **2** | ROUTINE | no | [S56] T1 |
| D8 | Android developer verification | Dependency | 1 | 2 | **2** | ROUTINE | no | [S28] T1 |
| O5 | Server cost at scale | Operational | 1 | 1 | **1** | ROUTINE (there is no server) | no | T4 |

### 1.2 The risks that change the design

These are why the "Waiting for your yes" list in IDEA.md exists:
- A1, A3: the share card, the launch plan, and chains plus recurring events to keep files fresh;
- L1, A7, L2: Decision D3, and no money in v1;
- T5: v1 is the MLA tier only;
- T1: Decision D1;
- T4: save versioning;
- T2, T3: the M0 gates;
- O1: no party names, plus a neutrality checklist;
- O2: sources and a review list;
- L3: fictional art and generic names;
- T6: Decision D2;
- O7: generic events;
- T8: accessibility basics;
- T10: a pending purchase state;
- O4: the contact & grievance screen.

### 1.3 STOPS IT, but only for these variants, not the product

- **Personalised (targeted) ads to under-18 users in India**, once DPDP s.9(3) applies (13 May 2027, [S35] T2). There is no lawful way through ([S33] T1).
- **Real politicians, parties, party symbols or lookalikes.**
  - Play bans impersonation ([S3] T1) and professional images of public figures ([S4] T1).
  - Courts protect a star-politician's name, image and screen title ([S43] T2).
  - Your own rule already excludes all of this (**FACT**).
- **Scheduled names, emblems or buildings in trade use** without Central Government permission ([S39] T1, copy).

### 1.4 The top risks explained

**A1: no way to reach the first players** (25)
- **What it is:** nothing named so far reaches 100 players.
- **Why it applies to this app:**
  - On 22 Nov 2026, the India store search for "prime minister game" returned 8 of 12 results from two publishers ([S57] T1 data).
  - No audience or group has been named (IDEA §9, OPEN QUESTION).
- **What it forces:**
  - Answer IDEA's open question 1 before building past M1.
  - Plan the share card (now LATER) as the first growth feature after v1.

**L1: under-18s and ad data** (20). Detail in §2.5.
- **What it is:** the Mobile Ads SDK "automatically collects and shares IP address, user product interactions, diagnostic information, and device/account identifiers" ([S29] T1).
- **Why it applies:** a 13+ audience means 13–17-year-olds, and Indian law calls them children ([S33] T1).
- **What it forces:** IDEA D3. There are no ads in v1.

**T5: content volume** (20)
- **What it is:** each tier needs its own files, meters and explainers, and every file needs a source and a neutrality check in two languages.
- **Why it applies:** you chose three tiers in one app (**FACT**), with sourcing (**FACT**).
- **What it forces:** v1 is the MLA tier, with 40 files. The CSV pipeline and validator are built first (**FACT**, M0).
- **UNVERIFIED** (my estimate). The confirmation: time how long writing and sourcing the first 10 files takes.

**T1: Indic text** (16)
- **What it is:** Devanagari needs shaping (conjuncts, vowel signs placed before the consonant). Your spec says libGDX's FreeType path doesn't do it (**FACT** as your claim).
- **Why it applies:** Hindi is in v1 (**FACT**).
- **What it forces:** Decision D1. I found no T1 libGDX statement either way, so this is **UNVERIFIED**. The confirmation: the M0 spike rendering "प्रधानमंत्री", "क्षेत्र", "श्री", "संसद" (**FACT**, your test strings).
- A HarfBuzz library for libGDX does exist: Matn, Apache-2.0, which lists "complex script shaping" ([S55] T1).

**T4: saves across updates** (16)
- **What it is:** tiers arrive as updates (IDEA §1). Files get fixed, renamed or withdrawn.
- **What it forces:**
  - stable file IDs that never change meaning;
  - a version number in every save;
  - migration code with unit tests (**FACT**, already in your quality bar);
  - a "file withdrawn" path and a backup copy.
- **UNVERIFIED** (engineering judgement). The confirmation: the M1 migration tests.

**A2: the closed-test gate** (16)
- **What it is:** "Developers with personal accounts created after November 13, 2023, must run a closed test" with "a minimum of 12 testers who have been opted in continuously for at least 14 days". Review "usually takes seven days or less". "Insufficient tester engagement" means more testing ([S1] T1).
- **Why it applies:** your account is personal (**FACT**). Its creation date is an OPEN QUESTION; I assume it was after 13 Nov 2023.
- **What it forces:** recruit 12 people before M1 ends.

**T2: 16 KB memory pages** (15)
- **What it is:**
  - "All apps targeting Android 15 (API level 35) and higher must support 16 KB memory page sizes on 64-bit devices on Google Play."
  - "Starting February 1, 2027, if your app updates don't support 16 KB memory page sizes, you won't be able to release these updates" ([S23] T1, page updated 2026-11-04).
  - New apps must target API 36 already ([S22] T1).
- **Why it applies:** libGDX ships native libraries. Its pull request to build them for 16 KB pages was **closed**, with maintainers moving the work to gdx-jnigen ([S48] T1). A matching jnigen change appears in an issue index ([S49] T3, not opened). The 1.14.1/1.14.2 release post (28 May 2026) doesn't mention 16 KB ([S47] T1).
- **What it forces:** a Milestone 0 gate. Upload an internal-test build and read Play Console's 16 KB compatibility warning ([S23] shows it), or check every `.so` for 16 KB alignment.
  - Fallback: rebuild the natives with 16 KB alignment (free, needs the NDK).
  - Decision D1(a) also removes the FreeType native library from the list.
- **UNVERIFIED** for libGDX 1.14.2; the M0 check confirms it.

**L2: your address goes public when you sell** (15)
- **What it is:** "To comply with consumer protection laws, merchant accounts (developer accounts with apps that monetize via paid apps or in-app purchases) must show their full address on Google Play. The address used is the one taken from the Google payments profile" ([S20] T1).
- **Why it applies:** your account is personal (**FACT**), and the spec sells packs, themes and remove-ads (**FACT**).
- **What it forces:** v1 sells nothing. Before v1.1, choose: accept showing the address, or change the payments-profile address to one you can legally use. A paid business address would need your yes.

**O1: bias complaints** (12)
- **What it is:** players map fictional sides onto real parties and accuse the game of bias.
- **What it forces:**
  - no party names, colours or symbols. A name collision is likely: the EC delisted 334 registered unrecognised parties in Aug 2025 alone, so the register runs to thousands ([S42] T2);
  - a neutrality checklist for every file (**FACT**, your content review);
  - each option framed as a policy trade-off, never "the good side";
  - a "Report a wrong fact" path.
- The review-bombing risk itself is **UNVERIFIED** (T4).

**O2: a wrong civic fact** (12)
- **What it is:** Play bans "demonstrably deceptive or false content that may interfere with voting processes, or about the outcome of elections" ([S5] T1).
- **Why it applies:** a wrong explainer about elections could be read that way, and Play's government-information rule also requires sources ([S2] T1).
- **What it forces:** every explainer carries a source (**FACT**). Uncertain facts go to your review list (**FACT**). Corrections ship as updates (O6).

**L3: Emblems and Names Act** (12). Detail in §2.9.

---

## 2. Legal and compliance picture

### 2.0 Where this applies

**India.** The fact you haven't given me is where you sell first. I answer for **India (ASSUMPTION)**. That brings in:
- the DPDP Act 2023 and Rules 2025;
- the Consumer Protection Act 2019, the E-Commerce Rules 2020 and the Dark Patterns Guidelines 2023;
- the online gaming Act and Rules (2025/2026);
- the Emblems and Names Act 1950;
- Indian GST and income tax.

**Elsewhere, realistically.** Without a country restriction, the Indian diaspora (Gulf, UK, US, Canada) and curious players anywhere can install it.
- EU/UK: GDPR applies to processing the data of people "in the Union" when you offer them goods or services ([S44] T1).
- AdMob demands a certified consent platform for personalised ads there ([S30] T1).
- US: CCPA applies only to businesses with over $25 million revenue, data on 100,000+ Californians, or half their revenue from selling data ([S45] T1). It does not apply.
- US children's law (COPPA) applies to child-directed services (T4, from memory, not checked). It does not apply at 13+.

**What it forces:** set v1's availability to India only. Revisit before expanding. ✅

### 2.1 What personal data it touches, and what that triggers

| Build | Data touched | Who receives it | What it triggers |
|---|---|---|---|
| **v1** (no SDKs) | The career save, on the phone only | Nobody | Data safety: "User data accessed by your app that is only processed locally on the user's device and not sent off device does not need to be disclosed" ([S9] T1). A privacy policy is still required ([S8] T1). DPDP: you process nothing, so its duties shouldn't bite (ASSUMPTION, ⚖️ low priority). |
| **+ Contact by email** | The sender's email, any name given, the message | You | Say so in the privacy policy. Delete after resolving (ASSUMPTION: 90 days). From 13 May 2027, DPDP notice and erasure duties apply to this ([S35] T2). |
| **+ Purchases** (Play Billing) | Payment details, collected by Google. Purchase tokens checked on the device. | Google | No Data safety entry for payment data if "your app never accesses this information" and the payment service collects it directly ([S9] T1). Your address becomes public ([S20] T1). GST/TCS (§2.10). |
| **+ Ads** (AdMob) | IP address, product interactions, diagnostics, device/account IDs, collected **and shared** automatically ([S29] T1, SDK 25.5.0) | Google and ad partners | Declare them in Data safety; the AD_ID permission ([S16] T1); DPDP for under-18s (§2.5); a certified consent platform if ads are served in the EEA/UK ([S30] T1) |
| **+ Play Games Services** | Gamer identity (gamertag, avatar), analytics, diagnostics; plus, depending on use, achievements, scores, "engagement and spend statistics", saved games ([S27] T1) | Google | Declare them per Google's page. Players delete via their Play Games profile ([S27] T1). |

**What it forces:** v1 = the first row. Each later row is a separate decision with a known cost.

### 2.2 Consent: what to ask, when, and how it's recorded

**v1 asks for nothing,** because nothing is collected. There is no sign-up and there are no forms. ✅

**The only "form" is Contact / Report a wrong fact,** which opens the player's own email app. Above the button, one line says why and who receives it — **ASSUMPTION** (DPDP notice principle, [S34] T2): "Opens your email app. Your message goes only to the developer, to answer you, and is deleted after 90 days."

**Marketing:** none. If a newsletter is ever added, it is a separate checkbox, never pre-ticked (**FACT**, your rule).

**If ads come later:**
- **India:** a DPDP notice and consent before processing. For under-18s that means verifiable parental consent ([S33] T1), which an anonymous offline game can't practically get — hence D3. ⚖️
- **EEA/UK:** Google's UMP certified consent platform ([S30] T1). Not applicable if India-only.
- **Recording consent:** the consent platform stores the consent string on the device. You keep no server copy (ASSUMPTION).

### 2.3 SDKs and tracking

| SDK | Collects without being asked | Links data across apps/sites for ads? | What it forces |
|---|---|---|---|
| libGDX core | Nothing (T4) | No | Nothing |
| Play Billing | Payment data, held by Google ([S9] T1) | No | Handle pending purchases (`enablePendingPurchases`, [S26] T1). Billing Library version 8 or later (v7 deadline was 31 Aug 2026; v8's is 31 Aug 2027, [S25] T1). |
| Google Mobile Ads (AdMob) | IP, interactions, diagnostics, device IDs ([S29] T1) | **Yes**: cross-app advertising | Android: the `AD_ID` permission is merged in by the SDK ([S16] T1). Use App Set ID for any non-ad purpose ([S16] T1). iOS would need Apple's App Tracking Transparency prompt (T4, not applicable: no iOS). India: no targeted ads to under-18s ([S33] T1). |
| Play Games Services | Gamer identity, analytics, diagnostics ([S27] T1) | No (Google's own) | Data safety entries. Keep achievements on the device for now. |
| Analytics (Firebase etc.) | — | — | **None planned.** Use Play Console's own statistics instead (IDEA §7). |

### 2.4 Data retention and deletion

- **Career save:** on the device. Settings → "Erase all progress" with a confirmation. Uninstalling removes it (T4). ✅
- **Support emails:** delete 90 days after the issue is resolved (ASSUMPTION; state it in the privacy policy). ✅
- **Account deletion:** Play requires it only "if your app allows users to create an account" ([S10] T1). This app has no accounts, so it is **not applicable**. Apple's equivalent rule is not applicable either (no iOS).
- **Even without accounts,** "all developers must complete new Data deletion questions in the Data safety form" ([S10] T1). ✅

### 2.5 Age

**The conflict:**
- Play's family rules treat children as **under 13**. Families rules, including family-certified ad SDKs only, apply when the target audience includes children ([S15] T1, [S14] T1). Your 13+ target avoids them (**FACT**).
- India's DPDP treats a child as **under 18** ("an individual who has not completed the age of eighteen years", [S33] T1). For a child's data it requires:
  - "verifiable consent of the parent" before processing (s.9(1));
  - no processing "likely to cause any detrimental effect on the well-being of a child" (s.9(2));
  - no "tracking or behavioural monitoring of children or targeted advertising directed at children" (s.9(3)).
- These apply from **13 May 2027** ([S35] T2). The penalty for breaching the obligations on children is up to ₹200 crore ([S34] T2).
- The PIB explainer mentions exemptions for essential services such as "healthcare, education or real-time safety" ([S34] T2). An entertainment game with explainers is unlikely to fit (ASSUMPTION ⚖️).

**What it forces:**
- **v1:** no data, so no age gate is needed (ASSUMPTION).
- **Before any ad or analytics SDK:** decide D3 ⚖️.
  - (a) 13+ with no ad SDK;
  - (b) an 18+ target audience. Play lets you pick "users only over the age of 18" and "specify additional restrictions to your app availability" ([S15] T1). I found no DPDP safe harbour for minors who play anyway (T4, ⚖️);
  - (c) 13+ with ads plus verifiable parental consent: impractical for an anonymous offline game.
- **Art direction must not look like a children's game,** so the declared 13+ stays credible ([S15] T1: declare the audience accurately). ✅
- **Content rating:** answer the IARC questionnaire accurately and update it whenever content changes, including new tiers and packs ([S18] T1). ✅

### 2.6 User content and moderation

- **v1 has no user content:** no chat, posts, uploads or profiles. Moderation duties and Apple's four requirements (filter, report, block, contact) do **not apply**.
- **India's intermediary rules (IT Rules 2021)** cover platforms that host third parties' content (T4, from memory, not checked). They do **not apply**.
- **Watch-out for later:** the share card. If players could type their own names or party names onto a shareable image, the game would print "PM <real name>" report cards.
  - **What it forces:** names come from a curated list and no free text appears on share images. **ASSUMPTION**, cheap.

### 2.7 Money

- **Payment rules:**
  - Digital goods sold in a Play app must use Google Play's billing system ([S11] T1). Stripe or UPI links for packs are not allowed.
  - Alternative billing exists only through enrolled programs in eligible regions ([S11] T1), which isn't worth it here.
  - Randomised items need odds disclosed ([S11] T1). There are no loot boxes (**FACT**), so this does not apply.
- **Fees:** for India, 15% on the first $1M a year for developers enrolled in the 15% tier, and 30% above that ([S12] T1, "until the announced updated service fees are rolled out globally"). **Enrol in the 15% tier** (free). ✅
- **Refunds:** "Google may give refunds for some purchases made through Google Play's billing system" under Google's policies ([S13] T1). You can also refund from Play Console (T4). One line in your Terms points to Google Play's refund policy. ✅
- **Subscriptions and auto-renew:** none planned, so **not applicable**.
- **Rewarded ads** (later):
  - Must be explicitly opt-in ([S17] T1).
  - "Must not include any text or icons, other than to describe the reward(s) offered, to mislead or incentivize users towards a particular choice (such as by indicating 'watch this ad to support our business')", and must deliver the reward ([S31] T1).
  - This matches your rule never to word anything as helping the country (**FACT**).
  - No ad may appear before the splash screen ([S17] T1).
- **Dark patterns** (India): the Guidelines "apply to (i) all platforms, systematically offering goods or services in India; (ii) advertisers; (iii) sellers" ([S41] T1, copy). For the Store and ad offers that means:
  - no fake countdowns (false urgency);
  - no "No thanks, I don't care about India" buttons (confirm shaming);
  - no repeated pop-ups (nagging);
  - no greyed-out "No" (interface interference);
  - no double negatives (trick question);
  - no ads disguised as files (disguised advertisement);
  - the full price shown up front (drip pricing). ✅
- **Spec gap:** "Remove ads ₹99" removes nothing while the only ads are opt-in rewarded ones. Selling it as-is would be misleading. **ASSUMPTION**: drop it, or define what it buys.

### 2.8 Sector-specific rules

**Politics and civics**
- **Play's misleading-claims policy** ([S5] T1):
  - bans "false content about elections" and "false claims of affiliation with governments";
  - "you cannot use 'Official' in a title without the necessary rights."
- **Play's government-information rule** ([S2] T1):
  - "Include easy-to-see information sources in your app's description and store listing page";
  - "Make it clear that the app doesn't represent a government or political entity";
  - complete the Government apps declaration in Play Console (Policy and programs → App content).
- **Impersonation:** "Don't imply that your app is related to or authorized by someone that it isn't" ([S3] T1).
- **Personality rights:** the Madras High Court restrained commercial use of a star-politician's name, image, initials and screen title ([S43] T2).
- **What it forces:**
  - a welcome/disclaimer screen and an About line;
  - sources in the store description;
  - no real people or lookalikes (**FACT**);
  - no party names (O1). ✅

**Elections law**
- The Model Code of Conduct and the RPA 1951 s.126 silence period cover parties, candidates and "election matter" meant to sway a real election (T4, from memory, not checked).
- A fictional election with fictional parties is not that. **Changes nothing.** UNVERIFIED; confirm only if a real election is ever referenced.

**India's online gaming law**
- The 2025 Act separates banned online money games ("financial stakes are involved") from online social games: "casual games… primarily skill-based and designed for entertainment, learning, or social interaction" ([S36] T2).
- The Rules have been in force since 1 May 2026. Registration is "required only when notified by the Central Government", and "every online game service provider must establish and maintain a functional grievance redressal system" ([S37] T2).
- **Not opened:** the Act text on India Code ([S38] T1) was unreachable from my connection.
- **What it forces:** nothing beyond the contact & grievance screen. Whether an offline game even counts as an "online game" is ⚖️ low priority (§2.13).

**Education**
- There is no licensing regulator for a consumer game with explainers (T4).
- The obligations are accuracy ([S2], [S5] T1) and the age rules in §2.5.

**Health**
- Health-ministry files must not present medical misinformation as fact. That is from memory, not checked against Play's health policy (**UNVERIFIED**, T4).
- **What it forces:** options are policy choices, never false science. ✅

**Finance**
- The in-game Treasury isn't money (**FACT**).
- Nothing purchasable changes the numbers (**FACT**).
- No real-money play (**FACT**).

**Maps**
- No map (**FACT**). India penalises maps that question its territorial integrity (Criminal Law (Amendment) Act 1961 s.2; T4, from memory, not checked).
- **Changes nothing:** the state picker stays a list.

**Sensitive events**
- "We don't allow apps that capitalize on or are insensitive toward a sensitive event… such as civil emergencies, natural disasters, public health emergencies, conflicts… Apps with content related to a sensitive event are generally allowed if that content has EDSA (Educational, Documentary, Scientific, or Artistic) value" ([S7] T1).
- **What it forces:**
  - flood, cyclone and pandemic files stay generic and educational;
  - nothing references a real event (**FACT**);
  - pause marketing during a real disaster. ✅

### 2.9 Names, emblems and buildings: the Emblems and Names Act 1950

**Section 3:** "no person shall… use… for the purpose of any trade, business, calling or profession, or in the title of any patent, or in any trade mark or design, any name or emblem specified in the Schedule or, any colorable imitation thereof without the previous permission of the Central Government" ([S39] T1). I read the text on an unofficial copy (advocatekhoj) because India Code was unreachable; confirm it on [S38]'s site.

**Schedule entries that touch this game** ([S39] T1):

| Item | Text (abridged) | What it means here |
|---|---|---|
| 3 | "The Indian National Flag" | No flag in the icon, store art, UI or game art. |
| 4 | "The name, emblem or official seal of the Government of India or of any State…" | No national or state emblem. No "Government of X" as a name. |
| 6 | "The name, emblem or official seal of the President, Governor… or Republic or Union of India" | Avoid "Republic of India" or "Union of India" in the title or branding. |
| 7 | "Any name, which may suggest… the patronage of the Government of India or the Government of a State" | No "Sarkari", "Official" or "Govt" in the title. |
| 9 | "The name or pictorial representation of Rashtrapati, Rashtrapati Bhavan, Raj Bhavan" | No drawings of either building. In-game names wait for advice. |
| 9-A | "…pictorial representation of… the Prime Minister of India…" | No real PM's likeness; avoid "Prime Minister of India" in the title. |
| 16 | "…the pictorial representation of Ashoka Chakra…" | No chakra in the icon or art. |
| 17 | "The name of the Parliament or the Legislature of any State, or the Supreme Court, or the High Court… Central Secretariat… Secretariat of any State Government or any other Government Office or the pictorial representation of any building occupied by any of the aforesaid institutions" | No drawings of Parliament House, assemblies, courts or secretariats. Never in the title, icon, purchase names or packs. |

**The open point** ⚖️: whether naming these institutions *inside game text* is "use for the purpose of any trade".
- Commercial books and games do name them. The Indian Election Game listing describes building "a Lok Sabha majority", per its BlueStacks description, read 22 Nov 2026 (T3).
- **What it forces:**
  - v1 text uses generic terms such as "the Assembly", "the Governor" and "the House";
  - get advice before the CM/PM tiers ship, if they need "Parliament", "Lok Sabha", "Rashtrapati" and the like (§2.13);
  - all buildings in the art are fictional. ✅

### 2.10 Selling in India

**Who is the seller**
- **You.** The Distribution Agreement says "You hereby appoint Google as Your agent or marketplace service provider… to make Your Products available in Google Play", and "Products are displayed to users at prices You establish" ([S21] T1).
- Your developer name shows as the seller (T4).

**What contact the store and law require**
- An email address is required and is shown on your listing. A phone number and website are optional ([S20] T1).
- Your full address is shown once you monetize ([S20] T1).

**Grievance route**
- The E-Commerce Rules 2020 define "platform" to include "applications including mobile applications". Every "e-commerce entity" must ([S40] T1, copy):
  - "appoint a grievance officer… and shall display the name, contact details, and designation of such officer on its platform";
  - acknowledge complaints "within forty-eight hours" and redress them "within one month".
- An e-commerce entity excludes "a seller offering his goods or services for sale on a marketplace e-commerce entity". Whether selling through Google Play makes you an e-commerce entity is ⚖️, once the app takes money.
- Complying costs nothing: a Contact & grievance screen naming you, with the timelines.
- The same screen covers the gaming Rules' grievance duty ([S37] T2) and the DPDP "point of contact" ([S34] T2). ✅

**Invoice and tax**
- Google Play: "If you're located in India, it is your responsibility to determine whether you need to obtain a Goods and Services Tax Identification Number (GSTIN) and to determine any applicable tax… Google as a marketplace intermediary service provider, is also responsible for deducting and depositing appropriate withholding tax and GST TCS (Tax Collection at Source), if any… sold by you" ([S19] T1).
- So you are the GST supplier. Google takes TDS/TCS out of your payouts, and buyers get Google Play's receipts (T4).
- ⚖️ A chartered accountant (not a lawyer), before the first payout:
  - whether to register for GST;
  - how to claim the TDS/TCS credit;
  - how Play income is taxed.

**Consumer and e-commerce rules that apply**
- The Consumer Protection Act 2019 (T4);
- the E-Commerce Rules 2020 ([S40] T1, copy);
- the Dark Patterns Guidelines 2023 ([S41] T1, copy; §2.7).

### 2.11 Licences

| Dependency or asset | Licence | What you must do | Source |
|---|---|---|---|
| libGDX | Apache-2.0 | Keep the licence and NOTICE text in Credits | [S46] T1 |
| FreeType (via gdx-freetype; not needed if D1(a)) | FTL, "a BSD-style license with a credit clause" (or GPLv2; **choose FTL**) | Credit line in Credits | [S50] T1 |
| Matn + HarfBuzz (only if D1(b)) | Apache-2.0 (Matn) | Licence text in Credits | [S55] T1 |
| Noto Sans Devanagari, Noto Sans | SIL OFL-1.1 | Embedding is fine. Ship the OFL text and don't sell the font alone. | [S51] T1 |
| Kenney assets | CC0 | Nothing required (a credit is courteous) | [S52] T1 |
| game-icons.net | **CC BY 3.0**: "use them freely as long as you credit the original author" | Credit each author used: "Icons made by {author}. Available on https://game-icons.net". This corrects your spec's "CC0". | [S53] T1 |
| jsfxr | Unlicense (public domain) | Nothing required. Sounds you generate are yours (T4). | [S54] T1 |
| Google SDKs (Billing, Ads, Play Games) | Google's own terms | Accept the terms; nothing to ship | T4 |

**Traps** ✅:
- AGPL or GPL code would force your source open. None is in the plan.
- CC BY-**NC** assets forbid commercial use, which matters once you sell.
- CC BY-**SA** assets force your derivative art to share alike.
- AI-generated art has unclear rights. Not planned (ASSUMPTION).

### 2.12 The pages the stores and the law expect

| Page | Needed? | What must be in it | Source |
|---|---|---|---|
| **Privacy policy** at a public URL and inside the app | **Yes, from v1.** "All apps must post a privacy policy link in the designated field within Play Console, and a privacy policy link or text within the app itself." | **v1 contents** (✅): who you are and your contact email; that the app collects no personal data and the career save stays on the device; support emails (what is kept, why, deletion after 90 days); no third-party SDKs; children (13+, no data); a grievance contact; the effective date and how changes are announced. **Later:** add AdMob, Billing and Play Games sections. | [S8] T1 |
| **Hosting** | GitHub Pages is fine for a policy page. It is "not intended for… e-commerce" or SaaS. | — | [S56] T1 |
| **Terms / EULA** | Not required by Play for this app (T4). **Recommended** ✅. | Fiction disclaimer; no government affiliation; licence to use; purchases via Google Play and its refund policy; content accuracy and "report a wrong fact"; Indian law and courts; contact. | T4 |
| **Refund terms** | **No separate page.** In-app purchases follow Google Play's refund policies. | One line in Terms | [S13] T1 |
| **Cookie policy and consent** | **No.** A GitHub Pages policy page with no analytics or embeds sets no non-essential cookies (T4). The app opens links in the browser, not an in-app web view. | — | T4 |
| **Contact & grievance** | Needed once selling, and from 13 May 2027 for any personal data such as support emails. Add it in v1, since it's free. | Your name, designation "Grievance Officer", email, 48-hour acknowledgement and one-month resolution | [S40] T1 (copy), [S34] [S37] T2 |
| **Account deletion web link** | **Not applicable** (no accounts) | — | [S10] T1 |
| **Government-information disclosures** | **Yes** | Sources in the store description; "does not represent a government or political entity" in the listing and the app; the Play Console declaration | [S2] T1 |
| **app-ads.txt** | Only if ads are added | — | T4 |

### 2.13 Advice versus standard practice, and when

| Item | Type | WHEN |
|---|---|---|
| Privacy policy, Terms, disclaimers, credits, Data safety answers, IARC answers, India-only availability, no emblems/flag/buildings, no real people or parties, Play Billing for digital goods, government-information disclosures | ✅ Standard practice | Before the first user |
| Naming Parliament, State Legislatures, Rashtrapati or Raj Bhavan *inside game text* | ⚖️ Lawyer | Before the CM/PM tiers ship. Not needed for v1 if v1 uses generic terms. |
| Any ad or analytics SDK with a 13+ audience (DPDP s.9), including whether an 18+ audience setting is enough | ⚖️ Lawyer | Before adding the SDK, and in any case before 13 May 2027 |
| GST registration, TDS/TCS credits, income tax on Play payouts | ⚖️ Chartered accountant | Before the first payout, i.e. once the app takes money |
| Whether the E-Commerce Rules treat you as an "e-commerce entity" | ⚖️ Lawyer | Once the app takes money. Comply cheaply anyway. |
| Whether an offline game is an "online game" under the 2025 gaming Act | ⚖️ | Only if online features are added or the app grows |
| Trademark on "Desh Chalao" | Public search ✅ before launch; registration ⚖️ | Registration once it grows |
| A legal notice from a party, person or authority | ⚖️ | Only if one arrives |

**Launch cost of advice: ₹0** if v1 follows IDEA §8 (no SDKs, generic institution names, nothing sold). Advice that can wait is not a launch cost.

### 2.14 Not applicable, and why

- **Apple's rules** (App Tracking Transparency, sign-up account deletion, the four content rules, In-App Purchase): there is no iOS (**FACT**). Revisit if iOS ships.
- **Moderation:** there is no user content.
- **Account deletion:** there are no accounts ([S10] T1).
- **Subscription disclosures:** there are no subscriptions.
- **Loot-box odds:** there are no loot boxes ([S11] T1).
- **COPPA:** the app isn't child-directed, and v1 is India-only (T4).
- **CCPA:** it falls below every threshold ([S45] T1).
- **GDPR and AdMob's EU consent platform:** v1 is India-only ([S44] [S30] T1).
- **The EU Digital Services Act "trader" listing:** EU only (T4).
- **India's IT Rules 2021 intermediary duties:** there is no third-party content (T4).
- **Election silence and the Model Code of Conduct:** the elections are fictional (T4).
- **Cookie consent:** no non-essential cookies are set (T4).

---

## 3. What would get this rejected or pulled (most likely first)

| # | Rejection or removal reason | Why it applies to this app | What to do | Source |
|---|---|---|---|---|
| 1 | **Production access refused after the closed test**: "fewer than 12 opted-in testers or insufficient tester engagement" | Personal account, no tester group named yet | Recruit 12 daily testers. Ship a build they want to open for 14 days in a row. | [S1] T1 |
| 2 | **Store-listing metadata**: title over 30 characters; "repetitive or unrelated keywords"; emojis or ALL CAPS; ranking, price or promo text in the title or icon; "a celebrity's name" | "Desh Chalao: Run India for a Day" is 32 characters. The spec lists five keywords, which would read as keyword stuffing if pasted as a list. | Title "Desh Chalao: MLA to PM". Weave the keywords into normal sentences. No "best" or "#1". | [S6] T1 |
| 3 | **Government-information disclosures missing** | Explainers describe real institutions | Sources in the description; a "does not represent a government" line in the listing and the app; the declaration in Play Console | [S2] T1 |
| 4 | **Misleading claims**: implied government affiliation, "Official", false election content | A flag, chakra or Parliament in the icon or screenshots signals affiliation. A wrong explainer about voting. | Fictional art; sourced explainers; never "official" | [S5] T1, [S39] T1 |
| 5 | **Privacy policy missing in the app or unreachable; Data safety doesn't match the SDKs** | Easy to forget when "we collect nothing". Easy to break later by adding AdMob without updating the form. | A policy link in About plus Console; re-answer Data safety with every SDK change | [S8] [S9] T1 |
| 6 | **Upload blocked**: target API below 36, natives not 16 KB-ready, outdated Billing Library | libGDX ships native libraries ([S48]). Billing versions expire yearly. | The M0 gates in §0, item 9 | [S22] [S23] [S25] T1 |
| 7 | **Impersonation or IP complaint** | A lookalike politician, a film title, a party symbol or colours | No real people, parties, symbols or titles (**FACT**) | [S3] [S4] T1, [S43] T2 |
| 8 | **Sensitive events** | The Pandemic Year pack and disaster files | Generic and educational; nothing tied to a real event; no marketing during real disasters | [S7] T1 |
| 9 | **Target audience or content rating wrong** | Cartoonish art could "appeal to children" while you declare 13+. New tiers or packs change the content. | Declare accurately; art not childlike; update IARC with each content change | [S15] [S18] T1 |
| 10 | **Ads policy** (once ads exist) | Reward text that nudges ("support us", "help the nation"); an ad before the splash; a reward not delivered | Neutral reward text; ads only on opt-in; always deliver | [S17] [S31] T1 |
| 11 | **Account-level problems** | An unreachable contact email, or an unverified identity or address | Keep the public email monitored | [S20] T1 |
| 12 | **Broken on the reviewer's phone** (crash, blank text, UI under the system bars) | Edge-to-edge is enforced on Android 15+ ([S24]). The custom text renderer is a new code path. | Test on Android 15/16 and a 2–3 GB phone before every release | [S24] T1; minimum-functionality policy not opened (T4, UNVERIFIED) |

---

## 4. Sources

Tier key as at the top. "Checked" is the day I opened the source. "Doc date" is the date the source itself shows, where it shows one. "Copy" means the law text read on an unofficial copy because the official site was unreachable from my connection; confirm it on the official site.

| ID | Source | Tier | Doc date | Checked |
|---|---|---|---|---|
| [S1] | [Play: App testing requirements for new personal developer accounts](https://support.google.com/googleplay/android-developer/answer/14151465) | T1 | current | 2026-11-22 |
| [S2] | [Play: Requirements for apps that communicate government information](https://support.google.com/googleplay/android-developer/answer/9514050) | T1 | current | 2026-11-22 |
| [S3] | [Play: Impersonation](https://support.google.com/googleplay/android-developer/answer/9888374) | T1 | current | 2026-11-22 |
| [S4] | [Play: Intellectual Property](https://support.google.com/googleplay/android-developer/answer/9888072) | T1 | current | 2026-11-22 |
| [S5] | [Play: Deceptive Behavior (Misleading Claims)](https://support.google.com/googleplay/android-developer/answer/9888077) | T1 | current | 2026-11-23 |
| [S6] | [Play: Metadata](https://support.google.com/googleplay/android-developer/answer/9898842) | T1 | current | 2026-11-23 |
| [S7] | [Play: Inappropriate Content (Sensitive Events)](https://support.google.com/googleplay/android-developer/answer/9878810) | T1 | current | 2026-11-23 |
| [S8] | [Play: User Data](https://support.google.com/googleplay/android-developer/answer/10144311) | T1 | current | 2026-11-23 |
| [S9] | [Play: Data safety section](https://support.google.com/googleplay/android-developer/answer/10787469) | T1 | current | 2026-11-23 |
| [S10] | [Play: Account deletion requirements](https://support.google.com/googleplay/android-developer/answer/13327111) | T1 | current | 2026-11-23 |
| [S11] | [Play: Payments](https://support.google.com/googleplay/android-developer/answer/9858738) | T1 | current | 2026-11-23 |
| [S12] | [Play: Service fees](https://support.google.com/googleplay/android-developer/answer/112622) | T1 | current | 2026-11-23 |
| [S13] | [Google Play Help: Refund policies](https://support.google.com/googleplay/answer/2479637) | T1 | current | 2026-11-23 |
| [S14] | [Play: Families policies](https://support.google.com/googleplay/android-developer/answer/9893335) | T1 | current | 2026-11-23 |
| [S15] | [Play: Target audience and app content](https://support.google.com/googleplay/android-developer/answer/9867159) | T1 | current | 2026-11-23 |
| [S16] | [Play: Advertising ID](https://support.google.com/googleplay/android-developer/answer/6048248) | T1 | current | 2026-11-23 |
| [S17] | [Play: Ads](https://support.google.com/googleplay/android-developer/answer/9857753) | T1 | current | 2026-11-23 |
| [S18] | [Play: Content ratings](https://support.google.com/googleplay/android-developer/answer/9898843) | T1 | current | 2026-11-23 |
| [S19] | [Play: Tax rates and VAT (India section)](https://support.google.com/googleplay/android-developer/answer/138000) | T1 | current | 2026-11-23 |
| [S20] | [Play: Developer account information (contact details, legal address)](https://support.google.com/googleplay/android-developer/answer/13634081) | T1 | current | 2026-11-23 |
| [S21] | [Google Play Developer Distribution Agreement](https://play.google/developer-distribution-agreement.html) | T1 | current | 2026-11-23 |
| [S22] | [Play: Target API level requirements](https://support.google.com/googleplay/android-developer/answer/11926878) | T1 | current | 2026-11-23 |
| [S23] | [Android: Support 16 KB page sizes](https://developer.android.com/guide/practices/page-sizes) | T1 | updated 2026-11-04 | 2026-11-23 |
| [S24] | [Android: Edge-to-edge in views](https://developer.android.com/develop/ui/views/layout/edge-to-edge) | T1 | current | 2026-11-23 |
| [S25] | [Android: Play Billing Library version deprecation](https://developer.android.com/google/play/billing/deprecation-faq) | T1 | current | 2026-11-23 |
| [S26] | [Android: Integrate the Play Billing Library (pending purchases)](https://developer.android.com/google/play/billing/integrate) | T1 | current | 2026-11-23 |
| [S27] | [Android: Play Games Services data disclosure](https://developer.android.com/games/pgs/data-collection) | T1 | current | 2026-11-23 |
| [S28] | [Android developer verification](https://developer.android.com/developer-verification) | T1 | current | 2026-11-23 |
| [S29] | [AdMob: Google Play data disclosure (Mobile Ads SDK 25.5.0)](https://developers.google.com/admob/android/privacy/play-data-disclosure) | T1 | current | 2026-11-23 |
| [S30] | [AdMob: Consent requirements for EEA, UK, Switzerland](https://support.google.com/admob/answer/13554116) | T1 | in force 16 Jan 2024 | 2026-11-23 |
| [S31] | [AdMob: Policies for rewarded ad units](https://support.google.com/admob/answer/7313578) | T1 | current | 2026-11-23 |
| [S32] | [AdMob: Payment thresholds](https://support.google.com/admob/answer/2772208) | T1 | current | 2026-11-23 |
| [S33] | [Digital Personal Data Protection Act 2023, Gazette of India](https://egazette.gov.in/WriteReadData/2023/248045.pdf) | T1 | Act 22 of 2023 | 2026-11-23 |
| [S34] | [PIB explainer: DPDP Rules 2025](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/nov/doc20251117695301.pdf) | T2 (official summary) | Nov 2025 | 2026-11-23 |
| [S35] | [AZB & Partners: DPDP framework comes into effect](https://www.azbpartners.com/bank/update-indias-digital-personal-data-protection-framework-comes-into-effect/) | T2 | 19 Nov 2025 | 2026-11-23 |
| [S36] | [PIB explainer: Online Gaming Bill 2025](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/aug/doc2025821618101.pdf) | T2 (official summary) | 21 Aug 2025 | 2026-11-23 |
| [S37] | [PIB backgrounder: Online Gaming Rules 2026](https://static.pib.gov.in/WriteReadData/specificdocs/documents/2026/apr/doc2026430859401.pdf) | T2 (official summary) | 30 Apr 2026 | 2026-11-22 |
| [S38] | [Promotion and Regulation of Online Gaming Act 2025, India Code](https://www.indiacode.nic.in/bitstream/123456789/22148/1/a2025-32.pdf) | T1 | Aug 2025 | **not opened**: unreachable from my connection |
| [S39] | Emblems and Names (Prevention of Improper Use) Act 1950: [Section 3](https://www.advocatekhoj.com/library/bareacts/emblemsandnames/3.php) and [Schedule](https://www.advocatekhoj.com/library/bareacts/emblemsandnames/schedule.php) | T1 (copy; [India Code](https://www.indiacode.nic.in/handle/123456789/1896) unreachable) | 1950, as amended | 2026-11-22 and 2026-11-23 |
| [S40] | [Consumer Protection (E-Commerce) Rules 2020, Gazette text](https://taxguru.in/wp-content/uploads/2020/07/Consumer-Protection-E-Commerce-Rules-2020.pdf) | T1 (copy) | Jul 2020 | 2026-11-23 |
| [S41] | [Guidelines for Prevention and Regulation of Dark Patterns 2023](https://taxguru.in/?p=896142) | T1 (copy) | 30 Nov 2023 | 2026-11-23 |
| [S42] | [All India Radio: EC delists 334 registered unrecognised parties](https://www.newsonair.gov.in/election-commission-delists-334-registered-unrecognised-political-parties) | T2 | 10 Aug 2025 | 2026-11-23 |
| [S43] | [The News Minute: Madras HC interim relief to Kamal Haasan (personality rights)](https://www.thenewsminute.com/tamil-nadu/madras-hc-grants-interim-relief-to-kamal-haasan-in-personality-rights-case) | T2 | Jan 2026 (per reports) | 2026-11-22 |
| [S44] | [GDPR (EUR-Lex), Art. 3 territorial scope](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679) | T1 | 2016/679 | 2026-11-23 |
| [S45] | [California AG: CCPA](https://oag.ca.gov/privacy/ccpa) | T1 | current | 2026-11-23 |
| [S46] | [libGDX repository (Apache-2.0)](https://github.com/libgdx/libgdx) | T1 | current | 2026-11-23 |
| [S47] | [libGDX releases (1.14.2 latest)](https://github.com/libgdx/libgdx/releases), [1.14.1 & 1.14.2 post](https://libgdx.com/news/2026/05/gdx-1-14-1) | T1 | 28 May 2026 | 2026-11-23 |
| [S48] | [libGDX PR #7394: build ELFs for 16 kB pages (closed)](https://github.com/libgdx/libgdx/pull/7394) | T1 (project record) | — | 2026-11-23 |
| [S49] | [gdx-jnigen issue index (#70, #73: 16 KiB page size)](https://issues.ecosyste.ms/hosts/GitHub/repositories/libgdx%2Fgdx-jnigen/issues) | T3 | — | search result only, not opened |
| [S50] | [FreeType licences](https://freetype.org/license.html) | T1 | updated 16 Jan 2021 | 2026-11-23 |
| [S51] | [Noto Devanagari (OFL-1.1)](https://github.com/notofonts/devanagari) | T1 | current | 2026-11-23 |
| [S52] | [Kenney UI Pack (CC0)](https://kenney.nl/assets/ui-pack) | T1 | current | 2026-11-23 |
| [S53] | [game-icons.net: About (CC BY 3.0)](https://game-icons.net/about.html) | T1 | current | 2026-11-23 |
| [S54] | [jsfxr (Unlicense)](https://github.com/chr15m/jsfxr) | T1 | current | 2026-11-23 |
| [S55] | [Matn: font shaping for libGDX (Apache-2.0)](https://github.com/0880880/matn) | T1 | current | 2026-11-22 |
| [S56] | [GitHub Pages limits](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits) | T1 | current | 2026-11-23 |
| [S57] | [Play search "prime minister game" (India store)](https://play.google.com/store/search?q=prime%20minister%20game&c=apps&gl=IN) | T1 (primary data) | — | 2026-11-22 |
| [S58] | [Indian Election Game listing (50K+ installs)](https://play.google.com/store/apps/details?id=com.nikhilesh1401.indianelectiongame&gl=IN) | T1 (primary data) | updated 27 Jun 2026 | 2026-11-22 |
| [S59] | [Lumikai report via Outlook Respawn (25% payer conversion)](https://respawn.outlookindia.com/gaming/gaming-news/lumikai-india-gaming-market-1-5-billion-rmg-ban-2025) | T2 | 23 Mar 2026 | 2026-11-22 |
| [S60] | [Play search "desh chalao" (no app with that name)](https://play.google.com/store/search?q=desh%20chalao&c=apps&gl=IN) | T1 (primary data) | — | 2026-11-22 |

**T4 items** (from memory, not checked) used above:
- IT Rules 2021 intermediary scope;
- Criminal Law (Amendment) Act 1961 s.2 (maps);
- RPA 1951 s.126 and the Model Code of Conduct;
- COPPA;
- the EU DSA trader listing;
- Consumer Protection Act 2019 as the parent law;
- Play refunds from Console and buyer receipts;
- libGDX core collects no data;
- libGDX accessibility gaps;
- uninstall erases app data;
- GitHub Pages sets no cookies;
- Terms not required by Play;
- app-ads.txt;
- Google SDK licence terms.

None of these alone changes the design. Where one would, it is marked UNVERIFIED above.

[S1]: https://support.google.com/googleplay/android-developer/answer/14151465
[S2]: https://support.google.com/googleplay/android-developer/answer/9514050
[S3]: https://support.google.com/googleplay/android-developer/answer/9888374
[S4]: https://support.google.com/googleplay/android-developer/answer/9888072
[S5]: https://support.google.com/googleplay/android-developer/answer/9888077
[S6]: https://support.google.com/googleplay/android-developer/answer/9898842
[S7]: https://support.google.com/googleplay/android-developer/answer/9878810
[S8]: https://support.google.com/googleplay/android-developer/answer/10144311
[S9]: https://support.google.com/googleplay/android-developer/answer/10787469
[S10]: https://support.google.com/googleplay/android-developer/answer/13327111
[S11]: https://support.google.com/googleplay/android-developer/answer/9858738
[S12]: https://support.google.com/googleplay/android-developer/answer/112622
[S13]: https://support.google.com/googleplay/answer/2479637
[S14]: https://support.google.com/googleplay/android-developer/answer/9893335
[S15]: https://support.google.com/googleplay/android-developer/answer/9867159
[S16]: https://support.google.com/googleplay/android-developer/answer/6048248
[S17]: https://support.google.com/googleplay/android-developer/answer/9857753
[S18]: https://support.google.com/googleplay/android-developer/answer/9898843
[S19]: https://support.google.com/googleplay/android-developer/answer/138000
[S20]: https://support.google.com/googleplay/android-developer/answer/13634081
[S21]: https://play.google/developer-distribution-agreement.html
[S22]: https://support.google.com/googleplay/android-developer/answer/11926878
[S23]: https://developer.android.com/guide/practices/page-sizes
[S24]: https://developer.android.com/develop/ui/views/layout/edge-to-edge
[S25]: https://developer.android.com/google/play/billing/deprecation-faq
[S26]: https://developer.android.com/google/play/billing/integrate
[S27]: https://developer.android.com/games/pgs/data-collection
[S28]: https://developer.android.com/developer-verification
[S29]: https://developers.google.com/admob/android/privacy/play-data-disclosure
[S30]: https://support.google.com/admob/answer/13554116
[S31]: https://support.google.com/admob/answer/7313578
[S32]: https://support.google.com/admob/answer/2772208
[S33]: https://egazette.gov.in/WriteReadData/2023/248045.pdf
[S34]: https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/nov/doc20251117695301.pdf
[S35]: https://www.azbpartners.com/bank/update-indias-digital-personal-data-protection-framework-comes-into-effect/
[S36]: https://static.pib.gov.in/WriteReadData/specificdocs/documents/2025/aug/doc2025821618101.pdf
[S37]: https://static.pib.gov.in/WriteReadData/specificdocs/documents/2026/apr/doc2026430859401.pdf
[S38]: https://www.indiacode.nic.in/bitstream/123456789/22148/1/a2025-32.pdf
[S39]: https://www.advocatekhoj.com/library/bareacts/emblemsandnames/schedule.php
[S40]: https://taxguru.in/wp-content/uploads/2020/07/Consumer-Protection-E-Commerce-Rules-2020.pdf
[S41]: https://taxguru.in/?p=896142
[S42]: https://www.newsonair.gov.in/election-commission-delists-334-registered-unrecognised-political-parties
[S43]: https://www.thenewsminute.com/tamil-nadu/madras-hc-grants-interim-relief-to-kamal-haasan-in-personality-rights-case
[S44]: https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679
[S45]: https://oag.ca.gov/privacy/ccpa
[S46]: https://github.com/libgdx/libgdx
[S47]: https://github.com/libgdx/libgdx/releases
[S48]: https://github.com/libgdx/libgdx/pull/7394
[S49]: https://issues.ecosyste.ms/hosts/GitHub/repositories/libgdx%2Fgdx-jnigen/issues
[S50]: https://freetype.org/license.html
[S51]: https://github.com/notofonts/devanagari
[S52]: https://kenney.nl/assets/ui-pack
[S53]: https://game-icons.net/about.html
[S54]: https://github.com/chr15m/jsfxr
[S55]: https://github.com/0880880/matn
[S56]: https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits
[S57]: https://play.google.com/store/search?q=prime%20minister%20game&c=apps&gl=IN
[S58]: https://play.google.com/store/apps/details?id=com.nikhilesh1401.indianelectiongame&gl=IN
[S59]: https://respawn.outlookindia.com/gaming/gaming-news/lumikai-india-gaming-market-1-5-billion-rmg-ban-2025
[S60]: https://play.google.com/store/search?q=desh%20chalao&c=apps&gl=IN
