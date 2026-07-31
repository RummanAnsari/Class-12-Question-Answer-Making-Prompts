# WBCHSE Class XII COMA — Question Paper Generator (Reusable Prompt)

> **How to use this file:** Copy the entire "MASTER PROMPT" section below and paste it to any AI assistant (Copilot / ChatGPT / Claude). Fill in the small **`>>> FILL THIS <<<`** placeholders (subject topics, language, marks, etc.), and you will get an identical, professionally formatted question paper — in English or Bangla — every time.

---

## 📌 MASTER PROMPT (copy everything inside the box)

```
You are an expert exam-paper designer for the WBCHSE (West Bengal Council of
Higher Secondary Education) board. Create a COMPLETE, ready-to-compile LaTeX
question paper following the EXACT specification below. Do not skip any part.

========================= WHAT I WANT =========================
1. SUBJECT      : Modern Computer Application (COMA)
2. CLASS        : Class XII
3. LANGUAGE     : >>> FILL THIS <<<  (choose: "English"  OR  "Bangla/বাংলা")
4. TOTAL MARKS  : 70  (Theory)   [keep official WBCHSE pattern]
5. DIFFICULTY   : >>> FILL THIS <<<  (e.g., "Standard board level" / "Advanced")
6. SYLLABUS TOPICS TO COVER (pick from Class XII COMA):
   - Python Programming (data types, operators, loops, strings, lists,
     functions, modules, recursion, errors)
   - E-Commerce (business models B2B/B2C/C2C/G2G, electronic payment, online shopping)
   - DBMS (keys, ER model, relational model, SQL DDL/DML, joins, integrity)
   - Data Warehousing & Data Mining (OLAP/OLTP, data mining steps)
   - Artificial Intelligence (ML types, NLP, applications, ethics/bias)
7. VARIATION    : Generate a FRESH set of questions each time (new numbers,
   new examples, reworded), but keep the SAME structure, counts, and marks.

===================== OFFICIAL WBCHSE PATTERN (MUST FOLLOW) =====================
GROUP A — Multiple Choice (MCQ) : 21 questions × 1 mark  = 21 marks
GROUP B — Short Answer          : 14 questions × 1 mark  = 14 marks
GROUP C — Broad/Descriptive     : 7 questions given, answer any 5, × 7 marks = 35 marks
TOTAL = 70 marks.  Time = 3 Hours 15 Minutes.

- Each Group C question has two parts (a)(b) with a split like [4+3] or [3+4].
- Every MCQ has exactly 4 options (a)(b)(c)(d), shown in 2 columns.
- Official instruction line MUST appear:
  "Special credit will be given for answers which are brief and to the point.
   Marks will be deducted for spelling mistakes, untidiness and bad handwriting.
   Figures in the margin indicate full marks for the questions."
  (In Bangla, use the Bangla translation shown in the template.)

===================== FORMATTING / TEMPLATE RULES =====================
Use the LaTeX PREAMBLE + STRUCTURE given in the "GOLD TEMPLATE" section of this
file EXACTLY (blue Group banners, grey instruction box, right-margin marks with
\qmarks, auto-numbered \qlist, 2-column \opts for MCQs, \parts for (a)(b)).
Keep technical terms (Python, SQL, keywords, code, model names like B2B/OLAP)
in ENGLISH even inside a Bangla paper — exactly like real WBCHSE bilingual papers.

===================== COMPILER / FONT RULES (CRITICAL) =====================
- ENGLISH paper  -> compiles with pdfLaTeX. If "listings"/"tikz"/"enumitem" are
  unavailable, fall back to "fancyvrb" for code and a text-based ER diagram.
- BANGLA paper   -> MUST compile with XeLaTeX (NOT pdfLaTeX / NOT LuaLaTeX)
  using fontspec + polyglossia and the font "Kalpurush" (full conjunct support,
  built into Overleaf). Wrap every Bangla chunk in \bn{...}.
  Use Bangla numerals (১, ২, ৩ …) in headings and marks.

===================== OUTPUT =====================
- Give the FULL .tex source in a single copy-paste code block.
- At the top of the file, keep a comment header stating the compiler + font.
- Also produce a matching "EXPLAINED ANSWER PAPER" if I ask (filename style:
  Paper<N>-A-<Language>, e.g. Paper1-A-Bangla / Paper1-A-English), where each
  question is REPEATED and followed by a detailed "Answer & Explanation" with
  reasons, examples, code blocks, comparison tables, and an ER diagram.

Now generate the paper.
```

---

## 🎯 Quick-Fill Cheat Sheet

| Placeholder | Example values |
|-------------|----------------|
| **LANGUAGE** | `English` · `Bangla/বাংলা` |
| **DIFFICULTY** | `Standard board level` · `Advanced / Pre-Board` |
| **VARIATION** | "Paper-2 with all new questions" · "same topics, harder MCQs" |
| **EXTRAS** | "also give explained answer key" · "add 30-mark Practical" · "bilingual side-by-side" |

---

## 🏆 GOLD TEMPLATE — Bangla Question Paper (confirmed working: XeLaTeX + Kalpurush)

> This is the exact, tested template. Ask the AI to keep this preamble and structure and only swap the question content.

