# WBCHSE Class XII COMA — English Question Paper Generator (Reusable Prompt)

> **What this makes:** A clean, official-format **English question paper** (70 marks) — Group A (21 MCQs), Group B (14 Short Answers), Group C (7 broad, answer any 5) — with blue Group banners, a grey instruction box, 2-column MCQ options and right-margin marks.
>
> **How to use:** Copy the "MASTER PROMPT" box, fill the `>>> FILL THIS <<<` slots, paste to any AI, then compile the result with **pdfLaTeX** (Overleaf or local).

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert WBCHSE (West Bengal Council of Higher Secondary Education)
exam-paper designer. Produce a COMPLETE, ready-to-compile LaTeX QUESTION PAPER
in ENGLISH following the EXACT specification below. Do not skip any part.

========================= WHAT I WANT =========================
1. SUBJECT      : Modern Computer Application (COMA)
2. CLASS        : Class XII
3. LANGUAGE     : English
4. TOTAL MARKS  : 70 (Theory)   Time: 3 Hours 15 Minutes
5. DIFFICULTY   : >>> FILL THIS <<<  (e.g., "Standard board level" / "Advanced / Pre-Board")
6. VARIATION    : >>> FILL THIS <<<  (e.g., "Paper-2 with all new questions" /
                  "same topics, harder MCQs")  -- generate FRESH questions but keep
                  the SAME structure, counts and marks.
7. SYLLABUS TOPICS (Class XII COMA):
   - Python Programming (data types, operators, loops, strings, lists, functions,
     modules, recursion, errors)
   - E-Commerce (B2B/B2C/C2C/G2G, electronic payment, online shopping)
   - DBMS (keys, ER model, relational model, SQL DDL/DML, joins, integrity)
   - Data Warehousing & Data Mining (OLTP/OLAP, data mining steps)
   - Artificial Intelligence (ML types, NLP, applications, ethics/bias)

===================== OFFICIAL PATTERN (MUST FOLLOW) =====================
GROUP A — Multiple Choice (MCQ) : 21 questions × 1 = 21 marks  (4 options each, 2 columns)
GROUP B — Short Answer          : 14 questions × 1 = 14 marks
GROUP C — Broad / Descriptive   : 7 questions given, ANSWER ANY 5, × 7 = 35 marks
                                  (each question has parts (a)(b) with a [4+3] or [3+4] split)
TOTAL = 70 marks.

- Print the official instruction block verbatim:
  "Special credit will be given for answers which are brief and to the point.
   Marks will be deducted for spelling mistakes, untidiness and bad handwriting.
   Figures in the margin indicate full marks for the questions."
- Show marks in the right margin using \qmarks (e.g. [21 x 1 = 21], [4 + 3]).
- Include code/SQL where natural (e.g. a factorial recursion prompt, SQL create/insert/select).

===================== FORMATTING (USE THE GOLD TEMPLATE) =====================
Use the EXACT preamble + custom commands from the "GOLD TEMPLATE" section of this
file: blue \groupbanner, grey {instructionbox}, auto-numbered \qlist with \Q,
2-column \opts for MCQ options, \parts for (a)(b), \qmarks for right-margin marks.
Only change the question content.

===================== COMPILER =====================
Compile with pdfLaTeX. Use only widely available packages
(geometry, amsmath, amssymb, graphicx, xcolor, fancyhdr, booktabs, multicol).
Do NOT require fontspec/polyglossia (that is only for the Bangla version).

===================== OUTPUT =====================
- Give the FULL .tex source in ONE copy-paste code block.
- Keep a short comment header naming the compiler (pdfLaTeX).
- End with "End of Question Paper" and the pattern summary line.

Now generate the question paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **DIFFICULTY** | `Standard board level` · `Advanced / Pre-Board` · `Scholarship / Olympiad` |
| **VARIATION** | `Paper-2, all new questions` · `same topics, harder MCQs` · `more code-based questions` |
| **EXTRAS** | `also give an explained answer key` · `add 30-mark Practical` · `make a Bangla version too` |

---

