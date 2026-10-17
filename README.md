# coding-standards

My standards for code I write or review, by hand or with AI agents. The primary audience is my own projects, where agents do the work and I review it. Adoption by other teams is secondary.

- [CODING_STANDARDS.md](CODING_STANDARDS.md) contains the complete rules, with a [table of contents](CODING_STANDARDS.md#contents). Technical rules come first, then contribution and review workflow, then language guidance and tools. Go and Rust guidance is provisional.
- [GUIDE.md](GUIDE.md) explains the choices and provides extra examples. It adds no rules; the standards take precedence.

Downstream repositories sync only `CODING_STANDARDS.md`. Its guide links work without copying the guide. Propose changes through a pull request.

## Scope

The standards set a high floor of practices, concepts, and broadly applicable conventions. Musts are the floor. Shoulds are high defaults that projects can depart from with a recorded reason, and projects can tighten any rule ([rule levels](CODING_STANDARDS.md#purpose-and-scope)).

Specific tools are suggestions in the guide. Projects own their tool configuration, metric definitions, and measurement mechanics. Where the standards leave such a detail to the project, they require the project to decide and record it. A few headline thresholds, such as coverage and complexity, remain Should defaults. Rules that keep checks honest stay in the standards however mechanical they look: configuration isn't loosened to pass, baselines only tighten, changed lines meet the coverage floor, and waivers are recorded.

This scope guides changes to this repository and adds no coding rules. Where the current standards still contain tool names or project-level detail, that text applies until a change removes it.

## Goals

These goals guide changes to this repository; they add no coding rules or exceptions. In priority order:

1. **Consistent decisions.** Help agents and reviewers agree on which rules apply and what counts as compliance without repeated owner clarification. Different justified design choices remain valid where the standards leave room for judgment.
2. **Practical expectations.** Address concrete problems and make review predictable. The existing [rule levels](CODING_STANDARDS.md#purpose-and-scope) and [exception process](CODING_STANDARDS.md#exceptions) provide consistency while preserving justified judgment.
3. **Simple downstream adoption.** Keep the copied standards complete and their authority clear, with explanations optional.
4. **Readable guidance.** Make rules easy to find and apply, retaining defining examples and essential interpretation. Completeness beats brevity.
5. **Maintainable policy.** Keep shared obligations consistent when they change, and preserve the reasoning and origins behind important choices.

Readability takes priority when consolidation makes rules harder to apply. Local links can repeat to keep rules findable; eliminating all repetition is not the goal. For project-specific conventions, see [Purpose and scope](CODING_STANDARDS.md#purpose-and-scope).

## Non-goals

- A universal consensus standard for every team.
- A comprehensive programming textbook or tool catalog.
- Project-specific tool configuration, metric definitions, or measurement mechanics.
- Minimizing word or token counts as an end in itself.
- Language coverage without concrete use in my projects. This guides future additions; existing provisional Go and Rust guidance remains.

## Evidence

Use observations from validator-fns adoption and review batches and similar downstream work: standards gaps agents encounter, owner corrections, and findings that recur across PRs. Record them in the relevant issue or PR and link resulting standards changes. Distinguish unclear standards, overlooked instructions, and missing enforcement where the cause is known. An optional `standards-gap` issue label can make this evidence searchable.

Another sign is downstream `AGENTS.md` files dropping duplicated general policy, retaining project-specific facts and agent instructions with links to the standards. Neither observation counts nor file length is a target, and an absence of recorded findings alone does not demonstrate improvement.
