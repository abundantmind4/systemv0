# Archway — Systems Engineering Platform

A unified product lifecycle platform for systems engineering projects. Built for enterprise engineering organizations in aerospace, defense, and regulated industries.

## Live Demo

Deploy to GitHub Pages and access at `https://<your-username>.github.io/archway/`

## Features

- **Dashboard** — Metrics overview with requirements coverage, task progress, verification methods, activity feed
- **Diagram Editor** — Drag-and-drop MBSE canvas with all SysML element types (Block, Activity, State, Interface, Package, Constraint, Sequence, Requirement), zoom/pan, connections, 4 pre-built diagrams
- **Requirements Traceability** — Interactive tree with parent/child hierarchy, status filtering, verification methods, bidirectional links to elements and tasks
- **Tasks / Kanban** — Board and list views, status changes, priority, assignees, requirement tracing
- **Workspace Chat** — Team messaging with inline item references (type `req-001` or `task-002` to auto-link)
- **Export** — Report generator with traceability matrix preview

## Deploy to GitHub Pages

### Option A: Quick (GitHub Web UI)

1. Go to [github.com/new](https://github.com/new) and create a repo named `archway`
2. Click **"uploading an existing file"** on the new repo page
3. Drag `index.html` into the upload area and commit
4. Go to **Settings → Pages → Source** → select `main` branch, `/ (root)` folder → **Save**
5. Wait 1-2 minutes, then visit `https://<your-username>.github.io/archway/`

### Option B: Git CLI

```bash
git init archway
cd archway
cp /path/to/index.html .
git add index.html
git commit -m "Initial commit — Archway MVP"
git branch -M main
git remote add origin https://github.com/<your-username>/archway.git
git push -u origin main
```

Then enable Pages in Settings as described above.

## Demo Data

The app ships with a realistic **LEO-SAT Mission** (Low Earth Orbit Satellite) workspace containing:

- 12 system elements (subsystems, interfaces, activities, states)
- 12 requirements with parent/child hierarchy and verification methods
- 10 tasks across 4 status columns
- 15 relationships (composition, dependency, transition)
- 4 diagrams (BDD, IBD, State Machine, Requirements)
- 6 chat messages with item references
- 6 version history entries

## Tech Stack

- React 18 (CDN)
- Single HTML file, zero build step
- Inline SVG icons (no external icon dependencies)
- DM Sans + JetBrains Mono typography
- CSS custom properties design system

## Architecture

All state is held in React `useState` hooks with seed data initialized on load. No backend required — this is a fully client-side prototype designed for VC demos and stakeholder walkthroughs.

The data model is graph-based: nodes (elements, requirements, tasks) connected by edges (composition, dependency, transition, verification links). All views read from the same state, so changes in the diagram editor reflect in requirements and task views.