## 🏆 GOLD TEMPLATE — English Question Paper (compiles with pdfLaTeX)

> This is the exact, tested template. Keep this preamble and structure; only swap the question content.

```latex
% =====================================================================
%  WBCHSE  Class XII  Modern Computer Application (COMA)
%  ENGLISH Question Paper -- 70 Marks
%  COMPILE WITH : pdfLaTeX  (standard packages, no special fonts needed)
% =====================================================================
\documentclass[12pt,a4paper]{article}

\usepackage[a4paper,margin=1in]{geometry}
\usepackage{amsmath,amssymb}
\usepackage{graphicx}
\usepackage{xcolor}
\usepackage{fancyhdr}
\usepackage{booktabs}
\usepackage{multicol}

%===================================
% Header & Footer
%===================================
\pagestyle{fancy}
\fancyhf{}
\lhead{\textbf{WBCHSE}}
\chead{\textbf{Modern Computer Application (COMA)}}
\rhead{\textbf{Class XII}}
\cfoot{\thepage}
\renewcommand{\headrulewidth}{0.5pt}

%===================================
% Colors
%===================================
\definecolor{sectionblue}{RGB}{0,70,140}
\definecolor{boxgray}{RGB}{230,230,230}

%===================================
% Group banner
%===================================
\newcommand{\groupbanner}[1]{%
  \vspace{0.35cm}%
  \noindent\colorbox{sectionblue}{%
    \begin{minipage}{\dimexpr\textwidth-2\fboxsep\relax}%
      \centering\color{white}\large\bfseries #1%
    \end{minipage}}\par
  \vspace{0.25cm}%
}

%===================================
% Instruction box
%===================================
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

%===================================
% Auto-numbered question list with right-margin marks
%===================================
\newcounter{qnum}
% MCQ / SA list
\newenvironment{qlist}{%
  \setcounter{qnum}{0}%
  \begin{list}{\textbf{\theqnum.}}{%
    \usecounter{qnum}%
    \setlength{\leftmargin}{2.2em}%
    \setlength{\labelwidth}{1.6em}%
    \setlength{\itemsep}{6pt}%
    \setlength{\parsep}{0pt}}%
}{%
  \end{list}%
}
\newcommand{\Q}{\item}

% marks in right margin
\newcommand{\qmarks}[1]{\hfill\textbf{[#1]}}

% (a)(b)(c)(d) options in 2 columns for MCQs
\newcounter{optno}
\newenvironment{opts}{%
  \setcounter{optno}{0}%
  \par\vspace{1pt}\begin{multicols}{2}%
  \begin{list}{(\alph{optno})}{%
    \usecounter{optno}%
    \setlength{\leftmargin}{2em}%
    \setlength{\itemsep}{1pt}%
    \setlength{\topsep}{1pt}}%
}{%
  \end{list}%
  \end{multicols}%
}

% (a)(b)(c) parts
\newenvironment{parts}{%
  \begin{list}{(\alph{partno})}{%
    \usecounter{partno}%
    \setlength{\leftmargin}{2em}%
    \setlength{\itemsep}{3pt}}%
}{%
  \end{list}%
}
\newcounter{partno}

\begin{document}

%===================================
% Title
%===================================
\begin{center}
{\Large \textbf{WEST BENGAL COUNCIL OF HIGHER SECONDARY EDUCATION}} \\[6pt]
{\Huge \textbf{Higher Secondary Examination}} \\[6pt]
{\LARGE Modern Computer Application (COMA)} \\[8pt]
\hrule
\vspace{0.15cm}
{\Large \textbf{Class XII \quad -- \quad Theory}} \\
\vspace{0.15cm}
\hrule
\vspace{0.5cm}
\begin{tabular}{p{6cm} p{6cm}}
\textbf{Full Marks: 70} & \hfill \textbf{Time: 3 Hours 15 Minutes} \\
\end{tabular}
\end{center}

\vspace{0.2cm}

%===================================
% Official Instruction Block
%===================================
\begin{instructionbox}
\textit{Special credit will be given for answers which are brief and to the point.
Marks will be deducted for spelling mistakes, untidiness and bad handwriting.}\par
\vspace{4pt}
\textit{Figures in the margin indicate full marks for the questions.}
\end{instructionbox}

%===================================
% GROUP A - MCQ (21 x 1 = 21)
%===================================
\groupbanner{GROUP -- A \quad ( Multiple Choice Type Questions )}

\noindent\textbf{1. Choose the correct alternative for each of the following:} \qmarks{21 $\times$ 1 = 21}

\vspace{4pt}

\begin{qlist}
\Q <<< MCQ question text >>>
\begin{opts}\item optionA \item optionB \item optionC \item optionD\end{opts}
% ... repeat until 21 MCQs ...
\end{qlist}

%===================================
% GROUP B - Short Answer (14 x 1 = 14)
%===================================
\groupbanner{GROUP -- B \quad ( Short Answer Type Questions )}

\noindent\textbf{2. Answer the following questions:} \qmarks{14 $\times$ 1 = 14}

\vspace{4pt}

\begin{qlist}
\Q <<< short-answer question 1 >>>
% ... repeat until 14 short-answer questions ...
\end{qlist}

%===================================
% GROUP C - Broad Type (5 x 7 = 35)
%===================================
\groupbanner{GROUP -- C \quad ( Broad / Descriptive Type Questions )}

\noindent\textbf{Answer any \emph{five} of the following questions:} \qmarks{5 $\times$ 7 = 35}

\vspace{6pt}

\begin{qlist}
\Q Answer the following: \qmarks{4 + 3}
\begin{parts}
\item <<< part (a) >>>
\item <<< part (b) >>>
\end{parts}
% ... repeat until 7 broad questions ...
\end{qlist}

\vfill

\begin{center}
\rule{8cm}{0.4pt}\\
\textbf{End of Question Paper}\\
\vspace{0.2cm}
\textit{Prepared as per the WBCHSE Question Pattern (Group A: 21, Group B: 14, Group C: 35 = 70 Marks)}
\end{center}

\end{document}
```

