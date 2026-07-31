# WBCHSE Class XII COMS (Computer Science) — BANGLA Question Paper Generator (Prompt #1)

> **Subject:** Computer Science (COMS) — science stream. **Different from COMA.**
> **What this makes:** A Bangla (বাংলা) **question paper**, 70 marks, official WBCHSE pattern.
> **How to use:** Copy the "MASTER PROMPT" box, fill the `>>> FILL THIS <<<` slots, paste to any AI, then compile with **XeLaTeX + Kalpurush** on Overleaf.

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert WBCHSE (West Bengal Council of Higher Secondary Education)
exam-paper designer. Produce a COMPLETE, ready-to-compile LaTeX QUESTION PAPER
in BANGLA (বাংলা) following the EXACT specification below. Do not skip any part.

========================= WHAT I WANT =========================
1. SUBJECT      : Computer Science (COMS)   [science stream — NOT COMA]
2. CLASS        : Class XII
3. LANGUAGE     : Bangla/বাংলা  (technical terms stay in English)
4. TOTAL MARKS  : 70 (Theory)   Time: 3 Hours 15 Minutes
5. DIFFICULTY   : >>> FILL THIS <<<  (e.g., "Standard board level" / "Advanced")
6. VARIATION    : >>> FILL THIS <<<  (e.g., "Paper-1" / "Paper-2 all new questions")
7. SYLLABUS TOPICS (Class XII COMS ONLY):
   - Python Programming (data types incl. tuples & dictionary; operators;
     expressions & type conversion; errors: syntax/logical/run-time;
     flow of control; conditional & iterative statements; strings; lists;
     tuples; dictionary; modules math/random/statistics; user-defined functions;
     EXCEPTION HANDLING try-except-finally)
   - E-Commerce (E-Commerce intro/goals/functions; business models
     B2B/B2C/C2C/C2G/G2G/B2G etc; EDI - Electronic Data Interchange;
     Electronic Payment System; Internet Marketing; online shopping pros/cons)
   - DBMS (Drawbacks of legacy system; advantages; data independence; data models;
     ER Modelling incl. weak/strong entity, specialization/generalization,
     aggregation; Relational Model & Relational Algebra; Integrity Constraints;
     SQL DDL/DML, constraints, aggregate functions, group by/having, joins)
   - Foundation of Artificial Intelligence (definition & scope; AI vs human
     intelligence; ML types supervised/unsupervised/reinforcement; deep learning
     & neural networks; NLP & computer vision; SEARCH AS OPTIMIZATION:
     state space search, data-driven & goal-driven, heuristic search, BFS, DFS,
     A* search; AI applications finance/chatbots/education; AI ethics & bias)

===================== OFFICIAL PATTERN (MUST FOLLOW) =====================
GROUP A — Multiple Choice (MCQ) : 21 questions × 1 = 21 marks  (4 options each, 2 columns)
GROUP B — Short Answer          : 14 questions × 1 = 14 marks
GROUP C — Broad / Descriptive   : 7 questions given, ANSWER ANY 5, × 7 = 35 marks
                                  (each question has parts (a)(b) with a [4+3]/[3+4] split)
TOTAL = 70 marks.

- Print the official instruction line (Bangla translation):
  "সংক্ষিপ্ত ও যথাযথ উত্তরের জন্য বিশেষ নম্বর দেওয়া হবে। বানান ভুল, অপরিচ্ছন্নতা এবং
   খারাপ হস্তাক্ষরের জন্য নম্বর কাটা যাবে। প্রান্তস্থ সংখ্যাগুলি প্রশ্নের পূর্ণমান নির্দেশ করে।"
- Use Bangla numerals (১, ২, ৩ …) in headings and marks: [ ২১ × ১ = ২১ ], [ ৪ + ৩ ].
- Include COMS-specific content: at least one MCQ/short/broad on EXCEPTION HANDLING,
  one on TUPLES or DICTIONARY, one on EDI, and one on AI SEARCH (BFS/DFS/A*).

===================== FORMATTING (USE THE GOLD TEMPLATE) =====================
Use the EXACT preamble + custom commands from the "GOLD TEMPLATE" section below:
blue \groupbanner, grey {instructionbox}, auto-numbered \qlist with \Q,
2-column \opts for MCQ options, \parts for (a)(b), \qmarks for right-margin marks.
Wrap every Bangla chunk in \bn{...}. Keep tech terms (Python, SQL, EDI, A*, B2B,
code, keywords) in ENGLISH — exactly like real WBCHSE bilingual papers.

===================== COMPILER / FONT (CRITICAL) =====================
Compile with XeLaTeX (NOT pdfLaTeX / NOT LuaLaTeX) using fontspec + polyglossia
and font "Kalpurush" (full conjunct support, built into Overleaf).
Fallback font: "Noto Serif Bengali".

===================== OUTPUT =====================
- Give the FULL .tex source in ONE copy-paste code block.
- Keep the comment header stating compiler + font at the top.
- End with "প্রশ্নপত্র সমাপ্ত" and the pattern summary line.

