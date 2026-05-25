# BEAT: Tokenizing and Generating Symbolic Music by Uniform Temporal Steps

## Code Structure

```
code/
├── beat_tokenizer/          # BEAT encoding & decoding
│   ├── encoder.py           # Piano-roll → BEAT token sequence
│   ├── decoder.py           # BEAT token sequence → Piano-roll / MIDI
│   ├── vocab.py             # Token vocabulary definition
│   └── utils.py             # Base-3 conversion, mean velocity, etc.
├── model/                   # Transformer language model
│   ├── transformer.py       # LLaMA-style decoder with RoPE
│   ├── config.py            # Model hyperparameters
│   └── generate.py          # Sampling & decoding strategies
├── data/                    # Data processing pipeline
│   ├── preprocess.py        # MIDI/MuseScore → quantized piano-roll
│   ├── dataset.py           # PyTorch dataset & batch construction
│   └── augment.py           # Transposition augmentation
├── tasks/                   # Task-specific scripts
│   ├── continuation.py      # Piano & multi-track continuation
│   ├── accompaniment.py     # Real-time accompaniment generation
│   └── probing.py           # Structural pattern probing tasks
├── evaluation/              # Evaluation metrics
│   ├── objective.py         # JS divergence (GC, SC) & FMD
│   ├── unique_beat.py       # Unique beat ratio analysis
│   └── bpe_analysis.py      # BPE compression rate
├── baselines/               # Baseline tokenization implementations
│   ├── remi.py
│   ├── compound_word.py
│   └── interleaved_abc.py
├── train.py                 # Training entry point
├── evaluate.py              # Evaluation entry point
└── requirements.txt
```

## Quick Start

```bash
# Install dependencies
pip install -r requirements.txt

# Preprocess data
python data/preprocess.py --input_dir /path/to/midi --output_dir /path/to/processed

# Train
python train.py --config configs/piano.yaml

# Generate continuation
python tasks/continuation.py --checkpoint /path/to/ckpt --prompt /path/to/prompt.mid

# Real-time accompaniment
python tasks/accompaniment.py --checkpoint /path/to/ckpt --melody /path/to/melody.mid
```

## Coming Soon

Code and pretrained checkpoints will be released upon paper acceptance.
