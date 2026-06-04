# AI Audit Template and Prompt Log Format Design

## Overview
Create a clean, reusable AI audit report template in both existing AI-02 locations and reformat `logs/prompts_log.md` for readability without changing the underlying prompt content.

## Requirements
- Update `templates/ai-02-ai-audit-report-template.md`.
- Update `ai-02-ai-audit-report-template.md` to keep it aligned with the template copy.
- Preserve the existing 5-section AI audit entry structure.
- Keep the template usable for repeated artifact entries.
- Reformat `logs/prompts_log.md` only.
- Do not change the content of the logged prompts.
- Do not invent or remove prompt entries.
- Keep existing screenshots and output material referenced in the log.

## Constraints
- Work only in existing project files.
- No content rewrite of prompt text inside `logs/prompts_log.md`.
- No structural cleanup that deletes evidence.
- Keep markdown simple and copy-friendly.
- Prefer consistency with the style already used in `templates/hw01-main-report-template.md` and the current AI-02 template.

## File Plan
- `templates/ai-02-ai-audit-report-template.md` — make the template cleaner and more consistent.
- `ai-02-ai-audit-report-template.md` — mirror the same cleaned template so both copies stay in sync.
- `logs/prompts_log.md` — normalize heading levels, spacing, and prompt/output section layout.

## Template Structure Plan
Each AI audit entry keeps these sections:
1. Prompt + Tool
2. Full AI Output
3. Verdict
4. Reasoning
5. Student Fix

Formatting adjustments:
- keep concise instructional bullets,
- keep fenced blocks for verbatim text placeholders,
- keep repeatable entry separators,
- keep end summary section for overall AI accuracy.

## Prompt Log Structure Plan
For each logged item in `logs/prompts_log.md`:
- use a consistent numbered heading,
- keep `## Prompt` and `## Output` subsections when present,
- place timestamps on their own line under the subsection,
- preserve images, quoted prompts, and generated markdown exactly as content,
- use blank lines consistently so the file is easier to scan and copy from.

## Validation
Before completion, verify:
- both AI-02 files match,
- the AI-02 template remains a template, not a partially filled report,
- `logs/prompts_log.md` keeps the same prompt content,
- no screenshot references are removed,
- markdown renders with clearer section separation.

## Acceptance Criteria
- Both AI-02 files are synchronized.
- The AI-02 template is cleaner but semantically unchanged.
- `logs/prompts_log.md` is easier to read and copy from.
- Prompt text remains intact.
- No unrelated files are modified.
