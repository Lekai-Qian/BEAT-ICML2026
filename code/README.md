# BEAT — source code

The BEAT reference implementation lives in [`beat_camera/`](beat_camera/): a
single LLaMA backbone over a unified 593-token vocabulary that generates both
solo **piano** and **multi-track** symbolic music. See
[`beat_camera/README.md`](beat_camera/README.md) for the full API,
data-preparation pipeline, and runnable examples.

## Structure

```
code/
└── beat_camera/
    ├── config.py            # shared model config + per-mode train configs
    ├── beat/                # shared library: vocab, base-3 codec, LLaMA backbone
    ├── piano/               # piano mode: tokenizer / decoder / dataset / inference
    ├── multitrack/          # multi-track mode: tokenizer / decoder / dataset
    ├── data_prep/           # MIDI / MusicXML -> NPZ converters (data pipeline)
    └── scripts/             # train / generate / continue entry points
```

## Quick start

Run modules from the `code/` directory so that `beat_camera` is importable:

```bash
cd code
pip install -r beat_camera/requirements.txt

# continue a MIDI prompt (piano)
python -m beat_camera.scripts.continue_piano \
    --checkpoint <ckpt.pt> --midi song.mid --prompt_bars 2

# continue a MIDI prompt (multi-track)
python -m beat_camera.scripts.continue_multitrack \
    --checkpoint <ckpt.pt> --midi song.mid --prompt_bars 2

# build training data from a MIDI folder
python -m beat_camera.data_prep.midi2pianonpz <midi_dir> --output_dir <out_dir>
```

Every entry point prints `--help` for its full option list. Pretrained
checkpoints and the processed datasets will be released separately.
