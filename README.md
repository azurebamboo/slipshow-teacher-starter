# Slipshow Teacher Starter: Zero-Install Cloud Slides

Welcome to the **Slipshow Teacher Starter** template!

This repository enables educators to create fluid, non-linear [Slipshow](https://slipshow.org) presentations directly inside their web browser—**with zero terminal commands and zero software installation required on district-locked computers**.

Every time you edit your Markdown slides here on GitHub, a free cloud workflow automatically compiles your presentation and publishes it to a live website.

---

## 🏛️ What's Inside This Sample (`presentation.md`)?

This template comes pre-loaded with an advanced, interactive Digital Humanities presentation: **"Federalist No. 10: Factions, the Extended Republic & the Algorithmic Age"**.

It demonstrates six key capabilities of Slipshow that **PowerPoint and Google Slides simply cannot do**:

1. **Continuous Canvas & Viewport Gliding (`{pause up=...}`, `{pause down=...}`):**
   - No arbitrary $16:9$ slide boundaries. The presentation exists on a fluid vertical landscape where the camera glides down through the primary source document.
2. **Micro-Textual Camera Zooming (`{pause focus=...}`):**
   - The camera zooms directly into specific contentious clauses of James Madison's 1787 text, highlights archaic phrases in color, and pulls back (`{pause unfocus}`) to reveal the macro-argument without losing context.
3. **Inspectable Vector Logic Trees (Mermaid.js):**
   - Madison's diagnostic tree ("Curing the Mischiefs of Faction") is defined in clean, plain-text code that renders crisp vector diagrams automatically.
4. **Historiographical Multi-Perspective Synoptic Slips:**
   - Evaluates three conflicting historical realities side-by-side: Madison's Federalist defense, *Brutus No. 1*'s Anti-Federalist counter-argument, and the constitutional exclusion of enslaved Black Americans.
5. **Mathematical & Network Theory Modeling (KaTeX):**
   - Native LaTeX mathematical formulas formalizing the Madisonian institutional theorem ($\mathcal{S} \uparrow \implies |\mathcal{F}| \uparrow \implies \mathbb{P}(\text{Tyranny}) \downarrow$) and contrasting it with the latency-zero dynamics of modern algorithmic feeds.
6. **Live Whiteboard Inking Mode (<span class="keyboard-shortcut">D</span> key):**
   - Press **`D`** on your keyboard during a live class or Zoom seminar to draw annotations, arrows, and circles directly on the canvas!

---

## 🚀 3-Minute Quick Start

### Step 1: Copy This Template to Your Account
1. Click the green **"Use this template"** button at the top right of this page.
2. Select **"Create a new repository"**.
3. Name your repository (e.g., `civic-slides` or `ap-gov-unit-1`).
4. Keep the repository **Public**, then click **"Create repository"**.

### Step 2: Enable GitHub Pages (One-Time Setup)
1. In your new repository, click **Settings** (top menu bar).
2. In the left navigation sidebar, click **Pages**.
3. Under **Build and deployment > Source**, click the dropdown and select **GitHub Actions** (instead of *Deploy from a branch*).
   *(That's it! GitHub Actions is now authorized to build your site.)*

### Step 3: Edit or Add Your Slides
1. Return to the main **Code** tab of your repository.
2. Click on `presentation.md`.
3. Click the **Pencil icon** (Edit this file).
4. Paste your primary source notes or AI-generated Slipshow Markdown.
5. Scroll down and click the green **Commit changes** button.

### Step 4: View Your Live Presentation
1. Click the **Actions** tab at the top of your repository. You'll see a green checkmark appear within ~20 seconds.
2. Visit your live site at:
   ```text
   https://<your-github-username>.github.io/<your-repo-name>/
   ```
3. **Presenting live:** Open the link in any classroom browser and use Arrow Keys or Spacebar to navigate.
4. **Offline backup:** Right-click the page, select **"Save Page As..."**, and save the self-contained `index.html` file to your laptop or USB drive. It will work completely offline without internet!

---

## 💡 Keyboard Controls in Slipshow
- **Next step / scroll camera:** `Spacebar` or `Right Arrow` / `Down Arrow`
- **Previous step:** `Left Arrow` / `Up Arrow`
- **Toggle Table of Contents / Outline:** `T`
- **Drawing Mode:** `D` (draw directly on your presentation canvas with mouse or touchscreen)

---

## 📂 Multi-Presentation Support

Want to host multiple lectures in one repository?
Just upload or create additional `.md` files (e.g., `unit-1.md`, `unit-2.md`, `federalist-10.md`). 

The cloud workflow compiles every `.md` file automatically:
- `presentation.md` becomes your home page: `https://<username>.github.io/<repo>/`
- `federalist-10.md` becomes: `https://<username>.github.io/<repo>/federalist-10.html`

---

## 🛠️ Slipshow Syntax Cheat Sheet for Educators

| Feature | Slipshow Syntax | Pedagogical Use Case |
| :--- | :--- | :--- |
| **Step Pause** | `{pause}` | Reveal text or bullet points incrementally |
| **Scroll to Top** | `{pause up=section-id}` | Smoothly pan viewport so a section title sits at the top |
| **Scroll to Bottom** | `{pause down=target-id}` | Bring a lower quote or table into view |
| **Center Viewport** | `{pause center=target-id}` | Center a diagram or question card on screen |
| **Zoom In** | `{pause focus=element-id}` | Zoom into a specific primary source phrase or vocabulary term |
| **Zoom Out** | `{pause unfocus}` | Return the camera to full canvas overview |
| **Semantic Callout** | `{.definition title="..."}` | Highlight core civic terms, theorems, or DBQ prompts |
| **Mermaid Flowchart** | ````mermaid ... ```` | Draw inspectable branching decision trees and causality maps |
| **LaTeX Math** | `$P(\text{tyranny}) \downarrow$` | Formalize constitutional theory, economics, or polling data |
