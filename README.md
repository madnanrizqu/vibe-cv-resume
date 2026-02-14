# CV Resume Agentic Building

**Maintain your CV at a higher level of abstraction using coding agents.**

<video src="demo.mp4" controls="controls" muted="muted" width="600"></video>

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
├── prompts/                    # AI prompt templates for CV operations
│   └── job_desc_match.md       # CV-to-job-description matching prompt
├── v1/                         # Version 1 of CV templates
│   ├── master.tex              # Base CV - your source of truth
│   └── lottiefiles/            # Job-specific variant example
│       ├── main.tex            # Optimized CV for this application
│       └── job_desc.md         # Target job description
└── .devcontainer/              # Docker dev container config
```

### How the folders work

- **`prompts/`** - Collection of battle-tested prompts for specific use cases. Start with `job_desc_match.md` to tailor your CV for a specific role.
- **`v1/`** - Folder-based versioning. `master.tex` is your base CV. Create subfolders (like `lottiefiles/`) for each job application with an optimized variant.

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
2. Fork this repository
3. Clone your fork and open in VS Code
4. Click **"Reopen in Container"** when prompted
5. Edit `v1/master.tex` and save - your PDF appears automatically

### Setup (Manual)

Install [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) for VS Code.

#### Mac ARM

1. `brew install --cask mactex-no-gui`
2. Add TeX to PATH:
   - **bash/zsh:** `eval "$(/usr/libexec/path_helper)"`
   - **other shells:** add `/usr/local/texlive/YYYY/bin/universal-darwin` to PATH (replace `YYYY` with your installed TeX Live version year)
3. Verify installation: `latexmk -pdf v1/master.tex`

Currently, these manual setup instructions are documented for **Mac ARM only**. Contributions for other platforms (Mac Intel, Windows, Linux) are welcome.

---

## Releases

See the GitHub Releases tab for version history and release notes.

