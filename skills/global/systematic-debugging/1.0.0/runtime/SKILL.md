---
name: systematic-debugging
description: Use when encountering any bug, test failure, or unexpected behavior, before proposing fixes
---

# Systematic Debugging

## Governed use (import version 1.0.0)

This is a governed adaptation of obra/superpowers systematic-debugging at commit
`8ca22dba9a94f28898bbce59f2537ff4d87c747d`, under the included MIT license.
The workflow and supporting examples do not grant execution or write permission.

- Read the current project governance, task scope, permissions and relevant acceptance contract before acting. Respect frozen architecture and Owner decisions.
- In inspection-only work, use existing code, reports and raw evidence. Do not reproduce failures, add instrumentation, run commands with side effects, or change files. Mark unconfirmed causes `UNKNOWN` and list the experiment and permissions needed.
- Separate product defects, acceptance-tool defects, test-data defects, environment issues, missing evidence and authorization conflicts. Compare successive repair rounds; distinguish newly introduced defects from recurring defects at the same location.
- Reuse validated tools and fixtures where possible. Do not rewrite a harness to investigate a small discrepancy. Derive expected results from the specification, not from observed implementation behavior.
- For authorized experiments or fixes, change one causal variable at a time within the smallest approved scope. Honor the project's existing retry budget and historical counts; never reset them. If no budget is defined, propose a bounded experiment and stopping condition to the Owner before a mutation.
- Log only approved non-sensitive diagnostics. Never print credentials, secret environment-variable values, patient data, or private business data. Permission to inspect a setting is not permission to disclose it.
- This version is selected as a standalone debugging Skill. Do not load another Skill implicitly. Additional Skills require a new selection and verified pairwise compatibility; unknown compatibility blocks co-loading.
- Repeated failures require evidence review and Owner escalation at the project's stopping point. Failure count alone does not prove an architectural defect. Partial test passes do not establish overall acceptance; report the remaining checks as `UNKNOWN`.

The examples below and in supporting documents are illustrative. Their shell syntax and application APIs are not runtime dependencies. On Windows, select equivalent approved tools for the actual task. Adding validation layers, tests or logging still requires scope and permission; apply only the necessary layers.

## Overview

**Core principle:** ALWAYS find root cause before attempting fixes. Symptom fixes are failure.

**Violating the letter of this process is violating the spirit of debugging.**

## The Iron Law

```
NO FIXES WITHOUT ROOT CAUSE INVESTIGATION FIRST
```

If you haven't completed Phase 1, you cannot propose fixes.

## When to Use

Use for ANY technical issue:
- Test failures
- Bugs in production
- Unexpected behavior
- Performance problems
- Build failures
- Integration issues

**Use this ESPECIALLY when:**
- Under time pressure (emergencies make guessing tempting)
- "Just one quick fix" seems obvious
- You've already tried multiple fixes
- Previous fix didn't work
- You don't fully understand the issue

**Don't skip when:**
- Issue seems simple (simple bugs have root causes too)
- You're in a hurry (rushing guarantees rework)
- Manager wants it fixed NOW (systematic is faster than thrashing)

## The Four Phases

You MUST complete each phase before proceeding to the next.

### Phase 1: Root Cause Investigation

**BEFORE attempting ANY fix:**

1. **Read Error Messages Carefully**
   - Don't skip past errors or warnings
   - They often contain the exact solution
   - Read stack traces completely
   - Note line numbers, file paths, error codes

2. **Reproduce Consistently**
   - Can you trigger it reliably?
   - What are the exact steps?
   - Does it happen every time?
   - If not reproducible → gather more data, don't guess

3. **Check Recent Changes**
   - What changed that could cause this?
   - Git diff, recent commits
   - New dependencies, config changes
   - Environmental differences

4. **Gather Evidence in Multi-Component Systems**

   **WHEN system has multiple components (CI → build → signing, API → service → database):**

   **BEFORE proposing fixes, inspect existing boundary evidence; add diagnostic instrumentation only when authorized:**
   ```
   For EACH component boundary:
     - Log what data enters component
     - Log what data exits component
     - Verify environment/config propagation
     - Check state at each layer

   Run once to gather evidence showing WHERE it breaks
   THEN analyze evidence to identify failing component
   THEN investigate that specific component
   ```

   **Example (multi-layer investigation):**
   - Compare existing workflow, build and application receipts.
   - Check whether an approved setting is present without printing its value.
   - Identify the first boundary whose actual inputs differ from the frozen contract.
   - If evidence is missing, describe a redacted, bounded capture requiring explicit permission.

5. **Trace Data Flow**

   **WHEN error is deep in call stack:**

   See `root-cause-tracing.md` in this directory for the complete backward tracing technique.

   **Quick version:**
   - Where does bad value originate?
   - What called this with bad value?
   - Keep tracing up until you find the source
   - Fix at source, not at symptom

### Phase 2: Pattern Analysis

**Find the pattern before fixing:**

1. **Find Working Examples**
   - Locate similar working code in same codebase
   - What works that's similar to what's broken?

2. **Compare Against References**
   - If implementing pattern, read reference implementation COMPLETELY
   - Don't skim - read every line
   - Understand the pattern fully before applying

