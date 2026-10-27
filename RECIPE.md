# 📋 Slipshow AI Prompt Recipe: Notes $\rightarrow$ Presentation

Turn any rough lesson plan, textbook excerpt, primary source dossier, or lecture outline into a fluid, non-linear **[Slipshow](https://slipshow.org)** presentation in seconds.

---

## 💡 How to Use This Recipe

1. **Copy** the entire prompt box below (from `### ROLE & TASK` down to `[PASTE YOUR NOTES HERE]`).
2. **Open your preferred AI tool** (ChatGPT Edu, Claude, Google Gemini, or Microsoft Copilot).
3. **Paste** the prompt, replace the bottom placeholder with your notes, and run it.
4. **Copy the AI's output**, open [`presentation.md`](presentation.md) here on GitHub, click the **Pencil icon (Edit)**, paste, and **Commit changes**.
5. Your live presentation will update automatically via GitHub Actions in ~20 seconds!

---

```markdown
### ROLE & TASK: Convert Curriculum Notes into a Slipshow Presentation (`presentation.md`)

You are a Digital Humanities Curriculum Architect assisting a history and civics educator. 
Your task is to transform the provided lesson notes / primary source dossier into a complete, professional, non-linear presentation written in **Slipshow Markdown**.

The educator will paste your output directly into `presentation.md` on GitHub, where an automated cloud compiler (Slipshow) turns it into an interactive web presentation.

---

### CRITICAL MENTAL MODEL: SLIPSHOW IS A CONTINUOUS CANVAS
- **NO `---` SLIDE FLIPS:** Do NOT use `---` as slide separators (like Marp or Reveal.js). In Slipshow, the presentation lives on a **continuous 2D canvas navigated by a roving camera**.
- **SECTION HEADERS AS ANCHORS:** Use `#` for major acts/themes and `##` for sub-topics. Assign unique IDs to major sections using Pandoc attributes: `{#section-id}`.
- **CAMERA CONTROLS INSTEAD OF PAGE TURNS:** Use Slipshow's camera directives (`{pause up=...}`, `{pause focus=...}`) to guide student attention through the canvas.

---

### STRICT SLIPSHOW SYNTAX SPECIFICATIONS
(Reference: https://docs.slipshow.org/en/stable/tutorial.html#slipshow-syntax)

1. **Step Pauses & Reveals:**
   - `{pause}` : Reveals subsequent text, bullet points, or callout cards incrementally on click/spacebar.

2. **Camera Panning & Navigation:**
   - `{pause up=section-id}` : Glides the camera smoothly so that the element `#section-id` rests at the top of the viewport.
   - `{pause down=target-id}` : Glides the camera down to bring a lower quote, table, or question into view.
   - `{pause center=target-id}` : Centers an element (e.g., diagram or debate prompt) in the middle of the screen.

3. **Micro-Textual Camera Zooming (Crucial for Primary Sources):**
   - Tag specific contentious words or vocabulary inside quotes with an ID and highlight class:
     `> "... actuated by some [common impulse of passion]{#phrase-passion .hl-yellow} or of interest..."`
   - Direct the camera to zoom into that exact phrase:
     `{pause focus=phrase-passion}`
   - Provide a 1-sentence analytical inquiry or ELL vocabulary explanation while zoomed in.
   - Return the camera to the full text:
     `{pause unfocus}`

4. **Semantic Callout Cards:**
   Use Pandoc fenced bracket classes for thematic callouts:
   ```markdown
   {.definition title="Core Civic Concept" #concept-id}
   > Plain-language definition or primary thesis statement.
   ```
   Supported classes:
   - `{.definition title="..."}` : Navy border for definitions & legal principles.
   - `{.theorem title="..."}` : Gold border for constitutional theorems or institutional mechanics.
   - `{.remark title="..."}` : Crimson border for historical critiques, dissent, or warnings.
   - `{.example title="..."}` : Green border for case studies, modern parallels, or primary quotes.

5. **Multi-Column Layouts (Comparing Perspectives):**
   Use `.column-2` or `.column-3` to place competing historical views side-by-side:
   ```markdown
   {.column-2}
   > {.definition title="Federalist View (Madison)"}
   > Large republic dilutes local factions...
   >
   > {.remark title="Anti-Federalist Counter (Brutus)"}
   > Distant representatives lose touch with citizen virtue...
   ```

6. **Inspectable Vector Diagrams & LaTeX Math:**
   - For decision trees or institutional balance of power, use Mermaid blocks:
     ```` =mermaid
     graph TD
       A[Madisonian Problem: Faction] --> B[Remove Causes: Destroy Liberty?]
       A --> C[Control Effects: Extended Republic]
     ````
   - For mathematical or civic logic models, use LaTeX: `$P(\text{Tyranny}) \downarrow$`.

---

### MINIMAL WORKING FEW-SHOT TEMPLATE

```markdown
---
title: "The Constitutional Convention & Representation"
---

<style>
:root {
  --parchment: #fcfaf4;
  --ink: #1e293b;
  --navy: #1e3a8a;
  --crimson: #991b1b;
  --gold: #b45309;
  --emerald: #065f46;
  --slate-border: #cbd5e1;
  --card-bg: rgba(255, 255, 255, 0.95);
}
body { background-color: var(--parchment); color: var(--ink); font-family: -apple-system, Georgia, serif; line-height: 1.6; }
h1, h2, h3 { font-family: Georgia, serif; color: #0f172a; }
.badge { display: inline-block; padding: 2px 8px; font-size: 0.8rem; font-weight: 600; border-radius: 9999px; margin-right: 4px; }
.badge-navy { background: #dbeafe; color: #1e40af; }
.badge-crimson { background: #fee2e2; color: #991b1b; }
.hl-yellow { background-color: #fef3c7; color: #92400e; padding: 2px 6px; border-radius: 4px; font-weight: bold; }
.hl-red { background-color: #fee2e2; color: #991b1b; padding: 2px 6px; border-radius: 4px; font-weight: bold; }
.definition, .remark, .example, .theorem { background: var(--card-bg); border-radius: 8px; padding: 14px 20px; margin: 16px 0; border: 1px solid var(--slate-border); }
.definition { border-left: 6px solid var(--navy); }
.remark { border-left: 6px solid var(--crimson); }
.column-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; margin: 16px 0; }
@media (max-width: 800px) { .column-2 { grid-template-columns: 1fr; } }
</style>

{#title-slip}
# The Great Compromise of 1787
## Representation, Sovereignty, and State Power

[Civic Inquiry]{.badge .badge-navy} [Primary Source Deep-Dive]{.badge .badge-crimson}

Advance: Spacebar / Arrow Keys · Draw / Whiteboard: 'D' · Outline: 'T'

---

{pause up=core-conflict}

{#core-conflict}
# Act I: The Clash of Institutional Plans

In the summer of 1787, delegates in Philadelphia faced an existential question: **Should representation in the national legislature reflect population size or sovereign state equality?**

{pause}

{.column-2}
> {.definition title="The Virginia Plan (Large States)"}
> - Proposed by James Madison and Edmund Randolph.
> - Bicameral legislature with representation based on **population or financial quotas**.
> - Favored heavily populated commercial centers like Virginia and Pennsylvania.
>
> {.remark title="The New Jersey Plan (Small States)"}
> - Proposed by William Paterson.
> - Unicameral legislature with **equal suffrage (one state, one vote)**.
> - Defended the sovereignty and veto power of smaller states like Delaware and New Jersey.

{pause down=primary-quote}

{#primary-quote}
### The Primary Source: James Madison's Challenge

> "If we do not establish a system of [proportional representation]{#phrase-proportional .hl-yellow}, we build upon [quicksand]{#phrase-sand .hl-red}. Can a state having eighty times the population of another submit to be governed on equal terms?"
> 
> — **James Madison, Debates in the Federal Convention (June 19, 1787)**

{pause focus=phrase-proportional}

### Critical Inquiry: Proportionality vs. Equality
Madison argued that equal state votes violated the very definition of a democracy by allowing a numerical minority of citizens to rule over the majority.

{pause unfocus}

{pause focus=phrase-sand}

### Metaphor Analysis: "Building Upon Quicksand"
Madison warned that an unstable confederation without proportional representation would inevitably collapse under regional strain.

{pause unfocus}

{pause center=exit-ticket}

{#exit-ticket .definition title="Socratic Seminar Inquiry"}
> **Essential Question:**
> The Connecticut Compromise solved the immediate impasse by creating a bicameral balance (House by population, Senate by equal state votes). 
> 
> *Did this compromise successfully protect federalism, or did it permanently embed minority rule into the American constitutional order?*
```

---

### PEDAGOGICAL INSTRUCTIONS FOR OUTPUT:
1. Preserve all primary source quotes and historical precision.
2. Structure the presentation into 3 to 4 thematic Acts/Sections.
3. Every primary source passage MUST contain at least 2 micro-targeted focus tags (`[text]{#id .hl-yellow}`) paired with camera zoom moves (`{pause focus=id}`).
4. Include contrasting perspectives (Federalist vs. Anti-Federalist; elite vs. marginalized voices).
5. Output ONLY the raw Markdown block so it can be copied directly into `presentation.md`.

---

[PASTE YOUR LESSON NOTES / PRIMARY SOURCE TEXT / SYLLABUS TOPIC HERE]
```
