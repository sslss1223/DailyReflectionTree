# Write-Up: The Daily Reflection Tree
**DT Fellowship Assignment — Design Rationale**

---

## Why These Questions?

The hardest part of this assignment was not building the tree. It was writing questions that a tired person at 7pm would actually *pause at* — not click through to get it over with.

My guiding test for every question: **Would a real person recognize themselves in at least two of the options?** If all four options pointed obviously to the "good" answer, the question was useless. I threw out seven early drafts for this reason.

### Axis 1 — Locus of Control

The opening question — "If today were a weather report, what would it be?" — is intentionally non-psychological. People arriving at an evening reflection tool are carrying the day's emotional residue. Asking "did you demonstrate internal locus of control today?" would activate defensiveness. Asking about weather gets an honest, felt answer before the analytical mind engages.

The follow-up questions differ based on whether the day felt good or bad. Someone who had a good day needs to be asked *why* they think it went well — because external attribution ("I got lucky") is invisible when the outcome was positive. Someone who had a hard day needs a different entry point: not "what did you do wrong?" but "what did you do with that feeling?" This asymmetry is intentional — Rotter's original work shows that locus of control attribution is emotionally asymmetric. People are more likely to externalize bad outcomes than good ones.

### Axis 2 — Contribution vs Entitlement

Entitlement is invisible to the person holding it. I designed the options carefully so that entitlement-leaning answers sound *reasonable* — "I felt I wasn't getting the recognition my work deserved" is a statement most people would agree is fair. The job of the tree is not to catch people saying something obviously wrong, but to make visible a pattern they might not have labeled.

The key move in Axis 2 is the second question — "At the end of today, which thought comes more naturally to you?" This shifts from reporting a specific incident (which people can rationalize) to revealing an *orientation*. The orientation question is harder to game.

The reflection nodes are careful not to shame. Organ's OCB research shows that entitlement-oriented employees are often people who feel genuinely undervalued. The reflection for the entitlement path acknowledges the need ("wanting recognition isn't wrong") before offering the reframe.

### Axis 3 — Radius of Concern

Maslow's self-transcendence (1969) is the under-taught apex of his hierarchy. Most pop-psychology stops at self-actualization. But Maslow himself argued in his later work that the healthiest humans orient *outward* — that meaning comes not from achieving your own goals but from serving something beyond yourself.

The opening question here is deliberately concrete: "Who was in the frame with you?" It avoids abstract language like "did you think about the collective?" and instead asks the person to visualize the actual scene. The follow-up diverges: self-oriented people are nudged to look outward ("did anyone else's situation cross your mind?"), while already-outward people are asked whether they *acted* on the awareness (Batson's distinction between empathy-as-feeling and perspective-taking-as-action).

---

## Branching Design — Trade-offs

**Binary branches vs. multi-way branches:** I chose to keep decision nodes binary — internal vs. external, contribution vs. entitlement — even though human experience is more continuous. The alternative (a spectrum of 4 branches) would require 4× the content nodes and would make the tree unwieldy for a 48-hour build. More importantly, the point of the tree is not to precisely score someone on a continuum — it's to move them from vague felt-sense to one concrete observation. Binary branches serve that goal.

**Cross-axis interpolation:** The summary node references the actual answer from A1_OPEN ("you described your day as '...'") to create the feeling of a coherent conversation rather than three separate quizzes. This is the most important structural decision in the tree — without it, the three axes feel disconnected. The 8 closing insight combinations (2³) ensure the summary is genuinely personalized.

**What I'd improve with more time:**
1. Add a fourth node type — "challenge" — that asks the employee to name one specific action for tomorrow, making the reflection operational rather than just observational.
2. Add streak tracking: "Yesterday you leaned external. Today you leaned internal. That's movement."
3. The summary node currently picks closing insights by key lookup. With more time, I'd add weighted scoring (not just dominant-pole) so that someone who scored 3:1 internal vs. 2:2 gets a meaningfully different reflection than someone 4:0.
4. Test every question against at least 10 real people before shipping. Questions that feel insightful to the designer often feel obvious or alienating to users.

---

## Psychological Sources

- Rotter, J.B. (1954). *Social learning and clinical psychology.* — Original locus of control framework
- Dweck, C.S. (2006). *Mindset: The New Psychology of Success.* — Fixed vs. growth attribution in response to setbacks
- Campbell, W.K. et al. (2004). "Psychological Entitlement: Interpersonal Consequences and Validation of a New Self-Report Measure." — Entitlement as stable trait, not just momentary feeling
- Organ, D.W. (1988). *Organizational Citizenship Behavior.* — Discretionary effort beyond formal job requirements
- Maslow, A.H. (1969). "Various meanings of transcendence." — Self-transcendence as the understated apex of human motivation
- Batson, C.D. (2011). *Altruism in Humans.* — Distinction between empathy-as-emotion and perspective-taking-as-cognition

---

*Total nodes: 31 | Question nodes: 10 | Decision nodes: 7 | Reflection nodes: 6 | Bridge nodes: 2 | Summary: 1 | Start/End: 2 | Unique conversation paths: 16*
