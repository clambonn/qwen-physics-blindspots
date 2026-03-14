# qwen-physics-blindspots
# Qwen2.5-1.5B Physics & Math Blind Spots

A probing experiment on a small base language model to find where it fails on undergraduate physics and math questions.

## What this is

I loaded [Qwen/Qwen2.5-1.5B](https://huggingface.co/Qwen/Qwen2.5-1.5B) — a 1.5B parameter base model released by Alibaba in 2024 — and tested it on 10 physics and math questions to find its blind spots.

## What I found

The model had three main failure patterns:

- **Web content hallucination** — for straightforward math problems, the model generated fake HTML from tutoring websites like Wyzant and Study.com instead of solving the problem
- **Incomplete computation** — set up equations correctly but stopped before computing the final numerical answer
- **Hallucinated constraints** — added conditions not present in the original question

## Dataset

The full dataset of 10 examples (input, expected output, model output, error type) is available on HuggingFace:

👉 [Clambon/qwen2.5-1.5B-physics-math-blindspots](https://huggingface.co/datasets/Clambon/qwen2.5-1.5B-physics-math-blindspots)

## How to run

Open the notebook in Google Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1V9HiZXzLCDoEO2axSEA5fX0RXiWBA6Mb#scrollTo=ks1rjKgNb3Wt)

Or clone the repo and run locally with a GPU.

## Requirements
```bash
pip install transformers torch accelerate
```

## Author

Yasmin Kasem — Physics undergraduate, Mansoura University
