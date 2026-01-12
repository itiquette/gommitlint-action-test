# gommitlint-action-test

A test repository for validating [gommitlint-action](https://github.com/itiquette/gommitlint-action) functionality.

## Test Branches

Each branch tests a different scenario:

| Branch | Purpose | Expected Result |
|--------|---------|-----------------|
| `test-valid-conventional` | Valid conventional commits | Pass |
| `test-bad-conventional` | Invalid format ("added some stuff") | Fail |
| `test-long-subject` | Subject line > 100 chars | Fail |
| `test-with-config` | Custom `.gommitlint.yaml` config | Pass |
| `test-fixup-commit` | Contains `fixup!` commit | Fail (by default) |
| `test-scope` | Scoped commits `feat(api):` | Pass |
| `test-base-branch` | Tests `base-branch` parameter | Pass |

## CI Workflow

The CI tests all gommitlint-action inputs:

- `range` - Commit range syntax
- `base-branch` - Base branch comparison
- `count` - Last N commits
- `config` - Custom config file
- `rules` - Run specific rules only
- `exclude-rules` - Skip specific rules
- `format` - Output format
- `verbose` - Verbose output
- `log-level` - Log level
- `skip-verification` - Skip binary checksum

## Testing

Run tests manually via workflow dispatch in the GitHub UI. Select a branch and action version to test.

## Usage

```bash
go run .
```
