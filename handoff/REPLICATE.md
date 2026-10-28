# Raise: how to replicate (saved 28 Oct 2026)

## What is in this folder
- `RaiseLondon/`: the full app code (git clone of github.com/minthantkyaw28/RaiseLondon, commit e5edb87, 28 Oct 21:19). This is the same code as the Lovable project lovable.dev/projects/282a4595-0860-4fa2-81c8-a697baaa787b (Lovable syncs to this repo).
  - `data/`: investor, company, deal, people and news CSVs (Dealroom export, 28 Oct 2026).
  - `supabase/migrations/` + `supabase/seed.sql`: database tables and seed data.
  - `docs/LOVABLE.md`, `docs/PROJECT.md`, `README.md`, `AGENTS.md`: the team's handoff notes.
  - `.env`: public Supabase URL and publishable key only (safe for the browser).
- `pitch-deck/project/`: the slide files of the Raise deck (claude.ai artifact A3McuHQVN5mhzgr7X54URG).
- `EVENT.md`: event details.

## Run it locally (tested 28 Oct: build OK)
1. `cd RaiseLondon`
2. `npm install` (or `bun install` if Bun is installed)
3. `npm run dev`, then open the local address it prints.
4. Get the latest code first with `git pull`.

## NOT in this folder (you must get these again)
- Secrets (never stored in git). Set them in Lovable Cloud / Supabase:
  - `ELEVENLABS_API_KEY`: voice transcription
  - `SUPABASE_SERVICE_ROLE_KEY`: server access to the database
  - `LOVABLE_CRON_SECRET`: scheduled jobs
  - `DEALROOM_CLIENT_SECRET`: Dealroom data refresh
- The live database contents (ratings, debriefs, pipelines people added in the app). Code + seed rebuild an empty copy.
- Lovable chat history (only in Lovable). The commit history (`git log`) records what was built.
- `node_modules` (re-created by `npm install`).

## Open issue
The app shows "Dealroom data" and "Source: Dealroom", but the deck's data slide says "AI agents collect public records" and no longer mentions Dealroom. Make them match before presenting.

## 3-minute pitch script (30-second demo at 1:00)
- 0:00 Cover: "We're team Raise. Raise puts London's active investors on one map, matched to your pitch, because finding the right investor shouldn't depend on who you already know."
- 0:10 Problem: "Raising in London today means networking. Founders spend months of evenings at events hoping to meet the right partner. Investor lists are scattered, out of date or paywalled. And if you're young with no network, you're filtered out before anyone hears your idea."
- 0:30 Alternatives: "Paid databases are priced for funds, free lists go stale, warm-intro tools need contacts you don't have, and AI intro tools don't tell you why they matched you. Nothing is built for a founder starting from zero. Raise is."
- 0:45 How it works: "Paste your pitch. Raise ranks investors out of 100 and tells you why. Check each firm's partners, portfolio and ratings. Then email the best fit first. Let me show you."
- 1:00 DEMO: filter Pre-seed + a sector ("These are the firms that fit"); click a firm ("partners, portfolio and cheque size"); Match my pitch → paste ("ranks every investor out of 100 and shows why"); point at top match ("That's who I email first").
- 1:30 Trust: "Only founders the firm actually backed can rate it, with set scores and no free text. Debriefs tell you why an investor passed, and only show once three or more founders answer."
- 1:50 Data: "AI agents collect public investor records, Make loads them into Supabase, and the app reads from there. The demo runs on real data: 281 London investors."
- 2:00 Business model: "Free for founders. Founder Pro, £15 a month, gives unlimited matches. Investors pay £99 a month to claim their profile, and events pay for labelled listings. Compare PitchBook at thousands a year. Paying never changes the ranking."
- 2:15 Scale: "£12.3bn went into UK smaller businesses last year, 57% of it to London. All-female founder teams got 2%. We win London, then other UK cities, then license to accelerators."
- 2:35 Roadmap: "Today it's built. Next: a founder pilot, verified accounts and a licensed data partner."
- 2:42 Ask: "Founders raising now: pilot Raise. Investors: claim your profile. Accelerators: run it with your next cohort. Finding an investor should take a pitch, not a network. We're team Raise. Thank you."

Fact sources: British Business Bank Small Business Equity Tracker 2026 (2025 data: £12.3bn, 57%) and 2024 (2%); Companies House 2024/25 (801,864 incorporations); Crunchbase/PitchBook prices from published plans and third-party estimates. £15/£99 are proposed prices, not tested.

## 3-minute demo-only script
- 0:00 Whole map: "Every dot is an active London investor, 281 of them, on one map."
- 0:20 Click Pre-seed + AI: "Two clicks, and the map drops to investors who back my stage and sector."
- 0:45 Switch Pixel → Chalk → Night: "Same data, easier to scan."
- 1:00 Search "Seedcamp": "Search any firm, partner or portfolio company."
- 1:15 Open profile: "What they invest in, cheque size, deals in the last year, partners to email, and my own pipeline from target to meeting."
- 1:50 What founders heard / Founder ratings: "Debriefs stay hidden until three founders answer. Ratings come only from founders the firm backed."
- 2:10 Match my pitch → paste sample: "Stage 40, sector 35, raise vs cheque 20, activity 5, and the reason for every match."
- 2:45 Top match: "That's who I email first. Finding an investor should take a pitch, not a network."

Sample pitch (made up for the demo): "We're a pre-seed AI startup in London building a tool that helps small clinics automate patient follow-ups. We're raising £500k. We have 3 paying pilot clinics and £2k monthly revenue. Two founders: one engineer, one ex-clinic manager."
