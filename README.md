# dustoff

Opinionated log housekeeping tool with dry-run support

Built for my own use; public in case it helps someone.

## Install

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Highlights

- Exit codes friendly for cron and CI
- Filter by age (--older-than) or size (--larger-than)
- Dry-run mode shows what would happen, touches nothing
- Scan directories for log files by glob pattern
- Archive matched logs into a timestamped .tar.gz

## Examples

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Project structure

```text
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   └── bug_report.md
│   └── dependabot.yml
├── docs/
│   ├── development.md
│   ├── roadmap.md
│   └── usage.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── utils.py
├── tests/
│   └── test_cli.py
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── pyproject.toml
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```