---

## 🔑 Custom Commands Reference (what each does)

| Command / Env | Purpose |
|---------------|---------|
| `\groupbanner{...}` | Full-width blue section banner (GROUP A/B/C) |
| `{instructionbox} ... {instructionbox}` | Grey shaded official-instructions box under the title |
| `{qlist} ... {qlist}` + `\Q` | Auto-numbered question list (used for MCQ and Short Answer) |
| `{opts} ... {opts}` + `\item` | 2-column (a)(b)(c)(d) MCQ options |
| `{parts} ... {parts}` + `\item` | (a)(b) sub-parts for Group C questions |
| `\qmarks{...}` | Right-margin marks, e.g. `\qmarks{4 + 3}` → **[4 + 3]** |

---

## ✅ Compile Checklist

1. **overleaf.com → New Project → Blank Project** (or any local TeX install).
2. Paste the generated `.tex`.
3. Compiler = **pdfLaTeX** (default). Click **Recompile**.
4. Done — no special fonts or packages needed.

> ⚠️ If a minimal TeX install lacks a package, all packages used here
> (geometry, amsmath, amssymb, graphicx, xcolor, fancyhdr, booktabs, multicol)
> are standard and present on Overleaf.

---

## 🧠 Key Facts (keep results consistent)

- **Structure = 21 MCQ + 14 Short + (7 Broad, answer any 5) = 70 marks.**
- **English → pdfLaTeX**; no fontspec/polyglossia needed (those are Bangla-only).
- **MCQs:** exactly 4 options, shown in **2 columns** via `{opts}`.
- **Group C:** each question has parts **(a)(b)** with a **[4+3]/[3+4]** split via `\qmarks`.
- **Official instruction block** must appear verbatim under the title.
- **Reusable commands:** `\groupbanner`, `{instructionbox}`, `qlist`+`\Q`, `opts`, `parts`, `\qmarks`.
- **To get the Bangla version:** add fontspec + polyglossia + Kalpurush, compile with
  **XeLaTeX**, wrap text in `\bn{}`, and use Bangla numerals (১,২,৩…).
```
