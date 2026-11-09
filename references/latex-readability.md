# LaTeX presentation that helps readers

Use the paper's layout to reveal the argument: what matters, how ideas relate, and where readers can find the detail. These are adaptable options, not a required visual style or package list. The snippets are illustrative and assume the document class supports the commands used.

## Make headings useful when scanning

Prefer concise headings that identify the point of the subsection. In Results and Discussion, a finding or implication can give readers an immediate takeaway. Methods headings can describe the activity or question. Use the strongest wording the section actually supports.

```latex
\subsection{Participants valued the option to revise}
\label{sec:revision-option}
```

Use the class's `\section`, `\subsection`, and related commands for the actual hierarchy. Bold text is useful for emphasis or a short label, but does not replace section structure. A reader scanning the headings should be able to follow the paper's main questions and takeaways.

## Give the central question room to stand out

After establishing the need, a standalone question or problem statement can make the paper's focus easy to locate. For example:

```latex
This motivates our central question:
\begin{quote}
  \centering
  \emph{How can people inspect a result and decide what to change?}
\end{quote}
```

This is an author-written question, not participant speech. The surrounding text should explain why it matters and how the paper addresses it. A plain standalone paragraph or a venue-provided callout may work equally well. Centering, italics, or a box are optional; a short passage needs only enough emphasis to be noticeable.

For a short introduction and question, `samepage` can help keep the passage together when a split disrupts reading. Inspect the result: a large unbreakable block can leave an awkward gap. Keep a central question in the narrative rather than turning it into a floating figure that may move away from its context.

## Let participant voices be distinct and meaningful

Choose excerpts that illuminate an experience or explain a finding. Introduce the point, present the participant's words, and explain their significance where it is not already apparent. Short phrases can remain inline; longer extracts may benefit from a class-supported `quote` or `quotation` environment.

```latex
\begin{quote}
  ``[Insert a verbatim participant excerpt here.]''
  \par
  \hfill(Pxx)
\end{quote}
```

The brackets and identifier are placeholders, not participant data. Use the actual excerpt and an appropriate consistent attribution. Preserve its meaning and make omissions or editorial additions visible. Prominence makes the voice distinguishable; it does not by itself establish credibility, prevalence, or a universally shared experience. Quotations should contribute to the analysis, not merely decorate the page.

## Make figures and captions carry a clear point

Introduce a figure near the passage where it helps explain the idea. Use readable labels, stable panel names, and a caption that identifies the comparison or sequence and the main point. Include conditions, units, or symbols when readers need them. Put essential explanatory content in the paper rather than requiring readers to decipher a screenshot's tiny interface text.

For an `acmart` workflow that uses `\Description`, a basic pattern is:

```latex
\begin{figure}[tbp]
  \centering
  \includegraphics[width=\linewidth]{figure-file}
  \caption{What the figure shows and the point it explains.}
  \label{fig:comparison}
  \Description{An alternative description of the meaningful visual content.}
\end{figure}
```

Replace the file and text with the actual figure and description. `\Description` is class-specific; modern tagged workflows may instead use an `alt` key on `\includegraphics`. Follow the installed class, toolchain, and venue's current instructions. A useful caption explains the figure alongside the image; an alternative description communicates its essential visual information when the image is unavailable.

## Make comparisons and technical detail easy to follow

Use a table for a genuine comparison, with informative row/column headings, units, and appropriate precision. Keep related values aligned and make emphasis understandable without relying only on color. Where the class supplies `booktabs`, a simple structure is:

```latex
\begin{table}[tbp]
  \caption{The inspection and revision actions available in each workflow.}
  \label{tab:workflow-actions}
  \centering
  \begin{tabular}{lll}
    \toprule
    Workflow & Inspect & Revise \\
    \midrule
    A & Preview & Prompt \\
    B & Preview and source & Prompt or edit \\
    \bottomrule
  \end{tabular}
\end{table}
```

The table entries are synthetic examples. Adapt the width and layout to real content and the publication column. Simple tables can be clearer than dense grids or pictures of tables. In tagged PDFs, identify table headers using the supported tagging workflow.

Introduce equations and code by explaining the idea they express, define unfamiliar symbols near their use, and connect the result back to the argument. A worked example or diagram may make a complex mechanism easier to understand. Use lists for genuine parallel items or steps; keep connected reasoning in prose.

## Keep the document navigable and comfortable to read

Use labels and references such as `Figure~\ref{fig:comparison}` so numbering follows revisions. Keep emphasis selective. Let the venue class provide the normal fonts, margins, heading styles, and spacing; check compatibility before adding packages. Prefer natural float placement, making targeted adjustments when the rendered result interrupts the explanation.

Where accessibility is relevant, preserve real text, meaningful heading structure, image alternatives, and logical reading order. Check current class/package support before changing PDF tagging or the compiler. A visually clear PDF and a correctly tagged PDF are related goals; confirm the aspects the task requires rather than assuming that compilation proves both.

After meaningful layout changes, compile and inspect the affected pages at reading size. Look for crowded callouts, stranded headings, detached attributions, illegible figure labels, and comparisons separated from their explanations. If needed, also inspect text extraction, tags, or reading order. Make changes that improve the reader's path without turning the paper into a collection of competing highlights.

See [sources.md](sources.md) for the supporting research and document guidance.
