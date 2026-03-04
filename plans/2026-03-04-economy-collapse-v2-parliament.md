# Economy Collapse Speedrun v2 — Parliament Edition

**Created:** 2026-03-04
**Status:** Concept & Implementation Plan
**Context:** Pivot from AI-generated options to player-generated proposals

---

## 1. The Core Idea

The game is no longer a quiz. It's a **political simulation**.

A real-world economic scenario appears on the projector screen. A small group of randomly elected **Parliament** members (3-5 players) must write policy proposals live on their phones under time pressure. The rest of the class — **The People** — watch parliament's proposals appear in real time on the projector as they're being typed, then vote on which policy to enact. An AI evaluates the quality of each proposal behind the scenes, but nobody sees those scores until the game is over.

Two modes: **Constructive** (build the best economy) and **Destructive** (collapse it as fast as possible). Same mechanics, flipped incentives.

The game host (Omar) is just the platform. The edgy, funny, or brilliant content comes entirely from the students. Nobody can blame the presenter for what parliament proposes.

---

## 2. Why This Is Better Than v1

| v1 (AI-generated options) | v2 (Parliament proposals) |
| --- | --- |
| Everyone does the same thing (pick A/B/C/D) | Two distinct roles with different experiences |
| AI generates edgy content → Omar is liable | Students generate content → Omar is the platform |
| Fixed 4 options, predictable format | Unpredictable, creative, chaotic proposals from real humans |
| Engagement = reading + tapping | Engagement = writing, watching live, judging, voting |
| One mode (destructive) | Two modes (constructive + destructive) |
| Feels like a quiz | Feels like a political simulation |
| Replayable but same vibe each time | Every game is completely different because humans write different things |

---

## 3. Roles

### Parliament (3-5 players, ~10% of class)
- Randomly assigned at game start
- Each round: see the scenario, write a policy proposal on their phone (30-40 second time limit)
- Goal depends on mode:
  - **Constructive**: Write the most economically sound, popular policy. Score = number of people who vote for your proposal.
  - **Destructive**: Write the most devastating, creative policy. Score = number of people who vote for your proposal.
- Parliament members compete against each other for votes across all rounds
- Their proposals appear live on the projector as they type (character by character or on submit — TBD, live typing is more entertaining)

### The People (~90% of class)
- Watch the scenario appear on the projector
- Watch parliament proposals appear in real time as they're being written
- Once proposals are submitted (or time runs out), vote on which policy to enact
- Goal depends on mode:
  - **Constructive**: Pick the policy that the AI rates as most economically beneficial. Score = AI quality rating of the policy you voted for.
  - **Destructive**: Pick the policy that the AI rates as most economically devastating. Score = AI quality rating (for destruction) of the policy you voted for.
- People don't see AI scores until the end — they're voting on instinct and judgment

---

## 4. Game Flow

### Pre-Game: Settings Screen (Host Only)

Before showing the QR code, the host configures:

| Setting | Options | Default |
| --- | --- | --- |
| Game Mode | Constructive / Destructive | Destructive |
| Game Duration | 3 / 5 / 7 / 10 minutes | 5 minutes |
| Parliament Size | 3 / 4 / 5 members | 4 |
| Names | Anonymous / Revealed | Anonymous |
| Proposal Time | 20 / 30 / 40 seconds | 30 seconds |
| Voting Time | 15 / 20 / 25 seconds | 20 seconds |

After configuring, the QR code appears and players join.

### Phase 1: Lobby

- QR code on projector, students scan and join
- Everyone enters a name (or gets assigned a random one if anonymous mode)
- Host screen shows players joining in real time
- Host clicks "Start Game" when ready
- The game randomly assigns Parliament members. Their phones show "You are Parliament" with a distinct UI. Everyone else sees "You are The People."
- Projector announces: "Parliament has been elected!" and shows (or hides, depending on anonymous setting) the parliament members' names

### Phase 2: Scenario (repeats each round)

