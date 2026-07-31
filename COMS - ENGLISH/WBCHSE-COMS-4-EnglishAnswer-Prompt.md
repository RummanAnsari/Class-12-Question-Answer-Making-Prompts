# WBCHSE Class XII COMS (Computer Science) — ENGLISH Explained Answer Paper Generator (Prompt #4)

> **Subject:** Computer Science (COMS) — science stream. **Different from COMA.**
> **What this makes:** A detailed **English answer key** (70 marks) where every question is **repeated** and followed by a **"Answer & Explanation"** block — with reasons, examples, framed code blocks, comparison tables and a text ER diagram.
> **How to use:** Copy the "MASTER PROMPT" box, fill the `>>> FILL THIS <<<` slots, paste to any AI, then compile with **pdfLaTeX** (Overleaf or local). This template is fully portable — it uses `fancyvrb` (not `listings`) and a text ER diagram (not `tikz`), so it compiles even on minimal TeX installs.

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert WBCHSE (West Bengal Council of Higher Secondary Education)
exam solutions author. Produce a COMPLETE, ready-to-compile LaTeX
"EXPLAINED ANSWER PAPER" in ENGLISH following the EXACT specification below.
Do not skip any question.

========================= WHAT I WANT =========================
1. SUBJECT      : Computer Science (COMS)   [science stream — NOT COMA]
2. CLASS        : Class XII
3. LANGUAGE     : English
4. TOTAL MARKS  : 70 (Theory)
5. FILENAME     : Paper<N>-A-English   (e.g. Paper1-A-English)
6. SOURCE PAPER : Use my existing COMS question paper if I paste one; otherwise
   generate fresh questions on these Class XII COMS topics:
   - Python (data types incl. TUPLES & DICTIONARY; operators; type conversion;
     errors syntax/logical/run-time; conditional & iterative statements; strings;
     lists; tuples; dictionary; modules; user-defined functions;
     EXCEPTION HANDLING try-except-finally)
   - E-Commerce (intro/goals/functions; business models B2B/B2C/C2C/C2G/G2G/B2G;
     EDI - Electronic Data Interchange (concepts, applications, model, limitations);
     Electronic Payment System; Internet Marketing; online shopping pros/cons)
   - DBMS (legacy drawbacks; data independence; data models; ER Modelling incl.
     weak/strong entity, specialization/generalization, aggregation;
     Relational Model & Relational Algebra; Integrity Constraints; SQL DDL/DML,
     constraints, aggregate functions, group by/having, joins)
   - Foundation of AI (definition & scope; AI vs human intelligence;
     ML supervised/unsupervised/reinforcement; deep learning & neural networks;
     NLP & computer vision; SEARCH AS OPTIMIZATION: state space search,
     data-driven & goal-driven, heuristic search, BFS, DFS, A*;
     AI applications; AI ethics & bias)

===================== OFFICIAL PATTERN (MUST MATCH) =====================
GROUP A — MCQ            : 21 questions × 1 = 21 marks
GROUP B — Short Answer   : 14 questions × 1 = 14 marks
GROUP C — Broad          : 7 questions (each has parts (a)(b), split [4+3]/[3+4]) × 7 = 35
TOTAL = 70.  Reset the question counter (\resetQ) at the start of each Group.

===================== HOW EACH ANSWER MUST LOOK =====================
For EVERY question in all three groups:
1. RESTATE the full question with \Question{marks}{question text}
   (blue vertical bar + "Q N." + right-margin marks [N]).
2. Immediately below, open the {answer} environment which prints a green
   "Answer & Explanation:" heading and indents the body.
3. Write a DETAILED explanation:
   - GROUP A (MCQ): state the correct option using \correct{...}, explain WHY it
     is correct AND why the other options are wrong, with a concrete example.
   - GROUP B (Short): a full-paragraph definition/explanation with an example.
   - GROUP C (Broad): thorough model answers. Where relevant include:
       * framed CODE blocks using the {code} environment. Show COMS-specific code
         such as EXCEPTION HANDLING (try-except-finally), DICTIONARY operations,
         and SQL create/insert/select.
       * comparison TABLES (e.g. List vs Tuple, Tuple vs Dictionary, BFS vs DFS,
         EDI advantages/disadvantages).
       * a text ER diagram: \fbox{MEMBER} ---< \fbox{Issues} >--- \fbox{BOOK}
         with keys/attributes noted.
       * for AI SEARCH questions, explain BFS/DFS/A* with a small state-space example.
4. Use \keyterm{...} to bold important terms.

===================== COMPILER (CRITICAL) =====================
Compile with pdfLaTeX. Use ONLY portable packages:
geometry, amsmath, amssymb, graphicx, xcolor, fancyhdr, booktabs, multicol, fancyvrb.
Do NOT use fontspec/polyglossia (Bangla-only), and DO NOT use listings or tikz
(use fancyvrb {code} for code and a text ER diagram instead).

