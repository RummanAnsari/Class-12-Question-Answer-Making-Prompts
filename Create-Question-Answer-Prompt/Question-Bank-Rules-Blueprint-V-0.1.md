<!--
============================================================
  QUESTION-BANK BUILDER — MASTER RULES / BLUEPRINT
  Source pattern: COMS Unit 3 — Introduction to C
  (Basic Structure book + Operators book)
  Author style: Rumman Ansari | https://rummanansari.com
============================================================
-->

# 📘 Question-Bank Builder — Master Rules & Blueprint

> **Purpose:** A single specification (“rules file”) that reproduces the exact look, structure, and question mix of the *Introduction to C* books, but rebuilt to a **33 / 33 / 34 = 100** layout with **unique, non-duplicate** questions and a **balanced spread of every question type**.
>
> **Use this file to generate → convert to PDF** (Markdown → PDF via Pandoc/print, or paste into Word and export).

---

## 1. 🎯 Global Rules (apply to every book)

| # | Rule | Requirement |
|---|------|-------------|
| R1 | **Total questions** | Exactly **100** per book |
| R2 | **Level split** | **Basic 33 · Intermediate 33 · Advanced 34** |
| R3 | **Uniqueness** | **No duplicate questions** — every stem, option set, and answer must be unique across *all* levels |
| R4 | **Type balance** | Every one of the **15 question types** must appear in **each** level (see §5 matrix) |
| R5 | **Bilingual** | Question stems in **Bangla + English** (technical keywords stay in English) |
| R6 | **Type label** | Every question is prefixed with **`Type: <name>`** |
| R7 | **Answer numbering** | Two-digit style: `01, 02, 03 … 33/34` |
| R8 | **Explanations** | Each answer = correct option **+ a 2–4 line explanation** |
| R9 | **Verification code** | (Operators-style books) add a runnable C snippet + **Output** where a value can be computed |
| R10 | **Progressive difficulty** | Basic → recall · Intermediate → application · Advanced → analysis/evaluation |

---

## 2. 🧱 Document Anatomy (fixed section order)

1. **Cover header** — Class / Subject / Chapter line
2. **Title block table** — Unit no., title, *Topics Covered*, author, website
3. **“এই ডকুমেন্ট কীভাবে ব্যবহার করবে”** (How to use this document)
4. **প্রস্তাবিত অধ্যয়নপথ** (Suggested Study Path) — 4 numbered steps
5. **Table of Contents** (1.1 – 1.6)
6. **প্রশ্ন বিভাগের সারাংশ** (Question Section Summary table)
7. **Basic Level — Questions → Answers & Explanations**
8. **Intermediate Level — Questions → Answers & Explanations**
9. **Advanced Level — Questions → Answers & Explanations**
10. **শেষ যাচাই নোট** (Final verification note) + page footer

---

## 3. 📊 Question Section Summary (paste-ready table)

| লেভেল (Level) | প্রশ্ন পরিসর (Range) | মোট প্রশ্ন (Total) |
|---------------|--------------------|--------------------|
| বেসিক লেভেল (Basic Level) | 1–33 | **33** |
| ইন্টারমিডিয়েট লেভেল (Intermediate Level) | 1–33 | **33** |
| অ্যাডভান্সড লেভেল (Advanced Level) | 1–34 | **34** |
| **মোট (Total)** | — | **100** |

---

## 4. 🧩 The 15 Question Types (definitions + template)

| # | Type | What it tests | Option pattern |
|---|------|---------------|----------------|
| 1 | **Single Correct Answer** | One correct fact | A–D, 1 correct |
| 2 | **Multiple Correct Answers** | 2+ correct facts | A–D, ≥2 correct |
| 3 | **True/False** | Boolean recall | A. True · B. False |
| 4 | **Yes/No** | Boolean concept | A. Yes · B. No |
| 5 | **Fill in the Blank** | Missing term | A–D fill options |
| 6 | **Numerical MCQ** | Computed value | A–D numbers |
| 7 | **Statement-Based MCQ** | Judge I/II/III statements | A–D combos |
| 8 | **Assertion and Reason** | Cause–effect logic | A–D standard 4 |
| 9 | **Match the Following** | Pair (i)(ii)(iii)→(a)(b)(c) | A–D mappings |
| 10 | **Sequence / Ordering** | Correct order of steps | A–D orders |
| 11 | **Best Answer** | Most-appropriate choice | A–D, best 1 |
| 12 | **Scenario-Based MCQ** | Applied real situation | A–D |
| 13 | **Image / Diagram-Based MCQ** | Read a code/diagram | A–D |
| 14 | **Negative MCQ (EXCEPT/NOT)** | Odd-one-out | A–D |
| 15 | **Hotspot / Interactive MCQ** | Identify a code part | A–D |

### Standard option key for Assertion–Reason (reuse verbatim)
```
A. Assertion ও Reason সত্য এবং Reason সঠিক ব্যাখ্যা
B. উভয়ই সত্য কিন্তু Reason সঠিক ব্যাখ্যা নয়
C. Assertion সত্য কিন্তু Reason মিথ্যা
D. Assertion মিথ্যা কিন্তু Reason সত্য
```