**Step 1 — Scenario Appears (5 seconds)**
- The AI generates a real-world-grounded economic scenario (same as v1 — uses economy state, policy history, current events)
- Projector shows: headline, description, current economy dashboard
- Everyone sees the scenario on their phone too

**Step 2 — Parliament Writes (30-40 seconds)**
- Parliament members see a text input on their phone: "Propose a policy to address this crisis"
- They type their proposal under time pressure
- The projector shows parliament proposals appearing in real time as they're typed — like a live feed of proposals being written. This is the entertainment. The class watches parliament scramble.
- People's phones show: "Parliament is deliberating..." with the scenario visible, plus a live feed of proposals coming in
- When time runs out (or all parliament members submit early), proposals are locked

**Step 3 — AI Evaluation (2-3 seconds, happens instantly in background)**
- The AI receives all submitted proposals + the scenario + economy state
- It assigns each proposal:
  - An **impact vector** (GDP, employment, inflation, etc.) — same as v1
  - A **quality score** (1-100) based on economic soundness (constructive) or destructive creativity (destructive)
  - A **destruction_points** value
- These scores are HIDDEN from everyone until the end of the game

**Step 4 — People Vote (20 seconds)**
- People see all parliament proposals as labeled options (Proposal 1, 2, 3, etc. — or parliament member names if revealed mode)
- They tap to vote for one proposal
- Projector shows live vote counts updating in real time
- Early vote skip: if all people have voted, move on immediately
- Parliament members CANNOT vote (they already made their play by writing the proposal)

**Step 5 — Results (3 seconds)**
- Projector shows: vote distribution, winning proposal highlighted, economy impact animation
- The winning proposal's AI-assigned impacts are applied to the economy model
- Dashboard updates — bars shift, indicators change color
- The AI's quality scores are NOT revealed — just the vote results and economy changes
- Next round begins

### Phase 3: Game Over

When time runs out or the economy collapses/thrives past a threshold:

**Projector shows the full reveal:**

1. **Economy Final State** — the dashboard in its final form
2. **The AI Reveal** — for each round, show what the AI actually scored each proposal. "You voted for Proposal 2 (score: 34/100), but Proposal 3 was actually the best move (score: 87/100)." This is the "aha" moment.
3. **Parliament Leaderboard** — ranked by total votes received across all rounds. The winner is "elected" (constructive) or "most diabolical" (destructive).
4. **People Leaderboard** — ranked by cumulative AI quality scores of the proposals they voted for. The top person had the best judgment.
5. **Awards:**
   - **Constructive mode**: "President" (parliament with most votes), "Chief Advisor" (person with best judgment score)
   - **Destructive mode**: "Supreme Dictator" (parliament with most votes for destructive policies), "Minister of Chaos" (person who consistently picked the most devastating options)
   - **The Whistleblower** (person who most often voted against the majority — always the contrarian)

---

## 5. Scoring System (Detailed)

### Parliament Scoring

Each round, a parliament member's score = **number of people who voted for their proposal**.

- Across all rounds, parliament members accumulate votes
- Final parliament ranking = total votes received
- This incentivizes writing proposals that appeal to the crowd
- In constructive mode: write something that sounds smart and responsible
- In destructive mode: write something so hilariously devastating that everyone wants to pick it

### People Scoring

Each round, a person's score = **AI quality rating of the proposal they voted for**.

- The AI rates each proposal on a 1-100 scale:
  - Constructive mode: how economically beneficial is this policy? (higher = better)
  - Destructive mode: how economically devastating is this policy? (higher = more destructive = better)
- People accumulate these scores across all rounds
- Final people ranking = cumulative AI quality scores
- This rewards good judgment — can you identify the actually best (or worst) policy?
- The twist: you don't see the AI scores until the end, so you're voting blind on what you *think* is best/worst

### Economy Updates

