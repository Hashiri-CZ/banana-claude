# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.0.0] - 2026-03-14

### Added
- **Multi-model routing** — task-based model selection table (draft/standard/quality/text-heavy/batch)
- **Cost tracking** — `cost_tracker.py` with log, summary, today, estimate, and reset commands
- **Direct API fallback** — `generate.py` and `edit.py` scripts for when MCP is unavailable (stdlib only)
- **Brand/style presets** — `presets.py` for reusable brand identities (colors, style, typography, lighting, mood)
- **CSV batch workflow** — `batch.py` parses CSV files into generation plans with cost estimates
- **Green screen transparency pipeline** — workaround for Gemini's lack of transparent backgrounds
- **Safety filter rephrase strategies** — 5 rephrase patterns, common trigger categories, example rephrases
- Cost tracking reference (`references/cost-tracking.md`) with pricing table and free tier limits
- Brand presets reference (`references/presets.md`) with schema, 3 example presets, merge behavior
- Abstract domain mode added to README
- Step 1.5 (Check for Presets) in Creative Director pipeline
- `/banana preset` and `/banana cost` commands in Quick Reference
- Expanded error handling for MCP unavailable and safety filter false positives

### Changed
- Quality Presets section replaced with Model Routing table
- Pro model status updated: may still be accessible for image generation
- Pricing note: research suggests NB2 pricing may be ~$0.067/img
- Architecture diagram updated to show all 7 scripts and 6 references
- install.sh creates `~/.banana/` directory for cost tracking and presets

### Removed
- Legacy `nano-banana/scripts/__pycache__/` (orphaned .pyc files)

## [2.1.0] - 2026-03-13

### Added
- 4K resolution output via `imageSize` parameter (512, 1K, 2K, 4K)
- 5 new aspect ratios: 2:3, 3:2, 4:5, 5:4, 21:9 (14 total)
- Thinking level control (minimal/low/medium/high)
- Search grounding with Google Search (web + image)
- Multi-image input support (up to 14 references)
- Image-only output mode
- Safety filter documentation with `finishReason` values
- Pricing table, content credentials section (SynthID + C2PA)
- Resolution selection step (Step 4.5) in pipeline
- Character consistency multi-image reference technique
- Cover image, pipeline diagram, reasoning brief diagram, domain modes diagram

### Changed
- Rate limits corrected: ~10 RPM / ~500 RPD (reduced Dec 2025)
- `NANOBANANA_MODEL` default: `gemini-3.1-flash-image-preview`
- Search grounding key: `googleSearch` (REST format)
- Quality presets now include resolution column

### Fixed
- SKILL.md markdown formatting bug on text-heavy template line
- Contradictory prompt engineering mistake #9 wording

## [2.0.0] - 2026-03-13

### Added
- Initial release of Claude Banana
- Creative Director pipeline with 6-component Reasoning Brief
- 8 domain modes, MCP integration, post-processing pipeline
- Batch variations, multi-turn chat, prompt inspiration
- Install script with validation

[3.0.0]: https://github.com/AgriciDaniel/claude-banana/releases/tag/v3.0.0
[2.1.0]: https://github.com/AgriciDaniel/claude-banana/releases/tag/v2.1.0
[2.0.0]: https://github.com/AgriciDaniel/claude-banana/releases/tag/v2.0.0