---

## 5. ⚖️ Balance Matrix — how the 100 questions are split

> Goal: every type appears in every level, no type over-used, `Single Correct` no longer dominates.

| # | Type | Basic (33) | Interm. (33) | Adv. (34) | **Total** |
|---|------|:---:|:---:|:---:|:---:|
| 1 | Single Correct Answer | 3 | 3 | 3 | 9 |
| 2 | Multiple Correct Answers | 2 | 2 | 2 | 6 |
| 3 | True/False | 2 | 2 | 2 | 6 |
| 4 | Yes/No | 2 | 2 | 2 | 6 |
| 5 | Fill in the Blank | 2 | 2 | 2 | 6 |
| 6 | Numerical MCQ | 2 | 3 | 4 | 9 |
| 7 | Statement-Based MCQ | 2 | 2 | 2 | 6 |
| 8 | Assertion and Reason | 2 | 2 | 2 | 6 |
| 9 | Match the Following | 2 | 2 | 2 | 6 |
| 10 | Sequence / Ordering | 2 | 2 | 2 | 6 |
| 11 | Best Answer | 2 | 2 | 2 | 6 |
| 12 | Scenario-Based MCQ | 2 | 2 | 3 | 7 |
| 13 | Image / Diagram-Based MCQ | 2 | 2 | 2 | 6 |
| 14 | Negative MCQ (EXCEPT/NOT) | 2 | 2 | 2 | 6 |
| 15 | Hotspot / Interactive MCQ | 2 | 1 | 2 | 5 |
| | **Level total** | **33** | **33** | **34** | **100** |

✅ All 15 types present in all 3 levels · ✅ 33 + 33 + 34 = 100 · ✅ No single type exceeds 9.

---

## 6. 🚫 No-Duplicate / Uniqueness Rules

- **U1 — Stem uniqueness:** No two questions may share the same sentence or ask the same fact twice (even across levels).
- **U2 — Concept spread:** A concept (e.g. `%` modulus) may appear again *only* through a **different question type** (e.g. once as Numerical, once as Match) — never the same phrasing.
- **U3 — Option freshness:** Distractors must be re-shuffled; do not reuse identical A–D sets.
- **U4 — Answer-key check:** Before finalizing, run a duplicate scan on: (stem text) + (correct answer) + (option set).
- **U5 — Numeric variety:** For Numerical MCQs, vary the operands so no two computations are identical.

**Quick dedup checklist:**
```
[ ] Every stem unique?          [ ] No repeated option sets?
[ ] Same concept ≠ same type?   [ ] Numeric operands varied?
[ ] Type-count matches §5?      [ ] 33 / 33 / 34 confirmed?
```

---

## 7. ✍️ Formatting Rules for Questions & Answers

**Question block template**
```
**Type: <Type Name>**N. <Bangla + English stem>?
A. <option>
B. <option>
C. <option>
D. <option>
```

**Answer block template**
```
0N. **উত্তর: <Letter>. <correct option>**
ব্যাখ্যা: <2–4 line bilingual explanation>.
```

**Answer block template (with verification — Operators-style)**
```
0N. **উত্তর: <Letter>. <correct option>**
ব্যাখ্যা: <explanation>.
**যাচাই করার প্রোগ্রাম:**
#include <stdio.h>
int main() {
    ...
    return 0;
}
**Output:** <value>
```

---

## 8. 🏷️ Section Headings (copy verbatim)

```
### বেসিক লেভেল প্রশ্ন (Basic Level Questions)
### বেসিক লেভেল উত্তর ও ব্যাখ্যা (Basic Level Answers and Explanations)
### ইন্টারমিডিয়েট লেভেল প্রশ্ন (Intermediate Level Questions)
### ইন্টারমিডিয়েট লেভেল উত্তর ও ব্যাখ্যা (Intermediate Level Answers and Explanations)
### অ্যাডভান্সড লেভেল প্রশ্ন (Advanced Level Questions)
### অ্যাডভান্সড লেভেল উত্তর ও ব্যাখ্যা (Advanced Level Answers and Explanations)
```

**Final note (place at very end):**
> শেষ যাচাই নোট: উত্তর নম্বরের স্টাইল একরূপ রাখার জন্য সব উত্তর বিভাগে দুই অঙ্কের নম্বরধারা ব্যবহার করা উচিত। Word-এ final formatting করার পরে Table of Contents refresh করে page number আপডেট করে নাও।

---

## 9. 🖨️ Convert this MD → PDF

- **Pandoc + XeLaTeX (best for Bangla):**
  ```bash
  pandoc Question-Bank-Rules-Blueprint.md -o output.pdf \
    --pdf-engine=xelatex -V mainfont="Noto Sans Bengali"
  ```
- **VS Code:** “Markdown PDF” extension → *Export (pdf)*.
- **Word route:** paste MD → Word → **Save As → PDF** (then refresh the Table of Contents).

---

*Blueprint generated for Rumman Ansari · rummanansari.com · Reusable for any COMS/COMA chapter (C, Python, MySQL, Java).*
