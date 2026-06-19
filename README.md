# BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps

[Demo](https://lekai-qian.github.io/BEAT-ICML2026/) | [Paper] (coming soon)

This is the code repository of the paper:

> BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps. ICML 2026.

BEAT encodes symbolic music in uniform temporal steps and generates it with a
single LLaMA backbone over a unified token vocabulary, supporting both solo
**piano** and **multi-track** settings.

# Status

The reference implementation is now available under
[`code/beat_camera/`](code/beat_camera/) — the BEAT tokenizer, the LLaMA
backbone, the MIDI/MusicXML data-preparation pipeline, and the training /
generation / continuation scripts. Pretrained checkpoints (piano and
multi-track) and the processed datasets will be released here separately.

The demo page (audio examples, repetition–diversity visualisations, and
qualitative comparisons) is served at the link above.

# Quick start

```bash
cd code
pip install -r beat_camera/requirements.txt

# continue a MIDI prompt (piano or multi-track)
python -m beat_camera.scripts.continue_piano \
    --checkpoint <ckpt.pt> --midi song.mid --prompt_bars 2
```

See [`code/beat_camera/README.md`](code/beat_camera/README.md) for the full API,
the data-preparation pipeline, and more examples.

# Repository layout

```
.
├── index.html, static/      # Demo page (served by GitHub Pages)
└── code/
    └── beat_camera/         # BEAT reference implementation
        ├── config.py        # model + training configuration
        ├── beat/            # unified vocabulary, base-3 codec, LLaMA backbone
        ├── piano/           # piano tokenizer / decoder / dataset / inference
        ├── multitrack/      # multi-track tokenizer / decoder / dataset
        ├── data_prep/       # MIDI / MusicXML -> NPZ converters
        └── scripts/         # train / generate / continue entry points
```
