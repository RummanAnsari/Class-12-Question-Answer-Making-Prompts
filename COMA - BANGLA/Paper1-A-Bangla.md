# WBCHSE Class XII COMA — Explained Answer Paper Generator (Reusable Prompt)

> **What this makes:** A **detailed answer key** (বিস্তারিত উত্তরপত্র) where every question is **repeated** and followed by a **long "Answer & Explanation"** block — with reasons, examples, code blocks, comparison tables and an ER diagram.
>
> **How to use:** Copy the "MASTER PROMPT" box, fill in the `>>> FILL THIS <<<` slots, and paste to any AI. Compile the result on **Overleaf**.

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert WBCHSE (West Bengal Council of Higher Secondary Education)
exam solutions author. Produce a COMPLETE, ready-to-compile LaTeX
"EXPLAINED ANSWER PAPER" (detailed answer key) following the EXACT
specification below. Do not skip any question.

========================= WHAT I WANT =========================
1. SUBJECT      : Modern Computer Application (COMA)
2. CLASS        : Class XII
3. LANGUAGE     : >>> FILL THIS <<<  ("Bangla/বাংলা"  OR  "English")
4. TOTAL MARKS  : 70 (Theory)  [official WBCHSE pattern]
5. FILENAME     : Paper<N>-A-<Language>   (e.g. Paper1-A-Bangla / Paper1-A-English)
6. SOURCE PAPER : Use my existing question paper if I paste one; otherwise
   generate fresh questions on these Class XII COMA topics:
   Python (data types, operators, loops, strings, lists, functions, modules,
   recursion, errors) · E-Commerce (B2B/B2C/C2C/G2G, e-payment, online shopping)
   · DBMS (keys, ER model, SQL DDL/DML, integrity) · Data Warehousing & Data
   Mining (OLTP/OLAP, mining steps) · Artificial Intelligence (ML types, NLP,
   applications, ethics/bias).

===================== OFFICIAL PATTERN (MUST MATCH) =====================
GROUP A — MCQ            : 21 questions × 1 = 21 marks
GROUP B — Short Answer   : 14 questions × 1 = 14 marks
GROUP C — Broad          : 7 questions (each has parts (a)(b) with split [4+3]/[3+4])
                           × 7 = 35 marks
TOTAL = 70.  Reset the question counter at the start of each Group.

===================== HOW EACH ANSWER MUST LOOK =====================
For EVERY question in all three groups:
1. REPEAT the full question using the \Question{marks}{question text} command
   (a small blue vertical bar + "প্রশ্ন N." / "Q N." + right-margin marks [N]).
2. Immediately below, open an {answer} environment which prints a green
   heading ("উত্তর ও ব্যাখ্যা :" in Bangla / "Answer & Explanation:" in English)
   and indents the body.
3. Write a DETAILED, LONGER explanation:
   - GROUP A (MCQ): state the correct option in bold, explain WHY it is correct
     AND why the other options are wrong, with a concrete example.
   - GROUP B (Short): a full-paragraph definition/explanation with an example.
   - GROUP C (Broad): thorough model answers. Where relevant include:
       * framed CODE blocks (Python factorial via recursion; SQL create/insert/select)
       * comparison TABLES (e.g. List vs Tuple, OLTP vs OLAP)
       * an ER diagram (MEMBER --- Issues --- BOOK) with keys/attributes noted.
4. Keep ALL technical terms in ENGLISH even inside a Bangla answer
   (Python, SQL, keywords, code, B2B, OLAP, primary key, etc.).
   In Bangla, wrap every Bangla chunk in \bn{...} and use Bangla numerals (১,২,৩…).

===================== COMPILER / FONT (CRITICAL) =====================
- BANGLA  -> compile with XeLaTeX (NOT pdfLaTeX / NOT LuaLaTeX),
  using fontspec + polyglossia and font "Kalpurush" (full conjunct support,
  built into Overleaf). Fallback font: "Noto Serif Bengali".
- ENGLISH -> compile with pdfLaTeX. If "listings"/"tikz" are unavailable,
  use "fancyvrb" for code and a text-based ER diagram instead.

===================== OUTPUT =====================
- Give the FULL .tex source in ONE copy-paste code block.
- Keep the comment header stating compiler + font at the top.
- Use the exact preamble + custom commands from the "GOLD TEMPLATE" section
  of this file (\Question, {answer}, \groupbanner, {instructionbox},
  \keyterm, \bn, code style). Only change the question/answer content.

Now generate the explained answer paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **LANGUAGE** | `Bangla/বাংলা` · `English` |
| **FILENAME** | `Paper1-A-Bangla` · `Paper2-A-English` |
| **SOURCE PAPER** | *"Use the question paper I pasted above"* · *"Generate fresh questions"* |
| **EXTRAS** | *"make explanations even longer"* · *"add a marking scheme note per question"* · *"bilingual answers"* |

---

## 🏆 GOLD TEMPLATE — Bangla Explained Answer Paper (confirmed working: XeLaTeX + Kalpurush)

> This is the exact, tested template. Keep this preamble and the `\Question{}{}` + `{answer}` pattern; only swap the question and explanation content.

