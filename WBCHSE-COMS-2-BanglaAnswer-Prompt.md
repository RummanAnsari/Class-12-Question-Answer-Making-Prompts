# WBCHSE Class XII COMS (Computer Science) — BANGLA Explained Answer Paper Generator (Prompt #2)

> **Subject:** Computer Science (COMS) — science stream. **Different from COMA.**
> **What this makes:** A Bangla (বাংলা) **detailed answer key** (বিস্তারিত উত্তরপত্র), 70 marks — every question **repeated**, then a **long "উত্তর ও ব্যাখ্যা"** block with reasons, examples, code, tables and an ER diagram.
> **How to use:** Copy the "MASTER PROMPT" box, fill the `>>> FILL THIS <<<` slots, paste to any AI, then compile with **XeLaTeX + Kalpurush** on Overleaf.

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert WBCHSE (West Bengal Council of Higher Secondary Education)
exam solutions author. Produce a COMPLETE, ready-to-compile LaTeX
"EXPLAINED ANSWER PAPER" (বিস্তারিত উত্তরপত্র) in BANGLA following the EXACT
specification below. Do not skip any question.

========================= WHAT I WANT =========================
1. SUBJECT      : Computer Science (COMS)   [science stream — NOT COMA]
2. CLASS        : Class XII
3. LANGUAGE     : Bangla/বাংলা  (technical terms stay in English)
4. TOTAL MARKS  : 70 (Theory)
5. FILENAME     : Paper<N>-A-Bangla   (e.g. Paper1-A-Bangla)
6. SOURCE PAPER : Use my existing COMS question paper if I paste one; otherwise
   generate fresh questions on these Class XII COMS topics:
   - Python (data types incl. TUPLES & DICTIONARY; operators; type conversion;
     errors syntax/logical/run-time; conditional & iterative statements; strings;
     lists; tuples; dictionary; modules; user-defined functions;
     EXCEPTION HANDLING try-except-finally)
   - E-Commerce (intro/goals/functions; business models B2B/B2C/C2C/C2G/G2G/B2G;
     EDI - Electronic Data Interchange; Electronic Payment System;
     Internet Marketing; online shopping pros/cons)
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
1. REPEAT the full question using \Question{marks}{question text}
   (blue vertical bar + "প্রশ্ন N." + right-margin marks [N]).
2. Immediately below, open {answer} which prints a green "উত্তর ও ব্যাখ্যা :"
   heading and indents the body.
3. Write a DETAILED, LONGER explanation:
   - GROUP A (MCQ): state the correct option in bold, explain WHY it is correct
     AND why the other options are wrong, with a concrete example.
   - GROUP B (Short): a full-paragraph definition/explanation with an example.
   - GROUP C (Broad): thorough model answers. Where relevant include:
       * framed CODE blocks (Python; SQL). Show COMS-specific code such as
         exception handling (try-except-finally) and dictionary operations.
       * comparison TABLES (e.g. List vs Tuple, tuple vs dictionary, BFS vs DFS,
         OLTP-style comparisons, EDI advantages/disadvantages).
       * an ER diagram (e.g. MEMBER --- Issues --- BOOK) with keys/attributes.
       * for AI SEARCH questions, explain BFS/DFS/A* with a small state-space example.
4. Keep ALL technical terms in ENGLISH even inside a Bangla answer
   (Python, SQL, EDI, A*, BFS, DFS, B2B, code, keywords). Wrap Bangla chunks in
   \bn{...} and use Bangla numerals (১,২,৩…).

===================== COMPILER / FONT (CRITICAL) =====================
Compile with XeLaTeX (NOT pdfLaTeX / NOT LuaLaTeX) using fontspec + polyglossia
and font "Kalpurush" (full conjunct support, built into Overleaf).
Fallback font: "Noto Serif Bengali".

===================== OUTPUT =====================
- Give the FULL .tex source in ONE copy-paste code block.
- Keep the comment header stating compiler + font at the top.
- Use the exact preamble + custom commands from the "GOLD TEMPLATE" section below
  (\Question, {answer}, \groupbanner, {instructionbox}, \keyterm, \bn, code style).
  Only change the question/answer content.

Now generate the explained answer paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **FILENAME** | `Paper1-A-Bangla` · `Paper2-A-Bangla` |
| **SOURCE PAPER** | *"Use the COMS question paper I pasted above"* · *"Generate fresh questions"* |
| **EXTRAS** | *"make explanations even longer"* · *"add marking scheme per question"* |

---

## 🏆 GOLD TEMPLATE — Bangla COMS Explained Answer Paper (XeLaTeX + Kalpurush)

