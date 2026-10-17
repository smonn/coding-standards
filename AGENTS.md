# AGENTS.md

This repository holds my coding standards as Markdown prose; there is no code. README.md states the goals, non-goals, and what counts as evidence for a change. Read it before proposing one. The "Changing these standards" section of CODING_STANDARDS.md applies here too.

## Project facts

- CODING_STANDARDS.md is the policy. Downstream repositories, such as validator-fns, copy it verbatim and nothing else, so it stays independently complete: every rule, level, scope, exception, and essential interpretation lives there.
- GUIDE.md is optional explanation and examples. It adds no rules or exceptions, uses no Must/Should/May rule keywords, and states that the standards take precedence.
- Links from the standards to the guide use absolute URLs (`https://github.com/smonn/coding-standards/blob/main/GUIDE.md#...`) so they work in downstream copies. Links within a document use local anchors.
- Each standards section keeps its *Why:* line and its defining examples.
- Completeness beats brevity, and readability beats consolidation. Word counts are measurements, never targets.

## Policy changes

A policy change alters a rule's level, scope, trigger, exceptions, interpretation, or existence. Rewording counts when it changes how the rule is applied.

- Propose each policy change as its own numbered decision for me: exact current and proposed text, expected benefit, protection lost, who would notice the loss (a reviewer, a tool, or nobody), and tradeoffs.
- Implement only the decisions I approve. Unapproved proposals stay in the issue or PR description, out of the diff.
- Decisions an issue explicitly names as settled stay settled. Currently: all six #7 decisions (screen-reader and message-catalog deferrals, YAGNI tiers, core dependency wrappers, coverage, UI mapping, FTA) and #8's CRAP check and threshold. Reopening one needs my explicit authorization on the issue you're working on. Other rules can be proposed for change through the process above. When an issue settles a new decision, add it here in the same PR.
- Work from the current text. Treat what issues and reviews I forward say about it as claims to check: quote the current text rather than a paraphrase or summary, and say where a claim no longer matches.

## Done means

- The PR includes a rule-by-rule comparison for every rule the diff touches: level, trigger, scope, exceptions, interpretation, and defining examples, each marked preserved or deliberately changed with its decision number.
- When text moves or is removed, the PR reports whitespace-delimited word counts before and after, for the standards and the guide separately, and distinguishes relocation from deletion.
- Every local anchor and guide link in all three documents resolves, and the table of contents matches the headings.
- When a change renames headings or anchors, or moves content out of the standards, check validator-fns' AGENTS.md and configuration for references and record the result, negative included.
- `git diff --check` passes.
- An independent reviewer without your context (a subagent or second agent) has checked preservation and readability. Their review does not count as approval.

## Workflow

- Use one branch and one draft PR per issue, branched from main, named `smonn/<issue>-<slug>`.
- Commits and PR titles use Conventional Commits, normally `docs:`, with a brief why in the body and `Refs #<issue>`.
- Record negative findings and retained rules, with reasons, on the issue or PR. A review that changes nothing is a valid outcome.
- Record related findings on the current issue or PR; ask before filing new issues.
- When I ask you to work on an issue, that covers committing, pushing, and opening a draft PR for it. Implementation still waits for approved decisions. Otherwise, commit, push, and open PRs only when asked. Merging, closing issues, and labeling are mine.
- Leave commits and PR descriptions free of AI attribution.
