# Architecture

## Goal

Build a portable personal health copilot system that can log events, normalize data, compute deterministic derived state, and present safe summaries.

## Layers

### 1. Raw layer
Store unmodified imports or external payloads when needed for auditability.

### 2. Canonical layer
Store normalized events and sessions in a stable schema independent of vendor.

### 3. Derived layer
Store or generate deterministic totals, comparisons, and summaries from canonical data.

### 4. Presentation layer
Render markdown, cards, dashboards, or video from derived artifacts.

## Recommended order

1. canonical schema
2. storage paths
3. manual ingestion
4. derived calculations
5. summaries
6. optional adapters
7. optional media output
