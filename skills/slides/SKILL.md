---
name: slides
description: Turn the current conversation's findings, or the repo itself, into a LaTeX Beamer deck compiled with tectonic. Plans the slide outline and waits for confirmation before writing the .tex.
---

Write a Beamer deck that summarises the current conversation's findings, or the repo itself when asked. Do not write the `.tex` file first. Plan it, show the plan, and wait.

## Process

1. Decide the subject. Default to the findings in the current conversation. If the user asks for an overview of the repo instead, explore it first: the code, the docs, and the skills it holds.

2. Decide the language. Write in the language of the conversation, unless the user names another one.

3. Plan the deck before you write any `.tex`. List the title, and one line per slide: its heading and its one-sentence gist. Show this plan to the user. Wait for confirmation. On a change, update the plan and show it again. Do not write the file until the user confirms.

4. Once confirmed, find the next free three-digit number `NNN` under `docs/slides/`. With no decks yet, start at `000`. Create `docs/slides/<NNN>-<kebab-case-name>/main.tex` from the template below.

5. Compile it: run `tectonic main.tex` inside `docs/slides/<NNN>-<kebab-case-name>/`. On a compile error, read it, fix the `.tex`, and compile again. Stop and show the user the raw error if it still fails after three tries.

6. Tell the user the path to the `.tex` file and the compiled PDF.

## Style

- One idea per slide. One idea per bullet.
- Short phrases over full sentences. Cut the verb when the noun says it.
- No filler: no "as we can see", no restating the title in the first bullet.
- Technical register. Keep the field's own terms; do not soften them for a lay reader.
- Prefer a table or a formula to a paragraph, when either carries the same decision.
- Six bullets per slide at most. Split a slide that needs more.

## Template

<beamer-template>

```latex
\documentclass[aspectratio=169]{beamer}
\setbeamertemplate{navigation symbols}{}

\title{<title>}
\author{<author, optional>}
\date{\today}

\begin{document}

\frame{\titlepage}

\begin{frame}{<Slide title>}
\begin{itemize}
  \item <point>
\end{itemize}
\end{frame}

\end{document}
```

</beamer-template>