===================== OUTPUT =====================
- Give the FULL .tex source in ONE copy-paste code block.
- Keep the comment header naming the compiler (pdfLaTeX).
- Use the exact preamble + custom commands from the "GOLD TEMPLATE" section of
  this file (\Question, {answer}, {code}, \groupbanner, {instructionbox},
  \keyterm, \correct). Only change the question/answer content.

Now generate the explained answer paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **FILENAME** | `Paper1-A-English` · `Paper2-A-English` |
| **SOURCE PAPER** | *"Use the COMS question paper I pasted above"* · *"Generate fresh questions"* |
| **EXTRAS** | *"make explanations even longer"* · *"add a 1-line marking scheme per question"* · *"add more code examples"* |

---

## 🏆 GOLD TEMPLATE — English COMS Explained Answer Paper (compiles with pdfLaTeX; fully portable)

```latex
% =====================================================================
%  WBCHSE  Class XII  Computer Science (COMS)
%  Paper1-A-English : EXPLAINED ANSWER PAPER -- 70 Marks
%  Each question is REPEATED, then a DETAILED explanation follows.
%  COMPILE WITH  :  pdfLaTeX  (standard English, no special fonts needed)
% =====================================================================
\documentclass[12pt,a4paper]{article}

\usepackage[a4paper,margin=1in]{geometry}
\usepackage{amsmath,amssymb}
\usepackage{graphicx}
\usepackage{xcolor}
\usepackage{fancyhdr}
\usepackage{booktabs}
\usepackage{multicol}
\usepackage{fancyvrb}   % portable code blocks (instead of listings)

%===================================
% Header & Footer
%===================================
\pagestyle{fancy}
\fancyhf{}
\lhead{\small\textbf{WBCHSE}}
\chead{\small\textbf{COMS — Answer Key}}
\rhead{\small\textbf{Class XII}}
\cfoot{\thepage}
\renewcommand{\headrulewidth}{0.5pt}

%===================================
% Colors
%===================================
\definecolor{sectionblue}{RGB}{0,70,140}
\definecolor{boxgray}{RGB}{230,230,230}
\definecolor{qblue}{RGB}{0,70,140}
\definecolor{answergreen}{RGB}{0,110,60}
\definecolor{codebg}{RGB}{245,245,245}

%===================================
% Group banner
%===================================
\newcommand{\groupbanner}[1]{%
  \vspace{0.4cm}%
  \noindent\colorbox{sectionblue}{%
    \begin{minipage}{\dimexpr\textwidth-2\fboxsep\relax}%
      \centering\color{white}\large\bfseries #1%
    \end{minipage}}\par
  \vspace{0.3cm}%
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
% Question header (repeated question)
%===================================
\newcounter{qcnt}
\newcommand{\Question}[2]{% #1 = marks label, #2 = question text
  \stepcounter{qcnt}%
  \vspace{0.35cm}%
  \noindent{\color{qblue}\rule{3pt}{\baselineskip}}\hspace{6pt}%
  \textbf{Q\theqcnt.}\ \textbf{#2}\hfill\textbf{[#1]}\par
  \vspace{2pt}%
}
\newcommand{\resetQ}{\setcounter{qcnt}{0}}

%===================================
% Answer block
%===================================
\newenvironment{answer}{%
  \vspace{2pt}\par\noindent
  \textbf{\color{answergreen}Answer \& Explanation:}\par\vspace{2pt}
  \begingroup\leftskip=1.2em
}{%
  \endgroup\vspace{4pt}
}

\newcommand{\keyterm}[1]{\textbf{#1}}
\newcommand{\correct}[1]{\textbf{\color{answergreen}#1}}
\DefineVerbatimEnvironment{code}{Verbatim}{frame=single,fontsize=\small,xleftmargin=1em,framesep=4pt,rulecolor=\color{sectionblue}}

\begin{document}

%===================================
% Title
%===================================
\begin{center}
{\Large \textbf{WEST BENGAL COUNCIL OF HIGHER SECONDARY EDUCATION}} \\[6pt]
{\Huge \textbf{Explained Answer Paper}} \\[4pt]
{\large (Paper 1A — with Detailed Explanations)}\\[6pt]
{\LARGE Computer Science (COMS)} \\[8pt]
\hrule
\vspace{0.15cm}
{\Large \textbf{Class XII \quad -- \quad Theory}} \\
\vspace{0.15cm}
\hrule
\vspace{0.5cm}
\begin{tabular}{p{6cm} p{6cm}}
\textbf{Full Marks: 70} & \hfill \textbf{Detailed model answers} \\
\end{tabular}
\end{center}

\vspace{0.2cm}

\begin{instructionbox}
\textit{In this answer paper, each question is restated and followed by a detailed model answer with reasons, examples and code, so that the concept is understood thoroughly. In Group C, any five questions are answered as required by the pattern.}
\end{instructionbox}

%===================================
% GROUP A
%===================================
\groupbanner{GROUP -- A \quad ( Multiple Choice Type Questions ) \quad [21 $\times$ 1 = 21]}
\resetQ

% ---- pattern for each MCQ (repeat 21 times) ----
\Question{1}{<<< COMS MCQ question text >>> \quad (a) optA \ (b) optB \ (c) optC \ (d) optD}
\begin{answer}
Correct answer: \correct{(X) <<< correct option >>>}.\par
<<< detailed WHY-it-is-correct + why the others are wrong + a concrete example >>>
\end{answer}

%===================================
% GROUP B
%===================================
\newpage
\groupbanner{GROUP -- B \quad ( Short Answer Type Questions ) \quad [14 $\times$ 1 = 14]}
\resetQ

% ---- pattern for each short answer (repeat 14 times) ----
\Question{1}{<<< short-answer question >>>}
\begin{answer}
<<< full-paragraph definition/explanation with an example >>>
\end{answer}

%===================================
% GROUP C
%===================================
\newpage
\groupbanner{GROUP -- C \quad ( Broad / Descriptive Type Questions ) \quad [5 $\times$ 7 = 35]}
\resetQ

% ---- pattern for each broad question (repeat 7 times) ----
\Question{4+3}{(a) <<< part a >>> (b) <<< part b >>>}
\begin{answer}
\keyterm{(a) ...} explanation, with bullet points:
\begin{itemize}
\item \keyterm{...} — ...
\end{itemize}
\keyterm{(b) ...}
% code block example (COMS: exception handling / dictionary / SQL):
\begin{code}
try:
    x = int(input("Enter a number: "))
    print(10 / x)
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("Done")
\end{code}
% comparison table example:
\renewcommand{\arraystretch}{1.3}
\begin{center}\begin{tabular}{|p{5.7cm}|p{5.7cm}|}
\hline \textbf{A} & \textbf{B} \\ \hline
... & ... \\ \hline
\end{tabular}\end{center}
% text ER diagram example:
\begin{center}
\setlength{\fboxsep}{6pt}%
\fbox{MEMBER} \ \textbf{---$<$} \ \fbox{\textit{Issues}} \ \textbf{$>$---} \ \fbox{BOOK}
\end{center}
\end{answer}

\vfill
\begin{center}
\rule{8cm}{0.4pt}\\
\textbf{End of Explained Answer Paper}\\
\vspace{0.2cm}
\textit{Prepared as per the WBCHSE Question Pattern (Group A: 21, Group B: 14, Group C: 35 = 70 Marks)}
\end{center}

\end{document}
```