Now generate the question paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **DIFFICULTY** | `Standard board level` · `Advanced / Pre-Board` · `Olympiad` |
| **VARIATION** | `Paper-1` · `Paper-2, all new questions` · `more code-based MCQs` |
| **EXTRAS** | `also give explained answer key` · `make an English version too` |

---

## 🏆 GOLD TEMPLATE — Bangla COMS Question Paper (XeLaTeX + Kalpurush)

```latex
% =====================================================================
%  WBCHSE  Class XII  Computer Science (COMS)
%  BENGALI (বাংলা) Question Paper -- 70 Marks
%  COMPILE WITH  :  XeLaTeX   (NOT pdfLaTeX / NOT LuaLaTeX)
%  REQUIRED FONT :  Kalpurush  (built into Overleaf; full conjunct support)
%  >>> CONFIRMED WORKING with XeLaTeX + Kalpurush <<<
% =====================================================================
\documentclass[12pt,a4paper]{article}

\usepackage[a4paper,margin=1in]{geometry}
\usepackage{fontspec}
\usepackage{polyglossia}
\usepackage{xcolor}
\usepackage{fancyhdr}
\usepackage{multicol}
\usepackage{array}
\usepackage{enumitem}

% ----- Languages -----
\setmainlanguage{english}
\setotherlanguage{bengali}

% ----- Fonts -----
\setmainfont{Latin Modern Roman}
% Kalpurush has FULL Bengali conjunct (যুক্তাক্ষর) support and is built into Overleaf.
% If Kalpurush is unavailable, replace with: Noto Serif Bengali
\newfontfamily\bengalifont{Kalpurush}[Script=Bengali]
\newcommand{\bn}[1]{{\bengalifont #1}}

% ----- Colours -----
\definecolor{sectionblue}{RGB}{0,70,140}
\definecolor{boxgray}{RGB}{230,230,230}

% ----- Header / Footer -----
\pagestyle{fancy}
\fancyhf{}
\lhead{\small WBCHSE}
\chead{\small \bn{কম্পিউটার সায়েন্স (COMS)}}
\rhead{\small \bn{দ্বাদশ শ্রেণি}}
\cfoot{\bn{পৃষ্ঠা} \thepage}
\renewcommand{\headrulewidth}{0.5pt}

% ----- Group banner -----
\newcommand{\groupbanner}[1]{%
  \vspace{0.35cm}%
  \noindent\colorbox{sectionblue}{%
    \begin{minipage}{\dimexpr\textwidth-2\fboxsep\relax}%
      \centering\color{white}\large\bfseries #1%
    \end{minipage}}\par
  \vspace{0.25cm}%
}

% ----- Instruction box -----
\newsavebox{\instrbox}
\newenvironment{instructionbox}{%
  \setlength{\fboxsep}{10pt}%
  \begin{lrbox}{\instrbox}%
  \begin{minipage}{\dimexpr\textwidth-2\fboxsep-2\fboxrule\relax}%
}{%
  \end{minipage}%
  \end{lrbox}%
  \begin{center}\colorbox{boxgray}{\usebox{\instrbox}}\end{center}%
}

% ----- Marks in right margin -----
\newcommand{\qmarks}[1]{\hfill\textbf{[#1]}}

% ----- Auto-numbered question list -----
\newcounter{qnum}
\newenvironment{qlist}{%
  \setcounter{qnum}{0}%
  \begin{list}{\textbf{\theqnum.}}{%
    \usecounter{qnum}%
    \setlength{\leftmargin}{2.2em}%
    \setlength{\labelwidth}{1.6em}%
    \setlength{\itemsep}{6pt}%
    \setlength{\parsep}{0pt}}%
}{\end{list}}
\newcommand{\Q}{\item}

% ----- MCQ options in 2 columns -----
\newcounter{optno}
\newenvironment{opts}{%
  \setcounter{optno}{0}%
  \par\vspace{1pt}\begin{multicols}{2}%
  \begin{list}{(\alph{optno})}{%
    \usecounter{optno}%
    \setlength{\leftmargin}{2em}%
    \setlength{\itemsep}{1pt}%
    \setlength{\topsep}{1pt}}%
}{\end{list}\end{multicols}}

% ----- (a)(b) parts -----
\newcounter{partno}
\newenvironment{parts}{%
  \begin{list}{(\alph{partno})}{%
    \usecounter{partno}%
    \setlength{\leftmargin}{2em}%
    \setlength{\itemsep}{3pt}}%
}{\end{list}}

\begin{document}

% ==================== TITLE ====================
\begin{center}
{\large\bfseries \bn{পশ্চিমবঙ্গ উচ্চমাধ্যমিক শিক্ষা সংসদ}}\\[6pt]
{\Huge\bfseries \bn{উচ্চ মাধ্যমিক পরীক্ষা}}\\[6pt]
{\LARGE \bn{কম্পিউটার সায়েন্স (COMS)}}\\[8pt]
\hrule\vspace{0.15cm}
{\Large\bfseries \bn{দ্বাদশ শ্রেণি \ --\ Theory}}\\
\vspace{0.15cm}\hrule
\vspace{0.5cm}
\begin{tabular}{p{6cm} p{6cm}}
{\bfseries \bn{পূর্ণমান : ৭০}} & \hfill {\bfseries \bn{সময় : ৩ ঘণ্টা ১৫ মিনিট}}
\end{tabular}
\end{center}

\vspace{0.2cm}

% ==================== INSTRUCTIONS ====================
\begin{instructionbox}
\itshape
\bn{সংক্ষিপ্ত ও যথাযথ উত্তরের জন্য বিশেষ নম্বর দেওয়া হবে। বানান ভুল, অপরিচ্ছন্নতা এবং খারাপ হস্তাক্ষরের জন্য নম্বর কাটা যাবে।}\par
\vspace{4pt}
\bn{প্রান্তস্থ সংখ্যাগুলি প্রশ্নের পূর্ণমান নির্দেশ করে।}
\end{instructionbox}

% ==================== GROUP A : MCQ ====================
\groupbanner{\bn{বিভাগ – ক} \quad ( \bn{বহু বিকল্পভিত্তিক প্রশ্ন} / MCQ )}

\noindent\textbf{\bn{১।\ প্রতিটি প্রশ্নের সঠিক বিকল্পটি নির্বাচন করো :}} \qmarks{\bn{২১ × ১ = ২১}}
\vspace{4pt}

\begin{qlist}
\Q \bn{<<< COMS MCQ in Bangla, tech terms in English >>>}
\begin{opts}\item optA \item optB \item optC \item optD\end{opts}
% ... repeat until 21 MCQs (include Python tuples/dict/exception, EDI, AI search) ...
\end{qlist}

% ==================== GROUP B : SHORT ANSWER ====================
\groupbanner{\bn{বিভাগ – খ} \quad ( \bn{সংক্ষিপ্ত উত্তরধর্মী প্রশ্ন} / Short Answer )}

\noindent\textbf{\bn{২।\ নিচের প্রশ্নগুলির উত্তর দাও :}} \qmarks{\bn{১৪ × ১ = ১৪}}
\vspace{4pt}

\begin{qlist}
\Q \bn{<<< short-answer question 1 >>>}
% ... repeat until 14 short-answer questions ...
\end{qlist}

\newpage

% ==================== GROUP C : BROAD ====================
\groupbanner{\bn{বিভাগ – গ} \quad ( \bn{রচনাধর্মী / বর্ণনামূলক প্রশ্ন} / Broad )}

\noindent\textbf{\bn{নিচের যেকোনো \emph{পাঁচটি} প্রশ্নের উত্তর দাও :}} \qmarks{\bn{৫ × ৭ = ৩৫}}
\vspace{6pt}

\begin{qlist}
\Q \bn{নিচের প্রশ্নের উত্তর দাও :} \qmarks{\bn{৪ + ৩}}
\begin{parts}
\item \bn{<<< part (a) >>>}
\item \bn{<<< part (b) >>>}
\end{parts}
% ... repeat until 7 broad questions ...
\end{qlist}

\vfill
\begin{center}
\rule{8cm}{0.4pt}\\
\textbf{\bn{প্রশ্নপত্র সমাপ্ত}}\\
\vspace{0.2cm}
\itshape \bn{WBCHSE প্রশ্ন-প্যাটার্ন অনুযায়ী প্রস্তুত (বিভাগ ক : ২১, বিভাগ খ : ১৪, বিভাগ গ : ৩৫ = ৭০ নম্বর)}
\end{center}

\end{document}
```

