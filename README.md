# BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps

[Demo](https://lekai-qian.github.io/BEAT-ICML2026/) | [Paper] (coming soon)

This is the code repository of the paper:

> BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps. ICML 2026.


# Status
The codebase will be released in this repository in the coming weeks. The current snapshot includes:

1. The demo page (audio examples, repetition–diversity visualisations, qualitative comparisons), served at the link above.
2. Placeholder structure under [`code/`](code/) listing the intended modules (tokenizer, model, data pipeline, tasks, evaluation, and baselines).

A full release will include training and inference scripts, pretrained checkpoints for both the piano and multi-track settings, and reproducible evaluation pipelines for the objective, subjective, and pattern-probing experiments reported in the paper.


# Repository layout
```
.
├── index.html, static/      # Demo page (served by GitHub Pages)
└── code/                    # Source code
    ├── beat_tokenizer/      # BEAT encoding & decoding
    ├── model/               # LLaMA-style decoder with RoPE
    ├── data/                # MIDI/MuseScore preprocessing & augmentation
    ├── tasks/               # Continuation, accompaniment, probing
    ├── evaluation/          # JS divergence, FMD, unique-beat, BPE
    └── baselines/           # REMI, Compound Word, Interleaved ABC, Naive Piano-Roll, ...
```