- Only the **winning proposal** (most votes) gets enacted each round
- The AI assigns an impact vector to the winning proposal, same as v1
- Economy indicators update on the projector dashboard
- In constructive mode: the class is collectively trying to keep the economy healthy
- In destructive mode: the class is collectively trying to tank it

---

## 6. AI's Role (Shifted from v1)

The AI does three things now:

### 1. Scenario Generation (same as v1)
- Receives: economy state, policy history, round number, current events context
- Generates: headline, description, news ticker headlines
- Scenarios compound on previous decisions

### 2. Proposal Evaluation (NEW)
- Receives: the scenario, all parliament proposals, economy state, game mode
- For each proposal, generates:
  - Impact vector (GDP, employment, etc.)
  - Quality score (1-100)
  - Destruction points
  - A brief "AI commentary" (revealed at end of game — e.g., "This would have caused hyperinflation within 6 months. Creative, but economically suicidal. 82/100 destruction score.")
- This happens in the background while people are voting, so no latency hit

### 3. End-Game Analysis (NEW)
- Generates a brief "post-game report" summarizing what happened to the economy and why
- Highlights the most impactful decisions
- Delivered as a fun narrative on the projector during the game-over screen

---

## 7. The Projector Experience (What Makes It a Show)

The projector is still the star. But now it has more phases:

### During Lobby
- QR code, player names appearing, game settings visible

### During Parliament Writing Phase
- Split screen: scenario on the left, live proposal feed on the right
- Parliament proposals appear as they're being typed or submitted
- Timer counting down: "Parliament has 25 seconds..."
- This is the popcorn moment — the class watches their parliament members scramble to write something

### During Voting Phase
- All proposals displayed (numbered or named)
- Live vote bars updating as people vote
- Timer counting down

### During Results
- Vote distribution chart
- Winning proposal highlighted with a dramatic reveal
- Economy dashboard updates with animated transitions
- News ticker updates with satirical commentary

### During Game Over
- The AI Reveal: each round's proposals with hidden scores now visible
- Leaderboards
- Awards
- Economy post-mortem narrative

---

## 8. Phone UI by Role

### Parliament Phone UI
- **Scenario screen**: Shows the headline and description
- **Writing screen**: Large text input, character counter (max ~200 chars to keep it short), submit button, countdown timer
- **Waiting screen**: "Your proposal has been submitted. Watching the people decide..." with live vote counts
- **Between rounds**: See how many votes you got, your running total

### People Phone UI
- **Scenario screen**: Shows headline and description + "Parliament is deliberating..."
- **Live proposal feed**: Watch proposals appear as parliament writes them
- **Voting screen**: All proposals listed as cards, tap to vote, countdown timer
- **After voting**: "Vote submitted. Waiting for results..."
- **Between rounds**: See which proposal won, but NOT the AI scores

### Both
- **Game over**: Personal stats, your final score, your rank, any awards

---

## 9. Anonymous vs. Revealed Mode

### Anonymous Mode
- Parliament proposals are labeled "Proposal 1", "Proposal 2", etc.
- People vote purely on policy content, not on who wrote it
- Parliament members' identities are hidden until the end-of-game reveal
- This prevents popularity bias and encourages honest evaluation

### Revealed Mode
- Proposals are labeled with the parliament member's name
- Adds a social/political layer — do you vote for your friend's proposal or the better one?
- More chaotic, more fun, but less "pure" as a judgment exercise

---

## 10. Technical Changes from v1

### What Stays
- FastAPI + WebSockets architecture
- Economy model (6 indicators, 0-100, clamping)
- QR code + ngrok setup
- Host display concept (dashboard, news ticker, overlays)
- OpenRouter/Grok for AI
- Cumulative scoring, end-of-game leaderboard
- Real-world news context in AI prompts