---

## 🔑 Custom Commands Reference

| Command / Env | Purpose |
|---------------|---------|
| `\Question{marks}{text}` | Restates a question with blue bar, auto-number "Q N" and right-margin `[marks]` |
| `{answer} ... {answer}` | Green "Answer & Explanation:" heading + indented body |
| `\resetQ` | Resets the question counter to 0 at the start of each Group |
| `\correct{...}` | Highlights the correct MCQ option in green bold |
| `\keyterm{...}` | Bolds a key term inside explanations |
| `{code} ... {code}` | Framed code block (Python/SQL) via `fancyvrb` — portable, no `listings` needed |
| `\groupbanner{...}` | Full-width blue section banner |
| `{instructionbox}` | Grey shaded note box under the title |

---

## 🖼️ Portable substitutes (why this always compiles)

| Rich feature | Portable substitute used here |
|--------------|-------------------------------|
| Code blocks (`listings`) | `fancyvrb` `{code}` environment |
| ER diagram (`tikz`) | Text boxes: `\fbox{MEMBER} ---< \fbox{Issues} >--- \fbox{BOOK}` |
| Fancy list options (`enumitem`) | Native `itemize` / `enumerate` |

> Inside a `{code}` block, write code **literally** (no `\texttt`, no `$...$`); `<`, `>`, `&` are fine as-is.

---

## ✅ Compile Checklist

1. **overleaf.com → New Project → Blank Project** (or any local TeX install).
2. Paste the generated `.tex`.
3. Compiler = **pdfLaTeX**. Click **Recompile**.
4. Done — no special fonts or packages needed.

---

## 🧠 Key Facts (COMS-specific)

- **COMS ≠ COMA.** Include COMS extras in answers: exception handling code,
  tuples/dictionary, EDI, and AI search (BFS/DFS/A*). No data warehousing/mining.
- **Structure = 21 MCQ + 14 Short + 7 Broad (parts a,b) = 70 marks.** `\resetQ` per group.
- **Every question is repeated, then explained** — MCQs explain why correct + why others fail.
- **English → pdfLaTeX**; no fontspec/polyglossia.
- **Portable by design:** `fancyvrb` for code, text ER diagram, native lists — compiles on minimal TeX and Overleaf alike.
- **Filename convention:** `Paper<N>-A-English`.
- **For the Bangla version:** add fontspec + polyglossia + Kalpurush, compile with
  XeLaTeX, wrap text in `\bn{}`, and use Bangla numerals (১,২,৩…).
```
