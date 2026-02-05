# Review Skill

Review staged and unstaged code changes for quality issues, bugs, and best practices before committing.

## What to Check

1. **Code Quality** - Unused imports, complexity, duplication, magic numbers
2. **Potential Bugs** - Missing null checks, off-by-one errors, resource leaks
3. **Best Practices** - Naming conventions, error handling, security issues
4. **Type Safety** - Missing annotations, type mismatches

## Output Format

Group findings by severity with `file:line` references:
- **Critical** (must fix)
- **Warnings** (should fix)
- **Suggestions** (nice to have)

After review, offer: "Ready to commit? Use `/commit`"
