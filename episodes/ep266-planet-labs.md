# EP266 — Will Marshall / Planet Labs

> **▶ Listen:** https://www.moonshots.io (EP266)
> **Show:** Moonshots with Peter Diamandis · **Aired:** 2026-06 · **Runtime:** ~1:50
> **Indexed:** 2026-08-22

Planet Labs images the entire landmass of Earth every day and has been doing it for a
decade. This episode is the CEO explaining what that archive can do — and, repeatedly and
explicitly, what his company has decided *not* to build on top of it. That second list is
the reason to listen. A CEO naming the products he is deliberately leaving on the table is
the cleanest white-space signal you will get, and there are at least four of them here.

---

## The room

| Who | Role | Why they matter here |
|---|---|---|
| Will Marshall | Co-founder & CEO, Planet Labs | Owns the archive; names what Planet won't build |
| Peter Diamandis | Host | Pushes the abundance framing; surfaces the consumer angle |
| Alex Wissner-Gross | Panel | Asks the sharpest question in the episode ("have you done it?") |
| Salim Ismail, Dave Blundin | Panel | Toss off the land-arbitrage idea and move on |

---

## Entity index

| Entity | What it is | First mentioned | Link |
|---|---|---|---|
| Planet Labs | Daily whole-Earth imaging, ~150 PB archive | early | [planet.com](https://www.planet.com) |
| Tanager | Hyperspectral imager, 400 bands, built with JPL | ~13:01 | [planet.com](https://www.planet.com/products/hyperspectral/) |
| Pelican | Current-gen high-res satellite, NVIDIA GPUs onboard | ~34:32 | [planet.com](https://www.planet.com/products/pelican/) |
| Owl | Next-gen daily-scan satellite, 3m → 1m | ~12:00 | [planet.com](https://www.planet.com) |
| NASA JPL | Co-built the Tanager hyperspectral instrument | ~13:01 | [jpl.nasa.gov](https://www.jpl.nasa.gov) |
| Google AlphaEarth | Earth-embedding model used alongside Planet data | ~21:16 | [deepmind.google](https://deepmind.google) |
| Google BigQuery | Where the tiled Earth embedding layer lands | ~21:16 | [cloud.google.com/bigquery](https://cloud.google.com/bigquery) |
| NVIDIA | GPUs flying on-orbit for edge inference | ~34:32 | [nvidia.com](https://www.nvidia.com) |

---

## Ideas

### 1. The predictive Earth model — the "crystal ball" Planet has not built

**Cue** — Wissner-Gross asks where the forward extrapolation is. Marshall: *"I think it's
coming... one step at a time. So we're focused first on retroactive analysis."* Pressed
directly — *"Have you done it?"* — Marshall answers **"No."** (~18:09–21:07)

**SIPOC**

| | |
|---|---|
| **Supplier** | Planet (API + embeddings), Google AlphaEarth |
| **Input** | Fixed-price API calls. Marshall is explicit that pricing is flat and you can train on it |
| **Process** | Train a forward model on one asset class's construction history; predict completion dates |
| **Output** | "This facility activates in N days," with a confidence band |
| **Customer** | Commodity desks, project-finance lenders, industrial supply-chain planners, insurers |

**Operator's read** — Planet already proved this on exactly one case: they trained on US
data-center construction history and extrapolated to China, predicting completion dates
*within a few days* (~19:24–20:14). Then they stopped, because as Marshall puts it there is
a *"$100 billion market just in the retro."* That is a company choosing the bigger adjacent
market — which is correct for them and leaves the door open for you.

You cannot out-compute Planet on a global model. You do not need to. Pick **one** asset
class where completion timing is worth money to somebody specific — LNG terminals, solar
farms, port expansions — and sell the prediction, not the pixels. The proof already exists
and they published it in a podcast.

What kills it: if Planet decides the forward model is the next $100B and ships it
themselves. Watch their product releases; this is a rented gap, not an owned one.

**Tag:** BUSINESS · **Verdict:** REAL

---

### 2. Permit and compliance enforcement detection

**Cue** — Marshall describes a live capability: civil government hands over a permit list,
AI finds the buildings in imagery, correlates against the list, flags what was built
without a permit. He calls it *"a boom to the legal industry."* (~44:51–45:30)

**SIPOC**

| | |
|---|---|
| **Supplier** | Planet imagery + public municipal permit registries |
| **Input** | API calls + the registry, which is usually free and public |
| **Process** | Change detection → building footprint extraction → join against permit list → exception report |
| **Output** | A ranked list of unpermitted structures with imagery evidence and dates |
| **Customer** | Municipal code enforcement, construction-litigation firms, title insurers |

**Operator's read** — This is the safest idea in the episode and Marshall says it has only
been run *"in a few areas."* Run-in-a-few-areas means not productized and not scaled.

It is a directory play, and directories are the format I trust most: the permit registry
*is* the list, and it is public. You are not creating demand, you are joining two datasets
that already exist and selling the exceptions. The buyer has a budget line for enforcement
and a legal obligation to act.

It is also not a crowded trade. Every geospatial startup chases hedge-fund alt-data because
the logos are sexier. Municipal code enforcement is unglamorous, procurement is slow, and
that is exactly why the gap is still there. Slow procurement is a moat once you are in.

**Tag:** BUSINESS · **Verdict:** REAL

---

### 3. EV road-toll land-value arbitrage

**Cue** — Diamandis, Blundin and Ismail riff on it live: *"which piece of land will generate
the most profit for us when EV tolls arrive?"* — reasoning about wiggly roads and drive-time
before versus after. Blundin: *"I'll bet I could do that during this podcast."* (~11:07–11:51)

**SIPOC**

| | |
|---|---|
| **Supplier** | Planet's 10-year archive + road network data + state policy trackers |
| **Input** | API calls, cheap; the hard input is legislative timing |
| **Process** | Parcel layer + drive-time topology + policy-change trigger |
| **Output** | Ranked parcels by expected relative value shift |
| **Customer** | **Unnamed.** Land funds, maybe. Nobody in the room is buying |

**Operator's read** — Note the blank. Four people in that room found this interesting and
not one of them is the customer.

The thesis is real — states are replacing lost gas-tax revenue and per-mile charging
changes the cost of distance — but the position is illiquid, the timing depends on
legislatures, and you would be holding land while you wait to be right. That is a fund's
trade, not an operator's. A fund can be early for three years. A business with payroll
cannot.

Keep it as a piece of thinking. Do not build it.

**Tag:** CONTENT · **Verdict:** INTERESTING, NOT BUILDABLE

---

### 4. Hyperspectral fingerprinting

**Cue** — The Tanager instrument: 400 spectral bands, IR through UV, built with JPL,
described as the first and most sensitive of its kind in orbit. It can identify tree
species, gas emissions, and — the detail worth stopping on — **which factory built a
vehicle**, because paint signatures differ by plant. (~13:01–13:59). Swath width goes 5× on
the next one (~43:01).

**SIPOC**

| | |
|---|---|
| **Supplier** | Planet (Tanager) |
| **Input** | API calls; narrower coverage than the daily optical scan |
| **Process** | Build a signature library for one material class, then match |
| **Output** | Provenance or emissions attribution with a spectral basis |
| **Customer** | Emissions-compliance regulators, ESG auditors, commodity provenance buyers |

**Operator's read** — Marshall presents this as a marvel, not a product line, and that is
the tell. Four hundred bands is a capability with no packaging.

The paint-signature detail is the one to sit with. Supply-chain provenance — proving where
a physical thing was actually made — is a live regulatory problem with real budget behind
it, and a spectral signature is a much harder moat than counting cars in a parking lot.

Least crowded idea in the episode. Also the one requiring the most domain work before you
could sell anything, because you have to build the signature library first and nobody hands
you that.

**Tag:** BUSINESS · **Verdict:** REAL

---

### 5. Sub-minute disaster response

**Cue** — On the LA Palisades fires, Planet delivered imagery within a couple of hours and
did building-by-building analysis of what was affected and where responders should go.
Marshall: *"had we been able to get that in a few minutes rather than a few hours. Could
that have saved lives?"* (~36:08–36:42)

**SIPOC**

| | |
|---|---|
| **Supplier** | Planet edge-compute (NVIDIA GPUs on Pelicans, sat-to-sat relay) |
| **Input** | API + integration work with responder systems |
| **Process** | Damage triage UI, routing, insurance claim pre-fill |
| **Output** | An operational product a responder uses under pressure |
| **Customer** | Emergency management agencies, Red Cross-class NGOs, property insurers |

**Operator's read** — Planet supplies the answer. Nobody supplies the *interface a person
uses while the fire is still burning*, and those are completely different products.

This is the one on this list I have standing to build. Everything I do professionally is
about performance under pressure — the constraint on a disaster-response tool is not model
accuracy, it is whether an exhausted human can act on it correctly at 3am. That is a
training-and-interface problem wearing a software costume.

The honest brake: government procurement is brutal, the sales cycle is measured in years,
and grant funding distorts the buyer. Real, and not a business you start while something
else pays the bills.

**Tag:** THE ONE WITH MY NAME ON IT · **Verdict:** REAL, SLOW

---

### 6. Natural-language query layer over Planet data

**Cue** — Marshall: *"we have already built this app, it's in beta testing right now... and
lots of other companies are doing things like that."* (~41:44–42:10)

**Operator's read** — Included specifically as a warning. The generic "chat with satellite
data" wrapper is being built by Planet itself and by everyone else. If your idea is a thin
conversational layer over someone's API, the API owner is already shipping it and they have
the data.

The lateral plays he gestures at are vertical. Go narrow, own a directory.

**Tag:** CONTENT · **Verdict:** ALREADY CROWDED

---

## Framing worth keeping

- **"Chips beat rockets."** Near-term, launch cost dominates; long-term, compute efficiency
  decides the winner (~1:17:54–1:18:29). Diamandis calls it the best line of the episode.
  It is also the argument for sitting in the application layer rather than building
  hardware.

- **AI has read the library but never looked out the window.** Marshall's recurring case:
  the next leap needs embodied, physical-world data, and planetary sensing supplies it
  (~1:37:26–1:44:18). Reframes Earth observation from niche vertical to something on the
  critical path.

- **The archive is the moat, and it is time-shaped.** *"Until someone invents a time
  machine... they can't go back in time and get our historical archives"* (~7:18–10:11).
  Ten years, 150 petabytes. A competitor launching a bigger constellation tomorrow still
  starts their archive tomorrow.

- **Planet has said out loud it will not build the downstream knowledge products.** Flat
  API pricing, train all you want, they sell data and stop there (~29:01–29:38). That
  sentence is the entire opening for everything above.

---

## The operator's take

The most valuable thing in this episode is not a technology. It is a CEO, on the record,
listing what his company has chosen not to build. Four separate times Marshall describes a
capability that works, then explains why Planet is not productizing it — the forward model,
permit enforcement, hyperspectral packaging, the responder interface. Most listeners hear a
tour of an impressive company. What is actually being read out is a list of unclaimed
positions, by the one person qualified to confirm they are unclaimed.

Where the altitude shows: everyone in that room evaluates ideas on whether they are
*interesting*, and that is the correct job for a fund, because a fund needs one in twenty to
be enormous. The EV-toll idea gets thirty seconds of genuine excitement and then everyone
moves on, and nobody asks who buys it. That question is not an oversight — it is genuinely
not their question. But it is the only question if the thing has to feed people. Run SIPOC
on the six ideas here and the Customer field is blank exactly once. That blank is the whole
difference between a podcast and a business plan.

If this were my only lead on Monday: permit enforcement. Not because it is the most
exciting — it is the least — but because the customer is named, the second dataset is
public and free, the buyer has a legal obligation rather than a preference, and Marshall
confirmed it has only been run in a few places. Boring, defensible, and the incumbent told
me they are not coming.

---

## What they'd say vs. what a builder hears

| They said | A builder hears |
|---|---|
| "There's a $100 billion market just in the retro" | They are not coming for the forward model. Rented gap — watch their releases |
| "This is to be a boom to the legal industry" | A named buyer with a budget line and a legal duty to act |
| "I'll bet I could do that during this podcast" | Nobody in this room is the customer |
| "We have already built this app" | Do not build the generic wrapper |
| "100x to go in the next couple of years" | The 100x is in the application layer, which is where a small team can stand |

---

## Honest limits

1. **Timestamps are from a working transcript** and may drift a few seconds from the
   published audio. Corrections welcome.
2. **The permit-enforcement buyer is asserted, not validated.** No municipality has been
   called. Until someone has, "the customer has a budget line" is a hypothesis with good
   priors, not a fact.
3. **Hyperspectral coverage is narrower than the daily optical scan** and the episode does
   not quantify revisit rate for Tanager. That gap could be fatal to a compliance product
   that needs regular cadence, and it is not addressed here.
4. **No pricing was verified.** "Fixed-price API, train all you want" is Marshall's
   characterization on a podcast, not a quote from a contract.

---

*Unofficial. Not affiliated with or endorsed by Moonshots, Peter Diamandis, or Planet Labs.
Short quotes used for commentary and criticism, attributed and timestamped. Go listen to the
episode — the link is at the top.*
