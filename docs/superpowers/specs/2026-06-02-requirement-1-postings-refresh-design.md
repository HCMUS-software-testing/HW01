# Requirement 1 Postings Refresh Design

## Overview
Update Requirement 1 in `report.md` for postings 02–10 using Posting 01 as the formatting reference.

## Requirements
- Reformat postings 02–10 to match the Posting 01 section pattern.
- Use `chrome-devtools-mcp@latest` to open each live posting and copy the full visible job description.
- Capture a fresh screenshot for each posting and show the user's username/display name if visible.
- Rewrite `Required Skills` for each posting from the live description.
- Rewrite `AI Impact Analysis (1–2 sentences)` for each posting from the role context.
- Normalize posting dates to `dd/mm/yyyy`.

## Constraints
- Keep the work inside existing project paths.
- Update `report.md` directly.
- Save refreshed screenshots in `req1-images/`.
- Preserve Requirement 1 overall structure.
- Prefer exact visible page content over prior summaries.

## Data Capture Plan
1. Open postings 02–10 one by one with Chrome DevTools MCP.
2. Expand hidden content such as `See more` before copying.
3. Record posting metadata needed for the report, especially posting date.
4. Capture the full visible description text.
5. Take a fresh evidence screenshot for each posting.

## Report Structure Plan
For each posting 02–10, use this shape:
- `#### 1.2.x Posting 0x`
- metadata bullets
- `**Job Description**`
- fenced code block with full copied description
- `**Required Skills**`
- `**AI Impact Analysis (1–2 sentences)**`
- `**Evidence**`

## Date Handling
- Convert relative platform dates such as `10d`, `1 week ago`, `13 hours ago`, `11 hours ago` into calendar dates in `dd/mm/yyyy`.
- Use the current session date `02/06/2026` as the reference point unless the page shows an absolute date.
- If the live page exposes a clearer absolute/published date, use that instead.

## Evidence Handling
- Keep screenshots in `req1-images/`.
- Reuse the current naming pattern when practical so report links stay predictable.
- Update image references in `report.md` if filenames change.

## Validation
Before completion, verify:
- postings 02–10 match Posting 01 structure,
- each posting contains a full copied description,
- each posting has rewritten `Required Skills`,
- each posting has rewritten `AI Impact Analysis`,
- each posting date is in `dd/mm/yyyy`,
- each posting has a fresh screenshot reference.

## Acceptance Criteria
- Requirement 1 is internally consistent.
- Posting 02–10 formatting matches Posting 01 closely.
- The report uses full live descriptions instead of short summaries.
- Evidence screenshots are refreshed.