### What Changes
- **Player roles**: New concept — parliament vs. people, randomly assigned at game start
- **Player phone UI**: Two different UIs depending on role (text input for parliament, voting for people)
- **Game settings screen**: New pre-game config page on the host
- **AI's job**: Still generates scenarios, but now also evaluates parliament proposals and assigns scores
- **Scoring system**: Parliament scored by votes received, people scored by AI quality of their picks
- **Game flow timing**: Each round has writing phase + voting phase (longer rounds, fewer rounds total)
- **Round structure in server.py**: New phases — scenario → parliament_write → voting → results
- **End-game screen**: AI reveal of hidden scores, richer leaderboard with role-specific awards

### What's Removed
- AI-generated policy options (replaced by parliament proposals)
- The fixed A/B/C/D option structure
- Pre-caching of scenarios with option sets (AI now only generates scenarios, evaluation happens after proposals are in)

### New Files/Modules Needed
- Game settings logic (config screen on host)
- Role assignment logic (random parliament selection)
- Proposal evaluation prompt (new AI call after proposals submitted)
- Updated player.html with role-based UI (parliament input vs. people voting)
- Updated host.html with writing phase display, settings screen

---

## 11. Estimated Round Pacing

| Phase | Duration | What's Happening |
| --- | --- | --- |
| Scenario appears | 5 sec | Everyone reads the crisis headline |
| Parliament writes | 30-40 sec | Parliament types proposals, projector shows live feed, people watch |
| AI evaluates | 2-3 sec | Background — happens while transitioning to vote phase |
| People vote | 15-20 sec | People pick a proposal, live vote bars on projector |
| Results | 3-5 sec | Winning proposal, economy update, brief pause |
| **Total per round** | **~60-70 sec** | |

For a 5-minute game: **~4-5 rounds**. Enough to tell a story, not too many to drag.

---

## 12. LLM Prompts Needed

### Prompt 1: Scenario Generation (adapted from v1)
Same as before — generates headline, description, news ticker based on economy state and policy history. No longer generates options.

### Prompt 2: Proposal Evaluation (NEW)
```
You are an economics AI evaluator for a classroom simulation game.

GAME MODE: {constructive|destructive}
CURRENT SCENARIO: {headline + description}
CURRENT ECONOMY STATE: {economy_state_json}

PARLIAMENT PROPOSALS:
{numbered list of all submitted proposals}

For EACH proposal, return JSON:
{
  "evaluations": [
    {
      "proposal_index": 1,
      "quality_score": 0-100,
      "impacts": {"gdp": X, "employment": X, "inflation": X, "public_trust": X, "trade_balance": X, "national_debt": X},
      "destruction_points": X,
      "ai_commentary": "Brief witty 1-sentence analysis revealed at end of game"
    },
    ...
  ]
}

SCORING RULES:
- Constructive mode: quality_score = how economically beneficial and well-reasoned the policy is
- Destructive mode: quality_score = how creatively devastating the policy is (reward wit and economic logic even in destruction)
- Impacts should be economically semi-plausible given the proposal
- destruction_points: positive = helps economy, negative = hurts economy
- ai_commentary: be witty, satirical, brief. This gets revealed at end of game for laughs.

If a proposal is gibberish, off-topic, or too short to evaluate:
- Give it a quality_score of 5-15
- Give neutral impacts
- ai_commentary: roast them gently
```

### Prompt 3: End-Game Narrative (NEW, optional)
```
Summarize what happened to this economy in 3-4 satirical sentences.
Economy started at: {starting state}
Economy ended at: {final state}
Policies enacted: {policy history}
Game mode: {constructive|destructive}

Write it like a news anchor wrapping up a segment. Be funny.
```

---

## 13. Game Settings Data Model

```python
@dataclass
class GameSettings:
    mode: str = "destructive"           # "constructive" or "destructive"
    duration_seconds: int = 300          # 3/5/7/10 minutes
    parliament_size: int = 4             # 3/4/5
    anonymous: bool = True               # anonymous or revealed names
    proposal_time_seconds: int = 30      # 20/30/40
    voting_time_seconds: int = 20        # 15/20/25
```

---

## 14. Open Design Questions

