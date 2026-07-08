# XGBoost From Scratch

**A hands-on, numbers-first walkthrough of how XGBoost actually works** — residuals, similarity scores, gain, learning rate, and regularization, all worked out by hand on a tiny dataset, then verified against the real `xgboost` library.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sindhug/xgboost-from-scratch/blob/main/xgboost_from_scratch.ipynb)
[![Watch the video](https://img.shields.io/badge/YouTube-Watch%20the%20video-red?logo=youtube)](https://youtu.be/Y0EJQFj0foo)
![Stars](https://img.shields.io/github/stars/sindhug/xgboost-from-scratch?style=social)

> 📺 Companion repo for **[XGBoost Explained: How the Algorithm Actually Works (Step-by-Step)](https://youtu.be/Y0EJQFj0foo)** by Schovia Labs.

[![XGBoost Explained](https://img.youtube.com/vi/Y0EJQFj0foo/maxresdefault.jpg)](https://youtu.be/Y0EJQFj0foo)

---

## Why this repo exists

Most XGBoost explainers wave their hands at "gradient boosting" and jump straight to `model.fit()`. This repo does the opposite: it recomputes every number XGBoost would compute internally — by hand, on a dataset small enough to fit in your head — so the algorithm stops being a black box.

If you've ever wondered *what a similarity score actually is*, *why gain decides a split*, or *what lambda and gamma are doing to your leaves*, this is for you.

## The example

We predict a building's power consumption from outdoor temperature — a single feature, a handful of points, plotted as temperature (x) vs. power consumed (y). Small enough to trace by hand, complex enough to show every mechanic that matters at scale.

## What's covered

- **The basics** — classification vs. regression, and why decision trees can do both
- **Boosting vs. Random Forest** — trees grown in parallel and averaged vs. trees grown in sequence, each fixing what the last one got wrong
- **Part 1 — Gradient boosting**: computing the mean, residuals, similarity score, and gain by hand to pick the best split (walking through candidate thresholds 2.5, 7.5, 12.5, and growing the tree a second level)
- **Part 2 — Learning rate (eta / shrinkage)**: how a tree makes a prediction, and why scaling each tree's correction (eta = 0.5, eta = 0.2) trades speed for safety
- **Part 3 — Tree capacity & stopping**: max depth / max leaves, gamma as a minimum-gain bar for splitting, and early stopping on a validation metric
- **Part 4 — Regularization (lambda)**: how lambda shrinks similarity and leaf values toward zero, how gamma acts as a toll on gain, and why together they keep trees modest
- **What makes it "Extreme"**: curvature-aware splits, built-in regularization, native handling of missing/sparse data, and the speed optimizations that make it viable on large datasets

## Run it yourself

**[`xgboost_from_scratch.ipynb`](./xgboost_from_scratch.ipynb)** reproduces every number from the video on the exact same dataset — mean → residuals → similarity → gain → splits → learning rate → regularization — then checks the result against the real `xgboost` library. Click the **Open in Colab** badge above; no setup needed.

## Status

- [x] Concept walkthrough (this README)
- [x] Notebook reproducing the worked example by hand (residuals → similarity → gain → splits)
- [x] Same example verified against real `xgboost` output
- [ ] Visualizations of tree growth across boosting rounds

## Support this project

If this helped XGBoost click for you, a ⭐ on this repo goes a long way — it's how other people searching for "how does XGBoost actually work" find it too.

- ⭐ Star this repo
- 📺 [Watch the full video](https://youtu.be/Y0EJQFj0foo) and subscribe to **Schovia Labs**
- 🔁 Share it with someone learning gradient boosting

## Related

- Decision trees (referenced in the video) — link coming soon as that repo goes up.