```latex
% =====================================================================
%  WBCHSE  Class XII  Computer Science (COMS)
%  Paper1-A-Bangla : EXPLAINED ANSWER PAPER (বিস্তারিত উত্তরপত্র) -- 70 Marks
%  Each question is REPEATED, then a DETAILED Bengali explanation follows.
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
\usepackage{longtable}
\usepackage{enumitem}
\usepackage{listings}
\usepackage{tikz}

% ----- Languages -----
\setmainlanguage{english}
\setotherlanguage{bengali}

% ----- Fonts -----
\setmainfont{Latin Modern Roman}
\newfontfamily\bengalifont{Kalpurush}[Script=Bengali]
\newcommand{\bn}[1]{{\bengalifont #1}}

% ----- Colours -----
\definecolor{sectionblue}{RGB}{0,70,140}
\definecolor{boxgray}{RGB}{230,230,230}
\definecolor{qblue}{RGB}{0,70,140}
\definecolor{answergreen}{RGB}{0,110,60}
\definecolor{codebg}{RGB}{245,245,245}

% ----- Header / Footer -----
\pagestyle{fancy}
\fancyhf{}
\lhead{\small WBCHSE \bn{— বিস্তারিত উত্তরপত্র}}
\chead{\small \bn{কম্পিউটার সায়েন্স (COMS)}}
\rhead{\small \bn{দ্বাদশ শ্রেণি}}
\cfoot{\bn{পৃষ্ঠা} \thepage}
\renewcommand{\headrulewidth}{0.5pt}

% ----- Group banner -----
\newcommand{\groupbanner}[1]{%
  \vspace{0.4cm}%
  \noindent\colorbox{sectionblue}{%
    \begin{minipage}{\dimexpr\textwidth-2\fboxsep\relax}%
      \centering\color{white}\large\bfseries #1%
    \end{minipage}}\par
  \vspace{0.3cm}%
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

% ----- Question header (repeated question) -----
\newcounter{qcnt}[section]
\newcommand{\Question}[2]{% #1 = marks label, #2 = question text
  \stepcounter{qcnt}%
  \vspace{0.35cm}%
  \noindent{\color{qblue}\rule{3pt}{\baselineskip}}\hspace{6pt}%
  \textbf{\bn{প্রশ্ন} \theqcnt.}\ \textbf{#2}\hfill\textbf{[#1]}\par
  \vspace{2pt}%
}
\newcommand{\resetQ}{\setcounter{qcnt}{0}}

% ----- Answer block -----
\newenvironment{answer}{%
  \vspace{2pt}\par\noindent
  \textbf{\color{answergreen}\bn{উত্তর ও ব্যাখ্যা :}}\par\vspace{2pt}
  \begingroup\leftskip=1.2em
}{%
  \endgroup\vspace{4pt}
}

% ----- code listing style -----
\lstset{
  basicstyle=\ttfamily\small,
  backgroundcolor=\color{codebg},
  frame=single,
  breaklines=true,
  columns=fullflexible,
  keepspaces=true,
  xleftmargin=1em,
  aboveskip=6pt,belowskip=6pt
}

\newcommand{\keyterm}[1]{\textbf{#1}}

\begin{document}

% ==================== TITLE ====================
\begin{center}
{\large\bfseries \bn{পশ্চিমবঙ্গ উচ্চমাধ্যমিক শিক্ষা সংসদ}}\\[6pt]
{\Huge\bfseries \bn{বিস্তারিত উত্তরপত্র}}\\[4pt]
{\large (Explained Answer Paper — Paper 1A)}\\[6pt]
{\LARGE \bn{কম্পিউটার সায়েন্স (COMS)}}\\[8pt]
\hrule\vspace{0.15cm}
{\Large\bfseries \bn{দ্বাদশ শ্রেণি \ --\ Theory}}\\
\vspace{0.15cm}\hrule
\vspace{0.5cm}
\begin{tabular}{p{6cm} p{6cm}}
{\bfseries \bn{পূর্ণমান : ৭০}} & \hfill {\bfseries \bn{প্রতিটি প্রশ্নের বিস্তারিত ব্যাখ্যাসহ উত্তর}}
\end{tabular}
\end{center}

\vspace{0.2cm}

\begin{instructionbox}
\itshape
\bn{এই উত্তরপত্রে প্রতিটি প্রশ্ন পুনরায় লেখা হয়েছে এবং তার নিচে বিস্তারিত ব্যাখ্যাসহ আদর্শ উত্তর দেওয়া হয়েছে। উদাহরণ, কোড ও কারণ-সহ ব্যাখ্যা যুক্ত করা হয়েছে যাতে শিক্ষার্থী বিষয়টি গভীরভাবে বুঝতে পারে।}
\end{instructionbox}

% ==================== GROUP A ====================
\groupbanner{\bn{বিভাগ – ক} \quad ( \bn{বহু বিকল্পভিত্তিক প্রশ্ন} / MCQ ) \quad [\bn{২১ × ১ = ২১}]}
\resetQ

% ---- pattern for each MCQ (repeat 21 times) ----
\Question{1}{\bn{<<< COMS MCQ in Bangla, tech terms in English >>>}\ \ (a) optA\ (b) optB\ (c) optC\ (d) optD}
\begin{answer}
\bn{সঠিক উত্তর : (X) \textbf{<<< correct option >>>}.}\par
\bn{<<< detailed WHY-it-is-correct + why others are wrong + example >>>}
\end{answer}

% ==================== GROUP B ====================
\newpage
\groupbanner{\bn{বিভাগ – খ} \quad ( \bn{সংক্ষিপ্ত উত্তরধর্মী প্রশ্ন} / Short Answer ) \quad [\bn{১৪ × ১ = ১৪}]}
\resetQ

% ---- pattern for each short answer (repeat 14 times) ----
\Question{1}{\bn{<<< short-answer question >>>}}
\begin{answer}
\bn{<<< full-paragraph definition/explanation with an example >>>}
\end{answer}

% ==================== GROUP C ====================
\newpage
\groupbanner{\bn{বিভাগ – গ} \quad ( \bn{রচনাধর্মী / বর্ণনামূলক প্রশ্ন} / Broad ) \quad [\bn{৫ × ৭ = ৩৫}]}
\resetQ

% ---- pattern for each broad question (repeat 7 times) ----
\Question{4+3}{\bn{(a) <<< part a >>> (b) <<< part b >>>}}
\begin{answer}
\bn{\textbf{(a) ...}}  % detailed explanation
\begin{itemize}[leftmargin=1.4em,itemsep=1pt]
\item \bn{...}
\end{itemize}
\bn{\textbf{(b) ...}}
% code block example (COMS: exception handling / dictionary / SQL):
\begin{lstlisting}[language=Python]
try:
    x = int(input("Enter a number: "))
    print(10 / x)
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("Done")
\end{lstlisting}
% comparison table example:
\begin{center}\begin{tabular}{|p{5.7cm}|p{5.7cm}|}
\hline \textbf{A} & \textbf{B} \\ \hline
\bn{...} & \bn{...} \\ \hline
\end{tabular}\end{center}
\end{answer}

\vfill
\begin{center}
\rule{8cm}{0.4pt}\\
\textbf{\bn{বিস্তারিত উত্তরপত্র সমাপ্ত}}\\
\vspace{0.2cm}
\itshape \bn{WBCHSE প্রশ্ন-প্যাটার্ন অনুযায়ী প্রস্তুত (বিভাগ ক : ২১, বিভাগ খ : ১৪, বিভাগ গ : ৩৫ = ৭০ নম্বর)}
\end{center}

\end{document}
```

