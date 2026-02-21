# CV Resume Agentic Building

Maintain your CV at a higher level of abstraction using coding agents.

https://github.com/user-attachments/assets/0ef93cae-9ad0-4564-a6ef-3d8f5d3aec4c

---

## Motivation

2025 changed how we code. We now work with AI agents that understand context, make intelligent edits, and iterate on feedback. So why are we still manually tweaking CV bullet points and reformatting layouts by hand?

**The problem:** CV maintenance is tedious. Every job application means copying content, adjusting formatting, and hoping you didn't break the layout. Version control is an afterthought. Tailoring for ATS systems feels like guesswork.

**The solution:** Treat your CV like code. LaTeX provides the structure. Coding agents provide the intelligence. Git provides the history. You provide the direction.

**The kicker:** You're probably already paying for a coding agent subscription. Why not squeeze more value out of it? Your Claude or Cursor subscription isn't just for code - it's for any structured text problem. CVs included.

---

## Why This Approach Works

- **LaTeX decouples content from presentation** - Change your layout without touching your achievements. Update your experience without breaking your design.
- **Agents can edit LaTeX like any code** - They understand the structure, can make targeted changes, and iterate based on your feedback.
- **Git provides versioning, branching, and tracking** - See exactly what changed between versions. Branch for different job applications. Tag your submissions.

---

## Use Cases

1. **Match CV to job descriptions for higher ATS scores** - Feed in a job posting and let the agent optimize your bullet points for keyword alignment
2. **Optimize achievement writing** - Transform weak bullets into quantified, action-driven statements
3. **Change layout without touching content** - Swap templates or adjust formatting while preserving your carefully crafted text
4. **Get expert CV reviewer evaluation** - Use agents to critique your CV like a professional recruiter would
5. **Version and branch for different applications** - Maintain a master CV while creating targeted variants for specific roles

---

## Folder Structure

```
├── templates/                  # CV layout templates (preamble stays here)
│   ├── gergely/                # Pragmatic Engineer style - 3-column header, blue sections
│   │   ├── master.tex          # Sample CV content
│   │   ├── master.pdf          # Preview of this template's styling
│   │   └── preamble.tex        # Layout and styling definitions
│   ├── gogo/                   # Clean professional style by Listiarso Wastuargo
│   │   ├── master.tex
│   │   ├── master.pdf          # Preview of this template's styling
│   │   └── preamble.tex
│   └── harshibar/              # Minimal style based on Jake Yang's template
│       ├── master.tex
│       ├── master.pdf          # Preview of this template's styling
│       └── preamble.tex
├── prompts/                    # AI prompt templates for CV operations
│   └── job_desc_match.md       # CV-to-job-description matching prompt
├── v1/                         # Your personalized CV (created from a template)
│   ├── master.tex              # Your CV - references preamble from templates/
│   └── <company>/              # Job-specific variant
│       ├── main.tex            # Optimized CV for this application
│       └── job_desc.md         # Target job description
└── .devcontainer/              # Docker dev container config
```

### How the folders work

- **`templates/`** - Each folder is a complete CV template with its own styling (`preamble.tex`) and sample content (`master.tex`). Preamble stays centralized here — your `v1/` references it via repo-root path.
- **`prompts/`** - Collection of battle-tested prompts for specific use cases. Start with `job_desc_match.md` to tailor your CV for a specific role.
- **`v1/`** - Your working CV. Contains `master.tex` which references a template's preamble via `\input{../templates/<name>/preamble}`. Create subfolders for job-specific variants.

---

## What You Get

- **Zero LaTeX setup** - Docker handles the entire TeX Live installation
- **Battle-tested template** - A clean, professional CV layout that compiles reliably
- **Working agent prompts** - Prompts that actually work with Claude, GPT-4, and other coding agents
- **Workflow examples** - See how to structure job-specific variants

---

## Quick Start

### Prerequisites

- [VS Code](https://code.visualstudio.com/)

### Setup (Dev Container)

1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/) and [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
2. Click **"Reopen in Container"** when prompted
3. Choose a template and set up your v1/ - see **Choosing a Template** below

### Setup (Manual)

Install [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) for VS Code.

#### Mac ARM

1. `brew install --cask mactex-no-gui`
2. Add TeX to PATH:
   - **bash/zsh:** `eval "$(/usr/libexec/path_helper)"`
   - **other shells:** add `/usr/local/texlive/YYYY/bin/universal-darwin` to PATH (replace `YYYY` with your installed TeX Live version year)
3. Verify installation: `latexmk -pdf templates/harshibar/master.tex`
4. Choose a template and set up your v1/ - see **Choosing a Template** below

Currently, these manual setup instructions are documented for **Mac ARM only**. Contributions for other platforms (Mac Intel, Windows, Linux) are welcome.

---

## Choosing a Template

Browse the template PDFs directly in the repository to see which style you prefer:
- **[gergely](templates/gergely/master.pdf)** - Pragmatic Engineer style with 3-column header and blue section headings
- **[gogo](templates/gogo/master.pdf)** - Clean professional style by Listiarso Wastuargo
- **[harshibar](templates/harshibar/master.pdf)** - Minimal style based on Jake Yang's template

Once you've chosen a template:

1. Fork this repository
2. Clone your fork and open in VS Code

3. **Remove the existing `v1/`**:
   ```
   rm -rf v1/
   ```

4. **Copy the template's `master.tex`** into a new `v1/` folder:
   ```
   mkdir v1 && cp templates/gergely/master.tex v1/
   ```
   Then update the first line of `v1/master.tex` to reference the template's preamble:
   ```latex
   \input{../templates/gergely/preamble}
   ```

5. Edit `v1/master.tex` with your own content - the preamble handles all styling.

---

## Releases

See the GitHub Releases tab for version history and release notes.

