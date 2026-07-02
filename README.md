# BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps

[Demo](https://lekai-qian.github.io/BEAT-ICML2026/) | [Code](https://github.com/Lekai-Qian/BEAT-code) | [Paper] (coming soon)

Project page and audio demo for the ICML 2026 paper:

> BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps. ICML 2026.

BEAT encodes symbolic music in uniform temporal steps and generates it with a
single LLaMA backbone over a unified token vocabulary, supporting both solo
**piano** and **multi-track** settings.

This repository hosts the **demo page** — audio examples, repetition–diversity
visualisations, and qualitative comparisons — served via GitHub Pages at the
link above.

# Code

The reference implementation (the BEAT tokenizer, the LLaMA backbone, the
MIDI/MusicXML data-preparation pipeline, and the training / generation /
continuation scripts) lives in a separate, lightweight repository:

**https://github.com/Lekai-Qian/BEAT-code**

Pretrained checkpoints (piano and multi-track) and the processed datasets will
be released there separately.

# Repository layout

```
.
├── index.html          # Demo page (served by GitHub Pages)
└── static/             # Demo assets: audio samples, images, CSS / JS
```
