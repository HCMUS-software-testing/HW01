# AI Audit Template and Prompt Log Format Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Synchronize both AI-02 markdown templates and reformat `logs/prompts_log.md` for readability without changing prompt content.

**Architecture:** Treat `templates/ai-02-ai-audit-report-template.md` as the canonical AI-02 content, then mirror the same cleaned markdown into `ai-02-ai-audit-report-template.md`. Reformat `logs/prompts_log.md` by normalizing markdown headings, blank lines, and prompt/output section layout while preserving the existing prompt text, screenshots, and generated content.

**Tech Stack:** Markdown, PowerShell for verification, git diff for review

---

### Task 1: Normalize the AI-02 template content

**Files:**
- Modify: `templates/ai-02-ai-audit-report-template.md`
- Modify: `ai-02-ai-audit-report-template.md`

- [ ] **Step 1: Replace the template body in `templates/ai-02-ai-audit-report-template.md` with the cleaned canonical version**

```md
# AI-02 — AI Audit Report Template (5 Sections per Artifact)

> Mandatory for AI-assisted artifacts. One batch from one prompt = one artifact entry.

## Entry A-01

### 1) Prompt + Tool
- Tool name: `<Claude/ChatGPT/Gemini/Copilot/Cursor/...>`
- Timestamp: `<HH:MM dd/mm/yyyy>`
- Full prompt (verbatim):

```text
<paste full prompt>
```

### 2) Full AI Output
- Paste full output verbatim OR attach red-bordered annotated screenshot.
- No paraphrase, no summary.

```text
<paste full AI output>
```

### 3) Verdict
- Verdict: `VALID` | `INVALID` | `INCOMPLETE`
- Reason:

`<reason grounded in ISTQB/course materials>`

### 4) Reasoning (2–5 sentences)
`<cite matching slide/ISTQB section and explain why verdict is correct>`

### 5) Student Fix
- Corrected artifact:

```text
<paste corrected version>
```

- What changed:
`<bullet list of edits made by student>`

---

## Entry A-02
(Repeat same 5-section block)

## Entry A-03
(Repeat same 5-section block)

## Entry A-04
(Repeat same 5-section block)

## Entry A-05
(Repeat same 5-section block)

---

## AI Accuracy Summary (required at end)

- Total artifact entries: `<n>`
- VALID: `<count>` (`<%>`)
- INVALID: `<count>` (`<%>`)
- INCOMPLETE: `<count>` (`<%>`)

### Conclusion
- When AI should be used for this HW:
`<...>`
- When AI should not be used for this HW:
`<...>`
```

- [ ] **Step 2: Mirror the same canonical body into `ai-02-ai-audit-report-template.md`**

```powershell
Copy-Item "C:\Users\tkin\Documents\software-testing\HW01\templates\ai-02-ai-audit-report-template.md" "C:\Users\tkin\Documents\software-testing\HW01\ai-02-ai-audit-report-template.md" -Force
```

Expected: root AI-02 file matches template copy exactly.

- [ ] **Step 3: Verify both files are identical**

```powershell
Get-FileHash "C:\Users\tkin\Documents\software-testing\HW01\templates\ai-02-ai-audit-report-template.md"; Get-FileHash "C:\Users\tkin\Documents\software-testing\HW01\ai-02-ai-audit-report-template.md"
```

Expected: both hashes are the same.

- [ ] **Step 4: Review the diff for AI-02 only**

```powershell
git diff -- "templates/ai-02-ai-audit-report-template.md" "ai-02-ai-audit-report-template.md"
```

Expected: only formatting/template-cleanup changes appear.

- [ ] **Step 5: Commit**

```powershell
git add "templates/ai-02-ai-audit-report-template.md" "ai-02-ai-audit-report-template.md"
git commit -m "fix: normalize ai audit report templates"
```

Expected: one focused commit for the AI-02 sync.

### Task 2: Reformat the prompt log without changing prompt text

**Files:**
- Modify: `logs/prompts_log.md`

- [ ] **Step 1: Rewrite `logs/prompts_log.md` into a consistent markdown layout**

Apply these formatting rules throughout the file:

```md
# 1. Requirements analysis

## Prompt
15:27 01/06/2026

![alt text](image-5.png)

## Output

![alt text](image-6.png)
![alt text](image-7.png)
![alt text](image-8.png)
```

And for quoted prompt text blocks, preserve the exact prompt text while separating it cleanly from screenshots, for example:

```md
## Prompt
15:38 01/06/2026

"Use document-skills, from pdf files in requirements/ folder, create all the template markdowns that are needed in this project. Place the templates in the folder templates/ "

![alt text](image.png)
```

And for generated markdown output blocks, preserve the full generated content under `## Output` without paraphrase.

- [ ] **Step 2: Verify prompt text is still present verbatim in key entries**

```powershell
Select-String -Path "C:\Users\tkin\Documents\software-testing\HW01\logs\prompts_log.md" -Pattern "Use document-skills, from pdf files in requirements/ folder, create all the template markdowns that are needed in this project. Place the templates in the folder templates/ ","In requirement 01 of report.md, for each job, based on the job description, rewrite the Required skills and AI Impact Analysis.","The table in section 3.3 Test Cases of report.md. Ensure in each sell, between sentence, add a breakline <br>."
```

Expected: all three prompt strings are still found exactly once each.

- [ ] **Step 3: Review the prompt log diff**

```powershell
git diff -- "logs/prompts_log.md"
```

Expected: content is reorganized by spacing/headings only; prompt wording is unchanged.

- [ ] **Step 4: Commit**

```powershell
git add "logs/prompts_log.md"
git commit -m "fix: reformat prompt log markdown"
```

Expected: one focused commit for prompt log formatting.

### Task 3: Final verification

**Files:**
- Modify: none
- Verify: `templates/ai-02-ai-audit-report-template.md`
- Verify: `ai-02-ai-audit-report-template.md`
- Verify: `logs/prompts_log.md`

- [ ] **Step 1: Run a final diff summary**

```powershell
git diff --stat
```

Expected: only three files changed.

- [ ] **Step 2: Open the final content for a quick spot check**

```powershell
Get-Content "C:\Users\tkin\Documents\software-testing\HW01\templates\ai-02-ai-audit-report-template.md" | Select-Object -First 40
Get-Content "C:\Users\tkin\Documents\software-testing\HW01\logs\prompts_log.md" | Select-Object -First 80
```

Expected: AI-02 starts with the cleaned template header; prompt log starts with a normalized first entry.

- [ ] **Step 3: Commit**

```powershell
git add "templates/ai-02-ai-audit-report-template.md" "ai-02-ai-audit-report-template.md" "logs/prompts_log.md"
git commit -m "fix: align ai audit template and prompt log format"
```

Expected: final clean commit if earlier task commits were skipped.