1. **Should parliament proposals appear live as they type, or only after submitting?** Live typing is more entertaining (the class watches words appear in real time) but could be distracting. Submitting all at once creates a reveal moment. Recommendation: show proposals live as they type — it's more engaging and fills the 30-second writing window.

2. **Can parliament members see each other's proposals while writing?** If yes, they might copy or react to each other. If no, proposals are independent. Recommendation: no — keep proposals independent. They see what they're writing but not what others are writing. The projector and people see all proposals live.

3. **What happens if a parliament member doesn't submit in time?** Their proposal is whatever they've typed so far (auto-submit on timeout). If they typed nothing, they get skipped for that round. Their phone shows "Time's up! Your draft was submitted." or "Time's up! You didn't submit a proposal."

4. **Should parliament roles rotate between rounds?** Original design says fixed parliament for the whole game. But rotating each round means more people get to write proposals. Trade-off: fixed = parliament members develop a "political identity" over rounds; rotating = more inclusive. Recommendation: fixed for now — simpler, and creates a competitive dynamic between parliament members across rounds.

5. **What if two proposals are tied in votes?** Random tiebreak, same as v1.

6. **Max proposal length?** 200 characters feels right — forces brevity, prevents essays, keeps the projector display clean. That's about 1-2 sentences.

---

## 15. Implementation Steps (High-Level)

### Phase 1: Refactor Game Core
- [ ] Add GameSettings dataclass with all configurable options
- [ ] Add role assignment logic (random parliament selection at game start)
- [ ] Refactor Game class: new round phases (scenario → writing → evaluation → voting → results)
- [ ] Add proposal collection from parliament members
- [ ] Add AI evaluation call (new prompt for scoring proposals)
- [ ] Update scoring: parliament = votes received, people = AI quality of their pick

### Phase 2: Refactor Server
- [ ] Add game settings endpoint (POST /settings before game start)
- [ ] Update WebSocket messages for new phases: `parliament_write`, `proposals_ready`, `voting`, etc.
- [ ] Different message payloads for parliament vs. people WebSockets
- [ ] Phase timers: writing countdown, voting countdown

### Phase 3: Refactor Host Display
- [ ] Add settings screen overlay (before lobby)
- [ ] Add parliament writing phase display (live proposal feed)
- [ ] Update voting display (show text proposals instead of fixed A/B/C/D)
- [ ] Add AI reveal to game-over screen (hidden scores now visible)
- [ ] Add end-game narrative

### Phase 4: Refactor Player UI
- [ ] Role assignment screen ("You are Parliament" / "You are The People")
- [ ] Parliament UI: text input with character counter, timer, submit button
- [ ] People UI: scenario display + live proposal feed during writing phase, then voting cards
- [ ] Updated game-over screen with role-specific stats

### Phase 5: Update LLM Integration
- [ ] Adapt scenario generation prompt (no longer generates options)
- [ ] Add proposal evaluation prompt and function
- [ ] Add end-game narrative generation (optional)
- [ ] Handle edge cases: empty proposals, gibberish, timeouts

### Phase 6: Testing
- [ ] Test with 2-3 phones: 1 parliament, 2 people
- [ ] Test both constructive and destructive modes
- [ ] Test anonymous and revealed modes
- [ ] Test edge cases: no proposals submitted, all same votes, parliament disconnect
- [ ] Full demo rehearsal

---

## 16. What We Keep from v1

The current codebase is not thrown away. Here's what carries over directly:

| Component | Status |
| --- | --- |
| config.py | Extend with GameSettings |
| economy.py | Keep as-is |
| game.py | Heavy refactor but same structure |
| llm.py | Keep scenario generation, add evaluation prompt, adapt system prompt |
| server.py | Refactor WebSocket handling for roles and phases |
| host.html | Extend with settings screen, writing phase, AI reveal |
| player.html | Major refactor for role-based UI |
| requirements.txt | Keep as-is |
| .env | Keep as-is |
| ngrok setup | Keep as-is |

---