---

## 🔑 Custom Commands Reference

| Command / Env | Purpose |
|---------------|---------|
| `\Question{marks}{text}` | Repeats a question with blue bar, "প্রশ্ন N" and right-margin `[marks]` |
| `{answer} ... {answer}` | Green "উত্তর ও ব্যাখ্যা :" heading + indented body |
| `\resetQ` | Resets the question counter at the start of each Group |
| `\keyterm{...}` | Bolds a key term inside explanations |
| `\bn{...}` | Typeset a Bangla chunk with Kalpurush |
| `lstlisting` | Framed code block (Python/SQL) |
| `\groupbanner{...}` | Blue section banner |
| `{instructionbox}` | Grey shaded note box |

---

## ✅ Compile Checklist

1. **overleaf.com → New Project → Blank Project**.
2. Paste the generated `.tex`.
3. Menu → Settings → **Compiler = XeLaTeX**.
4. **Recompile.** (Boxes □ on conjuncts → confirm XeLaTeX + Kalpurush.)

---

## 🧠 Key Facts (COMS-specific)

- **COMS ≠ COMA.** Include COMS extras in answers: exception handling code,
  tuples/dictionary, EDI, and AI search (BFS/DFS/A*). No data warehousing/mining.
- **Structure = 21 MCQ + 14 Short + 7 Broad (parts a,b) = 70 marks.** `\resetQ` per group.
- **Every question repeated, then explained** — MCQs explain why correct + why others fail.
- **Bangla needs XeLaTeX + Kalpurush**; tech terms in English; Bangla numerals.
- **Filename convention:** `Paper<N>-A-Bangla`.
```
