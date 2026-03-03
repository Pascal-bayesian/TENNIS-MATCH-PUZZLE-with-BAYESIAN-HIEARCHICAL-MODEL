# TENNIS-MATCH-PUZZLE-with-BAYESIAN-HIEARCHICAL-MODEL
Two Consecutive Wins: A Bayesian Modeling Exercise.  This repository develops a classic scheduling puzzle using progressively richer Bayesian network models in Netica.

---

**Problem:**
Alice must win two consecutive matches against two opponents, Jenny and Carla. Jenny is described qualitatively as the strongest player in the club and “very good.” Alice can choose the order in which she plays them. What ordering maximizes her probability of achieving two consecutive wins?

The puzzle is initially stated without numbers. The goal of this project is to translate qualitative information into explicit probabilistic structure and examine the consequences.

Three models are constructed:

1. **Fixed Skill Model** – Deterministic win probabilities (e.g., Jenny 0.6, Carla 0.5).
2. **Uncertain Skill Model** – Skill parameters modeled with Beta priors, optionally enforcing the constraint that Jenny is stronger than Carla.
3. **Hierarchical Advantage Model** – Carla’s skill follows a Beta distribution; Jenny’s skill is defined structurally as
   `Jenny_Str = clip(0,1, Carla_Str + d)`
   encoding ordinal superiority directly in the generative structure.

Across all models, the same strategic result emerges:

> When the objective is to win two consecutive matches, the weaker opponent should be placed in the middle.

The conclusion follows from structural logic rather than fragile numerical choices. The middle match functions as a bottleneck: every successful sequence must pass through it.

This repository illustrates how qualitative assumptions can be converted into coherent probabilistic models and how different modeling choices (constraint-as-evidence vs structural encoding) lead to the same decision-theoretic insight.

---

https://www.norsys.com/netica.html