```latex
% =====================================================================
%  WBCHSE  Class XII  Modern Computer Application (COMA)
%  BENGALI (বাংলা) Question Paper  -- 70 Marks
%  ---------------------------------------------------------------------
%  COMPILE WITH  :  XeLaTeX   (NOT pdfLaTeX / NOT LuaLaTeX)
%  REQUIRED FONT :  Kalpurush  (built into Overleaf; full conjunct support)
%  EASIEST WAY   :  Paste into Overleaf, set compiler = XeLaTeX, click Recompile
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
% >>> CONFIRMED WORKING SETUP: compile with XeLaTeX + Kalpurush font <<<
\setmainfont{Latin Modern Roman}
% Kalpurush has FULL Bengali conjunct (যুক্তাক্ষর) support and is built into Overleaf.
% If Kalpurush is unavailable, replace with: Noto Serif Bengali
\newfontfamily\bengalifont{Kalpurush}[Script=Bengali]
% A command to typeset a Bengali chunk:
\newcommand{\bn}[1]{{\bengalifont #1}}

% ----- Colours -----
\definecolor{sectionblue}{RGB}{0,70,140}
\definecolor{boxgray}{RGB}{230,230,230}

% ----- Header / Footer -----
\pagestyle{fancy}
\fancyhf{}
\lhead{\small WBCHSE}
\chead{\small \bn{মডার্ন কম্পিউটার অ্যাপ্লিকেশন (COMA)}}
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
{\LARGE \bn{মডার্ন কম্পিউটার অ্যাপ্লিকেশন (COMA)}}\\[8pt]
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
\Q \bn{<<< MCQ question text in Bangla, tech terms in English >>>}
\begin{opts}\item optionA \item optionB \item optionC \item optionD\end{opts}
% ... repeat until 21 MCQs ...
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

## 🇬🇧 GOLD TEMPLATE — English variant (differences only)

To produce the **English** version, keep the same structure but change:

```latex
% Remove these (not needed for English):
%   \usepackage{fontspec}
%   \usepackage{polyglossia}
%   \setmainlanguage / \setotherlanguage
%   \newfontfamily\bengalifont ... and the \bn command

% Keep standard packages; for code + diagrams use portable fallbacks:
\usepackage{amsmath,amssymb}
\usepackage{fancyvrb}   % code blocks (portable; use if 'listings' unavailable)
% ER diagram as text:  \fbox{MEMBER} ---< \fbox{Issues} >--- \fbox{BOOK}

% Group banners in English:
\groupbanner{GROUP -- A \quad ( Multiple Choice Type Questions )}
\groupbanner{GROUP -- B \quad ( Short Answer Type Questions )}
\groupbanner{GROUP -- C \quad ( Broad / Descriptive Type Questions )}

% Official instruction block (English):
% "Special credit will be given for answers which are brief and to the point.
%  Marks will be deducted for spelling mistakes, untidiness and bad handwriting.
%  Figures in the margin indicate full marks for the questions."
```
Drop the `\bn{}` wrapper entirely and write questions in plain English. Compile with **pdfLaTeX**.

---

## 📝 EXPLAINED ANSWER PAPER — extra prompt add-on

Append this when you also want a detailed answer key (filename: `Paper<N>-A-<Language>`):

```
Also create an EXPLAINED ANSWER PAPER. For EVERY question:
1. Restate the full question (with a small blue marker/number and marks on the right).
2. Below it, add a green "Answer & Explanation" heading (in Bangla: "উত্তর ও ব্যাখ্যা :").
3. Give a detailed, longer explanation: the correct option, WHY it is correct,
   WHY the others are wrong, with real examples.
4. For Group C, include code blocks (framed), comparison tables, and a simple
   ER diagram. Keep code and SQL in English.
Filename style: Paper1-A-Bangla (Bangla) or Paper1-A-English (English).
```

---

## ✅ Compile Checklist (paste-into-Overleaf steps)

1. Go to **overleaf.com → New Project → Blank Project**.
2. Paste the generated `.tex`.
3. **Bangla:** Menu → Settings → **Compiler = XeLaTeX**. (English: pdfLaTeX is fine.)
4. Click **Recompile**.
5. If Bangla shows boxes (□) on conjuncts → confirm compiler is **XeLaTeX** and font is **Kalpurush** (or try **Noto Serif Bengali**).

---

## 🧠 Key Facts to Remember (so results stay consistent)

- **Pattern is fixed:** 21 MCQ + 14 Short + (7 broad, answer any 5) = **70 marks**.
- **Bangla needs XeLaTeX + Kalpurush** — pdfLaTeX/LuaLaTeX will fail or show boxes.
- **Keep tech terms in English** inside Bangla papers (SQL, Python, B2B, OLAP, etc.).
- **Bangla numerals** (১ ২ ৩ …) in headings/marks for authenticity.
- **Portable packages:** prefer `fancyvrb` over `listings`, and a text ER diagram
  over `tikz`, if you want it to compile on any minimal TeX install.
- **Custom commands** to reuse: `\bn{}`, `\groupbanner{}`, `\qmarks{}`,
  `qlist`, `opts`, `parts`, `instructionbox`.
```
