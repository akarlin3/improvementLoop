# code-improvement-loop

Autonomous code auditing and improvement framework powered by LLMs.

The improvement loop scans a codebase, identifies issues via an LLM-powered
auditor, generates patches, validates them with tests, and scores improvements
through a judge pipeline — all with configurable, project-specific settings.

## Installation

```bash
pip install -e .
```

## Quick start

1. Copy the example config and customise it for your project:

   ```bash
   cp project_config.example.yaml project_config.yaml
   # edit project_config.yaml with your project details
   ```

2. Run the improvement loop:

   ```bash
   improvement-loop
   ```

## Project configuration

Each project provides a `project_config.yaml` that controls:

- **Source directories** to audit
- **Test command** to validate patches
- **System prompts** for the auditor, reviewer, and judge
- **Risk flags** and **forbidden patterns** for safety checks
- **Vector index** settings for codebase search

See `project_config.example.yaml` for the full schema with inline comments,
or `examples/pancdata3/project_config.yaml` for a real-world example.

## Development

```bash
pip install -e ".[test]"
python -m pytest tests/ -q
```
