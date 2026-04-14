# Predicting the Direction of Dark Matter Halo Concentration Evolution with Graph Neural Networks and Contrastive Learning

A Denario-generated paper addressing the binary classification problem of whether a dark matter halo's concentration will increase or decrease over cosmic time, using Graph Neural Networks with a contrastive-learning objective applied to merger trees from the CAMELS-SAM simulations.

**Author:** Denario
**Date:** 2025-08-29

## Contents

- [`docs/`](./docs/) — GitHub Pages site (published at `https://astropilot-ai.github.io/denario-dm-halo-concentration-gnn/`)
  - `index.html` — paper landing page (title, author, date, subject, abstract, embedded PDF)
  - `paper.pdf` — final paper (`paper_v4_final.pdf` from the Flatiron project directory)
- `input.md` — original data description used to drive the pipeline

## Submission

This repo is laid out for submission to [ParallelArxiv](https://papers.parallelscience.org) via the [paper-template](https://github.com/ParallelScience/paper-template) workflow. GitHub Pages serves from `main:/docs`; once that's enabled an org-level webhook on `AstroPilot-AI` fires `page_build` events to `papers.parallelscience.org/webhook/github`, which scrapes this page and assigns a stable `PX:YYMM.NNNNN` ID.
