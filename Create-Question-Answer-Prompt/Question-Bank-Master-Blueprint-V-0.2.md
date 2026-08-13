<!--
================================================================
  QUESTION-BANK BUILDER — MASTER BLUEPRINT  ·  v2.0 (PRO)
  Source pattern: COMS Unit 3 — Introduction to C
  (Basic Structure book + Operators book)
  Author: Rumman Ansari  ·  https://rummanansari.com
  Reusable for: C · Python · Java · MySQL · COMA/COMS chapters
================================================================
-->

# 📗 Question-Bank Builder — Master Blueprint **v2.0 (PRO)**

> **What this is:** A single, production-grade specification that reproduces the exact look and feel of the *Introduction to C* books — then upgrades it with stricter rules, cleaner formatting standards, and **12 extra features** (Bloom mapping, difficulty tags, marking scheme, answer-key grids, quality gates, accessibility, LaTeX/HTML/Word templates, and more).
>
> **Workflow:** Fill content against these rules → run the **Quality Gate (§13)** → export to **PDF / Word / HTML**.

---

## 📑 Table of Contents

1. [Global Rules](#1-global-rules)
2. [Document Anatomy](#2-document-anatomy)
3. [Question Section Summary](#3-question-section-summary)
4. [The 16 Question Types](#4-the-16-question-types)
5. [Balance Matrix (33·33·34)](#5-balance-matrix)
6. [Difficulty & Bloom Mapping ⭐NEW](#6-difficulty--bloom-mapping)
7. [Uniqueness / No-Duplicate Engine](#7-uniqueness-engine)
8. [Formatting Standards ⭐UPGRADED](#8-formatting-standards)
9. [Marking Scheme & Timing ⭐NEW](#9-marking-scheme--timing)
10. [Answer-Key Grid ⭐NEW](#10-answer-key-grid)
11. [Accessibility & Bilingual Rules ⭐NEW](#11-accessibility--bilingual-rules)
12. [Ready-to-Use Templates (MD/LaTeX/HTML/Word)](#12-ready-to-use-templates)
13. [Quality Gate Checklist ⭐NEW](#13-quality-gate-checklist)
14. [Revision Sheet & Exam Tips ⭐NEW](#14-revision-sheet--exam-tips)
15. [Export Commands](#15-export-commands)

---

## 1. Global Rules

| # | Rule | Requirement | Severity |
|---|------|-------------|:--------:|
| R1 | **Total questions** | Exactly **100** per book | 🔴 Must |
| R2 | **Level split** | **Basic 33 · Intermediate 33 · Advanced 34** | 🔴 Must |
| R3 | **Uniqueness** | Zero duplicates across all levels (stem + options + answer) | 🔴 Must |
| R4 | **Type coverage** | All **16 types** appear in **every** level | 🔴 Must |
| R5 | **Bilingual** | Bangla + English stems; technical keywords stay English | 🔴 Must |
| R6 | **Type label** | Prefix each Q with `Type: <name>` | 🟠 Should |
| R7 | **Two-digit numbering** | Answers: `01 … 34` | 🟠 Should |
| R8 | **Explanations** | 2–4 lines, *why correct + why others wrong* | 🔴 Must |
| R9 | **Verification code** | Runnable C snippet + **Output** wherever computable | 🟠 Should |
| R10 | **Progressive difficulty** | Recall → Apply → Analyse/Evaluate | 🟠 Should |
| R11 | **One correct key** | Single-answer Qs have exactly 1 correct; Multi ≥2 | 🔴 Must |
| R12 | **Distractor quality** | Every wrong option must be *plausible*, not filler ⭐NEW | 🟠 Should |
| R13 | **Answer distribution** | Correct answers spread ~evenly across A/B/C/D ⭐NEW | 🟡 Nice |
| R14 | **Traceable topic tag** | Each Q tagged to a syllabus subtopic ⭐NEW | 🟡 Nice |

---

## 2. Document Anatomy

Fixed section order (do not reorder):

1. **Cover header** — `Class · Subject · Chapter` line
2. **Title block table** — Unit no. · title · *Topics Covered* · author · website
3. **এই ডকুমেন্ট কীভাবে ব্যবহার করবে** (How to use)
4. **প্রস্তাবিত অধ্যয়নপথ** (Suggested Study Path — 4 steps)
5. **Table of Contents** (1.1–1.6)
6. **প্রশ্ন বিভাগের সারাংশ** (Summary table)
7. **⭐ Legend & Icon key** *(NEW — explains difficulty stars, type badges)*
8. **Basic Level** — Questions → Answers & Explanations
9. **Intermediate Level** — Questions → Answers & Explanations
10. **Advanced Level** — Questions → Answers & Explanations
11. **⭐ Answer-Key Grid** *(NEW — one-glance table)*
12. **⭐ Revision Sheet + Exam Tips** *(NEW)*
13. **শেষ যাচাই নোট** (Final verification note) + page footer

---

## 3. Question Section Summary

| লেভেল (Level) | পরিসর (Range) | মোট (Total) | নম্বর (Marks) | সময় (Time) |
|---------------|--------------|:-----------:|:-------------:|:-----------:|
| বেসিক (Basic) | 1–33 | **33** | 33 | ~25 min |
| ইন্টারমিডিয়েট (Intermediate) | 1–33 | **33** | 33 | ~30 min |
| অ্যাডভান্সড (Advanced) | 1–34 | **34** | 34 | ~35 min |
| **মোট (Total)** | — | **100** | **100** | **~90 min** |

---

## 4. The 16 Question Types

> v2 adds **#16 Case-Study / Comprehension** (a shared passage/code with 2–3 sub-questions).

| # | Type | Tests | Option Pattern |
|---|------|-------|----------------|
| 1 | Single Correct Answer | One fact | A–D, 1 correct |
| 2 | Multiple Correct Answers | Several facts | A–D, ≥2 correct |
| 3 | True/False | Boolean recall | True · False |
| 4 | Yes/No | Boolean concept | Yes · No |
| 5 | Fill in the Blank | Missing term | A–D |
| 6 | Numerical MCQ | Computed value | A–D numbers |
| 7 | Statement-Based MCQ | Judge I/II/III | A–D combos |
| 8 | Assertion & Reason | Cause–effect | A–D standard |
| 9 | Match the Following | Pair columns | A–D mappings |
| 10 | Sequence / Ordering | Correct order | A–D orders |
| 11 | Best Answer | Most-appropriate | A–D |
| 12 | Scenario-Based MCQ | Applied situation | A–D |
| 13 | Image / Diagram-Based | Read code/diagram | A–D |
| 14 | Negative (EXCEPT/NOT) | Odd-one-out | A–D |
| 15 | Hotspot / Interactive | Identify code part | A–D |
| 16 | **Case-Study / Comprehension ⭐NEW** | Passage + linked Qs | shared stem, A–D each |

**Reusable Assertion–Reason key:**
```
A. Assertion ও Reason সত্য এবং Reason সঠিক ব্যাখ্যা
B. উভয়ই সত্য কিন্তু Reason সঠিক ব্যাখ্যা নয়
C. Assertion সত্য কিন্তু Reason মিথ্যা
D. Assertion মিথ্যা কিন্তু Reason সত্য
```

---

## 5. Balance Matrix

> All 16 types in all 3 levels; nothing over-used; sums lock to **33 · 33 · 34 = 100**.

| # | Type | Basic | Interm. | Adv. | **Σ** |
|---|------|:---:|:---:|:---:|:---:|
| 1 | Single Correct | 3 | 3 | 2 | 8 |
| 2 | Multiple Correct | 2 | 2 | 2 | 6 |
| 3 | True/False | 2 | 2 | 2 | 6 |
| 4 | Yes/No | 2 | 2 | 2 | 6 |
| 5 | Fill in the Blank | 2 | 2 | 2 | 6 |
| 6 | Numerical | 2 | 3 | 4 | 9 |
| 7 | Statement-Based | 2 | 2 | 2 | 6 |
| 8 | Assertion & Reason | 2 | 2 | 2 | 6 |
| 9 | Match the Following | 2 | 2 | 2 | 6 |
| 10 | Sequence / Ordering | 2 | 2 | 2 | 6 |
| 11 | Best Answer | 2 | 2 | 2 | 6 |
| 12 | Scenario-Based | 2 | 2 | 3 | 7 |
| 13 | Image / Diagram | 2 | 1 | 2 | 5 |
| 14 | Negative (EXCEPT/NOT) | 2 | 2 | 2 | 6 |
| 15 | Hotspot / Interactive | 2 | 2 | 1 | 5 |
| 16 | Case-Study ⭐ | 2 | 2 | 2 | 6 |
| | **Level total** | **33** | **33** | **34** | **100** |

✅ 16 types × 3 levels · ✅ 33+33+34 = 100 · ✅ max share = 9%.

---

## 6. Difficulty & Bloom Mapping
> ⭐ NEW feature — tag every question so the book is pedagogically balanced.

**Difficulty stars (put beside the Type label):**
`★☆☆` Easy · `★★☆` Medium · `★★★` Hard

**Target difficulty mix per level**

| Level | ★☆☆ Easy | ★★☆ Medium | ★★★ Hard |
|-------|:---:|:---:|:---:|
| Basic | 70% | 25% | 5% |
| Intermediate | 30% | 55% | 15% |
| Advanced | 10% | 45% | 45% |

**Bloom's taxonomy alignment**

| Level | Dominant Bloom verbs |
|-------|----------------------|
| Basic | Remember, Understand (*define, identify, recall*) |
| Intermediate | Apply, Analyse (*compute, compare, use*) |
| Advanced | Analyse, Evaluate (*predict, justify, debug*) |

---

## 7. Uniqueness Engine
> No-duplicate guarantee — the core of your request.

- **U1 Stem uniqueness** — no repeated sentence/fact, even across levels.
- **U2 Concept spread** — a concept may reappear *only via a different type* (e.g. `%` once Numerical, once Match).
- **U3 Option freshness** — never reuse an identical A–D set; reshuffle distractors.
- **U4 Answer scan** — dedup key = `hash(stem + correct + sorted(options))`.
- **U5 Numeric variety** — vary operands so no two computations match.
- **U6 Cross-book check ⭐NEW** — when building a series, dedup against sibling chapters too.

**Automated dedup (optional Python):**
```python
seen=set()
for q in questions:
    key=(q["stem"].strip().lower(), q["answer"], tuple(sorted(q["options"])))
    assert key not in seen, f"Duplicate: {q['stem'][:40]}"
    seen.add(key)
print("✅ All unique:", len(seen))
```

---

## 8. Formatting Standards
> ⭐ UPGRADED — tighter, more consistent, print-safe.

**F1 — Question block**
```
**Type: <Name>**  `★★☆`  <sub-topic tag>
N. <Bangla stem + English keywords>?
A. <option>
B. <option>
C. <option>
D. <option>
```

**F2 — Answer block (standard)**
```
0N. **উত্তর: <Letter>. <correct option>**
ব্যাখ্যা: <why correct — 2 lines>. <why key distractor wrong — 1 line>.
```

**F3 — Answer block (with verification)**
```
0N. **উত্তর: <Letter>. <correct option>**
ব্যাখ্যা: <explanation>.
**যাচাই করার প্রোগ্রাম:**
`​`​`c
#include <stdio.h>
int main() {
    ...
    return 0;
}
`​`​`
**Output:** <value>
```

**F4 — Typography rules**
- Bold **only** the `Type`, `উত্তর`, and section headings.
- Code always in fenced blocks with language hint (```c / ```python).
- Escape sequences shown literally: `\n`, `\t` (never rendered).
- Options always A–D on separate lines — never inline.
- One blank line between questions; **no** blank line inside an option set.

**F5 — Numbering discipline**
- Questions: `1 … 34` (single digit ok).
- Answers: **two-digit** `01 … 34`.
- Match items: `(i)(ii)(iii)` ↔ `(a)(b)(c)`.

**F6 — Colour/emphasis (Word/HTML only)**
- Correct option: green bold. Section headers: navy. Code: monospace grey box.

---

## 9. Marking Scheme & Timing
> ⭐ NEW

| Item | Rule |
|------|------|
| Marks per Q | **+1** correct |
| Negative marking | **0** (or −0.25 for exam mode) |
| Multiple-correct | All-or-nothing (partial = 0) |
| Case-study | 1 mark per sub-question |
| Pass mark | ≥ 40 / 100 |
| Suggested total time | **90 min** (see §3) |
| Grade bands | A ≥85 · B 70–84 · C 55–69 · D 40–54 · F <40 |

---

## 10. Answer-Key Grid
> ⭐ NEW — a one-glance key at the book's end (fill after authoring).

**Basic (1–33)**

| Q | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 |
|---|---|---|---|---|---|---|---|---|---|----|----|
| Ans | | | | | | | | | | | |

| Q | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 | 21 | 22 |
|---|----|----|----|----|----|----|----|----|----|----|----|
| Ans | | | | | | | | | | | |

| Q | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 32 | 33 |
|---|----|----|----|----|----|----|----|----|----|----|----|
| Ans | | | | | | | | | | | |

*(Duplicate this grid for Intermediate 1–33 and Advanced 1–34.)*

---

## 11. Accessibility & Bilingual Rules
> ⭐ NEW

- **A1 Font** — use a Bangla-complete font (e.g. *Noto Sans Bengali* / *SutonnyOMJ*) so juktakkhor/conjuncts render.
- **A2 Contrast** — text vs background ≥ 4.5:1 (WCAG AA).
- **A3 Alt text** — every Image-Based Q describes its code/diagram in words too (screen-reader safe).
- **A4 No colour-only cues** — never rely on colour alone to mark the answer; also bold/label it.
- **A5 Language parity** — Bangla and English must carry the *same* meaning; keep code tokens English.
- **A6 Selectable code** — code stays as text (not screenshots) so it's copyable.

---

## 12. Ready-to-Use Templates

### 12a — Markdown headings (copy verbatim)
```
### বেসিক লেভেল প্রশ্ন (Basic Level Questions)
### বেসিক লেভেল উত্তর ও ব্যাখ্যা (Basic Level Answers and Explanations)
### ইন্টারমিডিয়েট লেভেল প্রশ্ন (Intermediate Level Questions)
### ইন্টারমিডিয়েট লেভেল উত্তর ও ব্যাখ্যা (Intermediate Level Answers and Explanations)
### অ্যাডভান্সড লেভেল প্রশ্ন (Advanced Level Questions)
### অ্যাডভান্সড লেভেল উত্তর ও ব্যাখ্যা (Advanced Level Answers and Explanations)
```

### 12b — LaTeX (XeLaTeX, Bangla-ready)
```latex
\documentclass[12pt]{article}
\usepackage{fontspec}
\usepackage{polyglossia}
\setmainlanguage{bengali}
\setotherlanguage{english}
\newfontfamily\bengalifont{Noto Sans Bengali}
\usepackage{listings, xcolor, enumitem}
\lstset{basicstyle=\ttfamily\small, backgroundcolor=\color{gray!10},
        frame=single, language=C}
\begin{document}
\section*{বেসিক লেভেল প্রশ্ন (Basic Level Questions)}
\textbf{Type: Single Correct Answer} \hfill $\star\star\star$

1. <stem>?
\begin{enumerate}[label=\Alph*.]
  \item option \item option \item option \item option
\end{enumerate}
\end{document}
```

### 12c — HTML/CSS (matches your `.ac-body` style)
```html
<div class="ac-body">
  <div class="q-card" data-type="Single Correct" data-diff="medium">
    <span class="q-type">Type: Single Correct Answer</span>
    <span class="q-diff">★★☆</span>
    <p class="q-stem"><b>1.</b> <stem>?</p>
    <ol type="A" class="q-opts">
      <li>option</li><li>option</li><li>option</li><li>option</li>
    </ol>
  </div>
  <div class="ans-card">
    <p><b>উত্তর:</b> A. correct — <span class="exp">ব্যাখ্যা…</span></p>
    <pre class="code"><code class="language-c">#include &lt;stdio.h&gt;
int main(){ return 0; }</code></pre>
    <p><b>Output:</b> value</p>
  </div>
</div>

<style>
.ac-body{font-family:'Noto Sans Bengali',sans-serif;line-height:1.7}
.q-card{border:1px solid #ddd;border-radius:10px;padding:14px;margin:12px 0}
.q-type{background:#0d47a1;color:#fff;padding:2px 8px;border-radius:6px;font-size:.85rem}
.q-diff{float:right;color:#e65100}
.ans-card{background:#f1f8e9;border-left:4px solid #33691e;padding:12px;border-radius:8px}
.code{background:#263238;color:#eee;padding:10px;border-radius:8px;overflow:auto}
</style>
```

### 12d — Word (styling recipe)
- Heading 1 = navy, 16pt · Heading 3 = level titles · Body = 12pt.
- Insert a real **Table of Contents** (References → TOC) and *refresh* before PDF export.

---

## 13. Quality Gate Checklist
> ⭐ NEW — run before you ship. All must be ✅.

```
STRUCTURE
[ ] 33 / 33 / 34 = 100 exactly
[ ] All 16 types present in each level (matches §5)
[ ] Section order matches §2

UNIQUENESS
[ ] Dedup scan passed (U1–U6)
[ ] No repeated numeric operands
[ ] Same concept only via different type

ANSWERS
[ ] Every Q has exactly one key (multi ≥2)
[ ] A/B/C/D correct-answer spread ~even (§R13)
[ ] Every explanation states why-correct + why-wrong
[ ] All verification code compiles & Output matches

FORMAT
[ ] Two-digit answer numbering
[ ] Code in fenced blocks with language hint
[ ] Escape sequences shown literally
[ ] Difficulty star on every question

BILINGUAL / A11Y
[ ] Bangla + English parity
[ ] Bangla font renders conjuncts
[ ] Image Qs have alt-text description
[ ] Contrast ≥ 4.5:1

FINALIZE
[ ] Answer-Key Grid filled (§10)
[ ] TOC refreshed · page numbers updated
```

---

## 14. Revision Sheet & Exam Tips
> ⭐ NEW — add near the end of each book.

**Quick-revision card (example, C):**
- `;` terminates a statement · `main()` starts execution.
- `%d` int · `%f` float · `%c` char · `%s` string.
- `*  /  %` before `+  -` · assignment `=` is right-to-left.
- `++a` (pre) increments then uses · `a++` (post) uses then increments.
- Comma operator returns the **last** expression's value.

**Exam tips:**
1. Read **EXCEPT/NOT** questions twice — the odd one out is the answer.
2. For Assertion–Reason, test each statement *independently* first.
3. In Numerical Qs, watch integer division truncation.
4. Eliminate 2 distractors first, then decide.
5. Attempt easy (★☆☆) questions first to bank marks.

---

## 15. Export Commands

```bash
# Markdown → PDF (best Bangla support)
pandoc Question-Bank-Master-Blueprint-v2.md -o book.pdf \
  --pdf-engine=xelatex -V mainfont="Noto Sans Bengali" --toc

# Markdown → DOCX
pandoc Question-Bank-Master-Blueprint-v2.md -o book.docx --toc
```
- **VS Code:** “Markdown PDF” extension → *Export (pdf)*.
- **Word route:** paste MD → Word → refresh TOC → *Save As → PDF*.

---

*Blueprint v2.0 (PRO) for Rumman Ansari · rummanansari.com · Reusable across C · Python · Java · MySQL · COMA/COMS chapters.*
