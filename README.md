# claude-marketplace

A Claude Code plugin marketplace registry hosting Daniel May's published skills and plugins.

## Overview

This repository is a Claude Code plugin marketplace — a registry that lists published plugins/skills available for installation into Claude Code. The registry is defined in `.claude-plugin/marketplace.json` and follows the Claude Code marketplace format. Each entry points to an external GitHub repository that contains the actual skill implementation.

## Plugins

| Plugin | Version | Description |
|--------|---------|-------------|
| **superfix** | 1.0.0 | Intelligent dev orchestrator — classifies GitHub issues or freeform descriptions, assembles the right skill set, and drives work to a merged PR |
| **supersocials** | 1.3.0 | End-to-end social media skill — strategy, copywriting, video scripts, content calendars, visual briefs, and analytics across Instagram, TikTok, LinkedIn, X, YouTube, Facebook, Pinterest, Threads, and Bluesky |
| **expert-panel** | 1.0.0 | Adversarial expert panel review — profiles proposals, routes to skill or agent workflow, runs 4 independent experts across adversarial axes, and produces a decision dossier with must-fix, should-fix, unresolved objections, and a steel-manned alternative |
| **company-intel** | 1.1.0 | Deep background research and competitive intelligence on any company or organisation — entity verification, financial intelligence, people profiling, digital footprint, and competitive analysis |
| **topic-intel** | 2.1.0 | Deep, multi-source intelligence research on any non-company topic — markets, industries, policies, regulations, academic fields, technology categories, trends, and public figures |
| **visual-review** | 2.0.0 | Visual QA skill — renders PDFs and HTML at 300 DPI, runs Quick Pass or Full Review, produces action-first HOLD/FIX IF TIME/NOTE reports covering typography, brand, layout, and commercial press-readiness |
| **visual-stack-review** | 1.0.0 | Document production stack analyser — detects renderer from PDF metadata and project signals, classifies document type, and recommends stay-and-fix or migration with effort breakdowns |

## Installation / Usage

This marketplace is consumed by Claude Code's plugin system. To add this marketplace as a source and install plugins from it:

```bash
# Add this marketplace registry
/plugin marketplace add https://github.com/thedanielmay/claude-marketplace

# Then install individual plugins by name, e.g.
/plugin install superfix
```

> The exact CLI commands depend on your Claude Code version. Refer to the [Claude Code documentation](https://docs.anthropic.com/claude-code) for the current plugin installation flow.

## Project Structure

```
claude-marketplace/
└── .claude-plugin/
    └── marketplace.json   # Registry manifest — lists all plugins with source URLs and versions
```

Each plugin entry in `marketplace.json` specifies:

- `name` — the plugin identifier used at install time
- `source.url` — the GitHub repository containing the plugin implementation
- `description` — what the plugin does
- `version` — the current published version
- `strict` — whether the plugin runs in strict mode

## Status

Active — plugins are versioned and updated regularly. Last updated May 2026.