```latex
% =====================================================================
%  WBCHSE  Class XII  Modern Computer Application (COMA)
%  Paper1-A-Bangla : EXPLAINED ANSWER PAPER (বিস্তারিত উত্তরপত্র) -- 70 Marks
%  ---------------------------------------------------------------------
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
\definecolor{ansboxbg}{RGB}{240,247,240}
\definecolor{codebg}{RGB}{245,245,245}

% ----- Header / Footer -----
\pagestyle{fancy}
\fancyhf{}
\lhead{\small WBCHSE \bn{— বিস্তারিত উত্তরপত্র}}
\chead{\small \bn{মডার্ন কম্পিউটার অ্যাপ্লিকেশন (COMA)}}
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
% Reset counter per group
\newcommand{\resetQ}{\setcounter{qcnt}{0}}

% ----- Answer block (shaded/indented) -----
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
{\LARGE \bn{মডার্ন কম্পিউটার অ্যাপ্লিকেশন (COMA)}}\\[8pt]
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
\Question{1}{\bn{<<< MCQ question in Bangla, tech terms in English >>>}\ \ (a) optA\ (b) optB\ (c) optC\ (d) optD}
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
\bn{\textbf{(a) ...}}  % detailed explanation, bullet points via itemize
\begin{itemize}[leftmargin=1.4em,itemsep=1pt]
\item \bn{...}
\end{itemize}
\bn{\textbf{(b) ...}}
% code block example:
\begin{lstlisting}[language=Python]
def factorial(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial(n-1)
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

## 🇬🇧 GOLD TEMPLATE — English variant (differences only)

To make the **English** explained answer paper, keep the same `\Question`/`{answer}` structure but change:

```latex
% Remove (not needed for English):
%   \usepackage{fontspec}, \usepackage{polyglossia}
%   \setmainlanguage / \setotherlanguage
%   \newfontfamily\bengalifont ... and the \bn command

% Portable code/diagram fallbacks (if listings/tikz unavailable):
\usepackage{amsmath,amssymb}
\usepackage{fancyvrb}   % use \begin{code}...\end{code} instead of lstlisting
\DefineVerbatimEnvironment{code}{Verbatim}{frame=single,fontsize=\small,xleftmargin=1em}
% ER diagram as text:  \fbox{MEMBER} ---< \fbox{Issues} >--- \fbox{BOOK}

% English \Question header: change "প্রশ্ন" -> "Q"
\renewcommand{\Question}[2]{\stepcounter{qcnt}\vspace{0.35cm}%
  \noindent{\color{qblue}\rule{3pt}{\baselineskip}}\hspace{6pt}%
  \textbf{Q\theqcnt.}\ \textbf{#2}\hfill\textbf{[#1]}\par\vspace{2pt}}

% English {answer} heading: "Answer & Explanation:"
% Group banners: GROUP -- A/B/C ( ... Type Questions )
```
Drop the `\bn{}` wrapper, write in plain English, and compile with **pdfLaTeX**.

---

## 🔑 Custom Commands Reference (what each does)

| Command / Env | Purpose |
|---------------|---------|
| `\Question{marks}{text}` | Repeats a question with blue bar, auto-number ("প্রশ্ন N"/"Q N") and right-margin `[marks]` |
| `{answer} ... {answer}` | Green "উত্তর ও ব্যাখ্যা :" / "Answer & Explanation:" heading + indented body |
| `\resetQ` | Resets the question counter to 0 at the start of each Group |
| `\groupbanner{...}` | Full-width blue section banner |
| `{instructionbox}` | Grey shaded note box under the title |
| `\keyterm{...}` | Bold a key term inside explanations |
| `\bn{...}` | Typeset a Bangla chunk with Kalpurush (Bangla file only) |
| `lstlisting` / `code` | Framed code block (Python/SQL) |

---

## ✅ Compile Checklist (Overleaf)

1. **overleaf.com → New Project → Blank Project**.
2. Paste the generated `.tex`.
3. **Bangla:** Menu → Settings → **Compiler = XeLaTeX**. (English: pdfLaTeX.)
4. **Recompile.**
5. Boxes (□) on Bangla conjuncts? → confirm **XeLaTeX** + font **Kalpurush**
   (or try **Noto Serif Bengali**).

---

## 🧠 Key Facts (keep results consistent)

- **Structure = 21 MCQ + 14 Short + 7 Broad (parts a,b) = 70 marks.** Reset counter per group.
- **Every question is repeated, then explained** — MCQs explain why the correct option wins AND why others fail.
- **Bangla needs XeLaTeX + Kalpurush**; pdfLaTeX/LuaLaTeX will fail or show boxes.
- **Tech terms stay in English** inside Bangla answers; use **Bangla numerals** in headings/marks.
- **Group C uses code blocks + tables + an ER diagram** for full, exam-ready answers.
- **Portability:** prefer `fancyvrb` over `listings`, and a text ER diagram over `tikz`,
  if compiling on a minimal TeX install (English). Overleaf has all packages.
- **Filename convention:** `Paper<N>-A-<Language>` (e.g. Paper1-A-Bangla).
```
