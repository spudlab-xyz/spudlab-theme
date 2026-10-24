---
title: What makes data traceable?
date: 2026-10-02
description: A short guide to recording provenance and context without making a data pipeline needlessly complicated.
tags: [data, reproducibility]
---

Traceability starts with being able to answer a few direct questions: where did a value come from, when was it recorded, what does it mean, and what happened to it afterwards?

## Preserve the source

Record provider, station, or instrument identifiers where it is lawful and useful. Keep source permissions and attribution requirements with the dataset.

## State what changed

Document filtering, corrections, aggregation, and unit conversions. A derived value should not be presented as a direct measurement.

> Good provenance does not guarantee good data, but it makes data possible to inspect and correct.

## Make uncertainty visible

Missing values, quality flags, and known limitations are data too. Preserve them instead of silently replacing them with plausible values.