---

## 🔑 Custom Commands Reference

| Command / Env | Purpose |
|---------------|---------|
| `\bn{...}` | Typeset a Bangla chunk with Kalpurush |
| `\groupbanner{...}` | Full-width blue section banner (বিভাগ ক/খ/গ) |
| `{instructionbox}` | Grey shaded official-instructions box |
| `{qlist}` + `\Q` | Auto-numbered question list (MCQ + Short) |
| `{opts}` + `\item` | 2-column (a)(b)(c)(d) MCQ options |
| `{parts}` + `\item` | (a)(b) sub-parts for Group C |
| `\qmarks{...}` | Right-margin marks |

---

## ✅ Compile Checklist

1. **overleaf.com → New Project → Blank Project**.
2. Paste the generated `.tex`.
3. Menu → Settings → **Compiler = XeLaTeX**.
4. **Recompile.** (Boxes □ on conjuncts → confirm XeLaTeX + Kalpurush.)

---

## 🧠 Key Facts (COMS-specific)

- **COMS ≠ COMA.** COMS is Computer Science (science stream); it ADDS tuples,
  dictionary, exception handling, EDI, and AI search (BFS/DFS/A*), and has NO
  data warehousing/data mining.
- **Pattern = 21 MCQ + 14 Short + (7 Broad, answer any 5) = 70 marks.**
- **Bangla needs XeLaTeX + Kalpurush**; pdfLaTeX/LuaLaTeX will show boxes.
- **Tech terms stay in English**; use Bangla numerals in headings/marks.
```