3. **Identify Differences**
   - What's different between working and broken?
   - List every difference, however small
   - Don't assume "that can't matter"

4. **Understand Dependencies**
   - What other components does this need?
   - What settings, config, environment?
   - What assumptions does it make?

### Phase 3: Hypothesis and Testing

**Scientific method:**

1. **Form Single Hypothesis**
   - State clearly: "I think X is the root cause because Y"
   - Write it down
   - Be specific, not vague

2. **Test Minimally**
   - Make the SMALLEST possible change to test hypothesis
   - One variable at a time
   - Don't fix multiple things at once

3. **Verify Before Continuing**
   - Did it work? Yes → Phase 4
   - Didn't work? Form NEW hypothesis
   - DON'T add more fixes on top

4. **When You Don't Know**
   - Say "I don't understand X"
   - Don't pretend to know
   - Ask for help
   - Research more

### Phase 4: Implementation

**Fix the root cause, not the symptom:**

1. **Create Failing Test Case**
   - Simplest possible reproduction
   - Automated test if possible
   - One-off test script if no framework
   - MUST have before fixing
   - Confirm the approved regression detects the specified defect; do not automatically load another Skill

2. **Implement Single Fix**
   - Address the root cause identified
   - ONE change at a time
   - No "while I'm here" improvements
   - No bundled refactoring

3. **Verify Fix**
   - Test passes now?
   - No other tests broken?
   - Issue actually resolved?
   - Cite the actual verification receipts and unresolved checks before claiming success

4. **If Fix Does Not Work: Stop and Reassess**
   - Preserve the failed attempt and actual evidence.
   - Count attempts using the existing project history and approved budget.
   - Resume Phase 1 only within the authorized budget; otherwise request an Owner decision.
   - Compare whether each failure belongs to the product, newly written tools/data, environment, evidence, or governance.
   - Propose an architecture review only when traceable evidence supports it. Do not change a frozen architecture or declare it wrong from repeated failures alone.

## Red Flags - STOP and Follow Process

If you catch yourself thinking:
- "Quick fix for now, investigate later"
- "Just try changing X and see if it works"
- "Add multiple changes, run tests"
- "Skip the test, I'll manually verify"
- "It's probably X, let me fix that"
- "I don't fully understand but this might work"
- "Pattern says X but I'll adapt it differently"
- "Here are the main problems: [lists fixes without investigation]"
- Proposing solutions before tracing data flow
- **"One more fix attempt" (when already tried 2+)**
- **Each fix reveals new problem in different place**

**ALL of these mean: STOP. Return to Phase 1.**

**If repeated fixes failed:** Reassess the evidence and follow the existing stopping rule (see Phase 4.4).

## your human partner's Signals You're Doing It Wrong

**Watch for these redirections:**
- "Is that not happening?" - You assumed without verifying
- "Will it show us...?" - You should have added evidence gathering
- "Stop guessing" - You're proposing fixes without understanding
- "Ultra-think this" - Question fundamentals, not just symptoms
- "We're stuck?" (frustrated) - Your approach isn't working

**When you see these:** STOP. Return to Phase 1.

## Common Rationalizations

| Excuse | Reality |
|--------|---------|
| "Issue is simple, don't need process" | Simple issues have root causes too. Process is fast for simple bugs. |
| "Emergency, no time for process" | Systematic debugging is FASTER than guess-and-check thrashing. |
| "Just try this first, then investigate" | First fix sets the pattern. Do it right from the start. |
| "I'll write test after confirming fix works" | Untested fixes don't stick. Test first proves it. |
| "Multiple fixes at once saves time" | Can't isolate what worked. Causes new bugs. |
| "Reference too long, I'll adapt the pattern" | Partial understanding guarantees bugs. Read it completely. |
| "I see the problem, let me fix it" | Seeing symptoms ≠ understanding root cause. |
| "One more fix attempt" (after 2+ failures) | Repeated failures require evidence review and the approved stopping rule; architecture remains unconfirmed without evidence. |

## Quick Reference

| Phase | Key Activities | Success Criteria |
|-------|---------------|------------------|
| **1. Root Cause** | Read errors, reproduce, check changes, gather evidence | Understand WHAT and WHY |
| **2. Pattern** | Find working examples, compare | Identify differences |
| **3. Hypothesis** | Form theory, test minimally | Confirmed or new hypothesis |
| **4. Implementation** | Create test, fix, verify | Bug resolved, tests pass |

## When Process Reveals "No Root Cause"

If systematic investigation reveals issue is truly environmental, timing-dependent, or external:

1. You've completed the process
2. Document what you investigated
3. Implement appropriate handling (retry, timeout, error message)
4. Add monitoring/logging for future investigation

**If the evidence is insufficient:** Report `UNKNOWN`; do not infer a cause from an unsupported percentage.

## Supporting Techniques

These techniques are part of systematic debugging and available in this directory:

- **`root-cause-tracing.md`** - Trace bugs backward through call stack to find original trigger
- **`defense-in-depth.md`** - Add validation at multiple layers after finding root cause
- **`condition-based-waiting.md`** - Replace arbitrary timeouts with condition polling
