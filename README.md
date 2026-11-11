<p align="center"><img src="assets/banner.svg" alt="Sandworm Cyber Arsenal" width="100%"></p>

<p align="center"><b>68 skill entries · 19 tools · 34 source repositories</b></p>

# Sandworm Cyber Arsenal

A focused security collection covering AppSec, agent and MCP security, reverse engineering, DFIR, detection, and supply-chain review.

คลัง Cyber ที่รวม AppSec, AI/MCP security, reverse engineering, DFIR, detection และ supply-chain review

[ภาษาไทย](README.th.md) · [Skills](CATALOG.md) · [Tools](TOOLS.md) · [Start here](docs/start-here.md) · [Sources](SOURCES.md) · [Collection hub](https://github.com/Sandworm-Lazarus/sandworm-arsenal)

## Original tool: Detection Lab

Authored implementation, documented inputs and synthetic regression fixtures. [Guide](docs/original-tool.md) · [Original work](ORIGINAL_WORK.md).

```bash
python3 scripts/detection_lab.py --input examples/events.json --expect examples/expected-alerts.json
python3 -m unittest discover -s tests -v
```

## What is inside

| Track | Entries |
| --- | ---: |
| Cyber | 46 |
| AI Security | 17 |
| Reverse / DFIR | 5 |

| Tool category | Projects |
| --- | ---: |
| Skill review | 2 |
| AI evaluation | 5 |
| Secrets | 1 |
| Containers / IaC | 2 |
| Supply chain | 4 |
| CI security | 1 |
| Code analysis | 2 |
| MCP development | 1 |
| Privacy & data handling | 1 |

## Use the collection

Browse the pinned source links and use the task paths in [Start here](docs/start-here.md). The offline CLI requires Python 3.9+ and no third-party dependencies.

```bash
git clone https://github.com/Sandworm-Lazarus/sandworm-cyber-arsenal.git
cd sandworm-cyber-arsenal
python3 scripts/arsenal.py search "" --json
python3 scripts/arsenal.py tools "" --json
python3 scripts/arsenal.py stats
python3 scripts/arsenal.py check
```

On Windows, use `py -3` if `python3` is unavailable.

## Evidence and reuse

Entry and Overview labels retain the inspection scope from the original research. Tool records are README overviews. No upstream installation, runtime certification, or benchmark result is claimed. [Review coverage](docs/review-status.md) records this collection's counts.

Original summaries, artwork, CLI and guides are [MIT licensed](LICENSE). Linked projects retain their own licenses; inspect [source/license notes](SOURCES.md) before copying or deploying external packages. This collection contains original curation and links, not upstream bundles.

## Related collections

- [AI Toolbox](https://github.com/Sandworm-Lazarus/sandworm-ai-toolbox)
- [Agent Skills](https://github.com/Sandworm-Lazarus/sandworm-agent-skills)
- [LLM Lab](https://github.com/Sandworm-Lazarus/sandworm-llm-lab)
- [Dev Playbooks](https://github.com/Sandworm-Lazarus/sandworm-dev-playbooks)

Selections overlap where tools support multiple tasks. Do not add collection counts together to infer a unique total.

## Original utility: privacy guard

Use the local Python [privacy guard](docs/privacy-guard.md) to apply explicit field policies and text masking to synthetic text or JSON. It uses the standard library and makes no network requests. Read the documented coverage and limits before using its output.

```bash
printf '%s\n' '{"customer_name":"Synthetic Person","message":"Email nina@example.invalid"}' | python3 scripts/privacy_guard.py json --sensitive-field customer_name
python3 -m unittest discover -s tests -p 'test_privacy_guard.py' -v
```

The [synthetic privacy fixtures](examples/privacy-fixtures.json) describe acceptance cases; they are not a Presidio or general PII-detection benchmark.

Read the [original-tool development case study](docs/development-notes/2026-11-11-original-tools.md) for implementation decisions and verification evidence.

Reproduce the committed fixture report with `python3 scripts/check_privacy_fixtures.py --check-report examples/privacy-guard-results.json`.
