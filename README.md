# VoxWarden-Gate

**A Risk-Aware Security Toolkit and Benchmark for Open-Source Voice AI Ecosystems.**

> Status: in development (NDSS SafeOSE '27 Open-Source AI Security Hackathon submission)

## Problem
Open-source voice AI systems combine detectors, ASR models and applications,
but there is no reusable security layer that decides whether a voice
instruction should be trusted, and no open benchmark that measures end-to-end
security outcomes (attack success, false blocks, latency) instead of detector
accuracy alone.

## Pipeline
    Voice input
      -> Ingest and normalize
      -> Audio authenticity detection (pluggable detectors)
      -> Speech-to-text (pluggable ASR)
      -> Instruction risk analysis (risk tiers)
      -> Policy engine (allow / step-up / block)
      -> Open-source voice application or agent (via adapters)
      -> Audit log and VoxWarden-Bench evaluation

## Repository structure
    gate/        core toolkit (ingest, detectors, asr, risk, policy, audit)
    adapters/    integrations with voice frameworks and NLIP
    bench/       VoxWarden-Bench: datasets, attacks, metrics
    demo/        end-to-end demo
    configs/     policy and experiment configs
    docs/        threat model, datasets, decisions
    results/     benchmark outputs

## Setup
    python3.11 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt

## License
MIT. See LICENSE.
