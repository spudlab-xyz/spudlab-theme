---
title: Field Station
date: 2026-09-18
description: A modular environmental monitoring station designed for repair, calibration, and long-term use.
status: Prototype
tags: [hardware, environment]
---

Field Station explores how an environmental monitor can remain understandable and repairable throughout its life.

## Design goals

- Use replaceable sensing modules.
- Record calibration and configuration alongside observations.
- Store timestamps, units, and source identifiers explicitly.
- Continue collecting safely during a network outage.

## Measurement context

Every observation records the sensor, unit, collection time, sampling interval, and applicable quality flags. Prototype results are clearly separated from validated observations.
