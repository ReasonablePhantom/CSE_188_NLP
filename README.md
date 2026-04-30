# Heuristic Monotonicity Tags Help Prompted Inference but Reveal Fine-Tuning Fragility in a Small LLM on FLD

This is the official repository for the paper **"Heuristic Monotonicity Tags Help Prompted Inference but Reveal Fine-Tuning Fragility in a Small LLM on FLD"**.

## Overview

This repository contains the code and data to reproduce our investigation into whether heuristic monotonicity annotations help a small instruction-tuned language model (`Qwen2.5-1.5B-Instruct`) perform formal natural language inference on the FLD.v2 dataset.

**Key Findings:**
**Prompting:** Adding lightweight monotonicity labels improves direct prompting accuracy from 37.5% to 41.0%.
**Fine-Tuning Collapse:** Under free-generation QLoRA fine-tuning, the model exhibits a generation collapse, predicting the `UNKNOWN` class for almost all samples.
**Log-Prob Recovery:** When evaluating the exact same fine-tuned models using forced-choice log-prob scoring, discriminative ability is recovered (up to 48.0% accuracy), demonstrating that generative collapse obscures latent semantic learning.

## Repository Structure

* `CSE_188_NLP.ipynb`: The main Jupyter Notebook containing the complete pipeline: data preprocessing, heuristic labeling, model loading (4-bit QLoRA), prompt-based inference, and forced-choice log-prob evaluation.
* `requirements.txt`: List of Python dependencies required to run the experiments.
* `all_predictions.csv`: The raw model outputs and prediction logs from our evaluation runs.
* `summary_metrics.csv`: The compiled accuracy and macro-F1 scores across different experimental settings.

## Installation

We recommend using Python 3.10+ and setting up a virtual environment. Install the necessary packages using:

```bash
git clone [https://github.com/ReasonablePhantom/CSE_188_NLP.git](https://github.com/ReasonablePhantom/CSE_188_NLP.git)
cd CSE_188_NLP
pip install -r requirements.txt
