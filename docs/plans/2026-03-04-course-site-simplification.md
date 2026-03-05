# Course Site Simplification Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Replace the current multi-section, multi-page layout with a single, minimal academic course page containing only title, description, time, syllabus, resources, and contact email.

**Architecture:** One static HTML page (`index.html`) and a minimal stylesheet (`style.css`). No navigation, JS, or additional pages. Single-column layout with clear headings and a simple syllabus table.

**Tech Stack:** HTML5, CSS3 (no frameworks).

---

### Task 1: Replace `index.html` with the single-page minimal layout

**Files:**
- Modify: `index.html`

**Step 1: Replace the file content with the minimal HTML below**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>CS 4891 — Claude Code Course</title>
  <meta name="description" content="A concise course page for CS 4891: Claude Code Course." />
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <main class="container">
    <header>
      <h1>Claude Code Course</h1>
      <div class="subtitle">CS 4891 · Spring 2026</div>
      <p>
        An intensive course on AI-assisted software development using Claude Code. We cover prompt
        engineering, agentic workflows, and modern software engineering practices for building reliable
        systems with LLMs.
      </p>
      <p class="meta">Mon / Wed / Fri · 10:00–11:15 AM · Gates Hall 305 &amp; Online</p>
    </header>

    <section>
      <h2>Course Syllabus (14 Weeks)</h2>
      <table aria-label="Course syllabus">
        <thead>
          <tr>
            <th>Week</th>
            <th>Topic</th>
          </tr>
        </thead>
        <tbody>
          <tr><td>1</td><td>Introduction to Claude Code &amp; AI Development</td></tr>
          <tr><td>2</td><td>Prompt Engineering Fundamentals</td></tr>
          <tr><td>3</td><td>Working with Codebases: Context &amp; Navigation</td></tr>
          <tr><td>4</td><td>Test-Driven Development with AI</td></tr>
          <tr><td>5</td><td>Agentic Workflows &amp; Tool Use</td></tr>
          <tr><td>6</td><td>Multi-Turn Conversations &amp; Context Management</td></tr>
          <tr><td>7</td><td>Refactoring &amp; Code Quality with AI</td></tr>
          <tr><td>8</td><td>Midterm Review &amp; Project Workshop</td></tr>
          <tr><td>9</td><td>Advanced Prompt Patterns &amp; Chain-of-Thought</td></tr>
          <tr><td>10</td><td>CI/CD Integration &amp; AI-Assisted DevOps</td></tr>
          <tr><td>11</td><td>Security, Ethics &amp; Responsible AI Use</td></tr>
          <tr><td>12</td><td>Building Custom AI Workflows</td></tr>
          <tr><td>13</td><td>Capstone Project Work &amp; Peer Review</td></tr>
          <tr><td>14</td><td>Final Presentations &amp; Course Retrospective</td></tr>
        </tbody>
      </table>
    </section>

    <section>
      <h2>Resources</h2>
      <ul>
        <li><a href="https://docs.anthropic.com/en/docs/claude-code/overview" target="_blank" rel="noopener">Claude Code Documentation</a></li>
        <li><a href="https://www.anthropic.com" target="_blank" rel="noopener">Anthropic</a></li>
        <li>Course repository and slides (to be posted)</li>
      </ul>
    </section>

    <section>
      <h2>Contact</h2>
      <p>Email: <a href="mailto:email@example.edu">email@example.edu</a> (placeholder)</p>
    </section>
  </main>
</body>
</html>
```

**Step 2: Quick visual check**

Open the page locally to confirm spacing and hierarchy look clean:

```bash
xdg-open index.html
```

Expected: single-column page with title, description, time, syllabus table, resources, and contact.

**Step 3: Commit**

```bash
git add index.html
```

```bash
git commit -m "refactor(site): simplify course homepage"
```

---

### Task 2: Replace `style.css` with minimal academic styling

**Files:**
- Modify: `style.css`

**Step 1: Replace the file content with the minimal CSS below**

```css
:root {
  --text: #111;
  --muted: #555;
  --rule: #e9e9e9;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  color: var(--text);
  background: #fff;
  line-height: 1.6;
}

.container {
  max-width: 760px;
  margin: 0 auto;
  padding: 48px 24px 64px;
}

h1 {
  font-size: 2rem;
  margin: 0 0 0.25rem;
}

.subtitle {
  color: var(--muted);
  font-size: 0.95rem;
  margin-bottom: 1.25rem;
}

.meta {
  color: var(--muted);
  font-size: 0.95rem;
}

section {
  margin-top: 2rem;
  padding-top: 1.25rem;
  border-top: 1px solid var(--rule);
}

h2 {
  font-size: 1.2rem;
  margin: 0 0 0.75rem;
}

p { margin: 0 0 0.75rem; }

ul { padding-left: 1.2rem; margin: 0; }

li { margin: 0.35rem 0; }

a {
  color: #0b5fff;
  text-decoration: none;
}

a:hover { text-decoration: underline; }

table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.95rem;
}

th, td {
  text-align: left;
  padding: 0.35rem 0;
  border-bottom: 1px solid var(--rule);
}

th { font-weight: 600; color: #333; }
```

**Step 2: Quick visual check**

```bash
xdg-open index.html
```

Expected: clean typography, simple table, no decorative elements.

**Step 3: Commit**

```bash
git add style.css
```

```bash
git commit -m "style(site): reduce page styling"
```

---

### Task 3: Final verification + push

**Files:**
- None (verification only)

**Step 1: Confirm only intended files changed**

```bash
git status --short
```

Expected: clean working tree.

**Step 2: Push to GitHub**

```bash
git push
```

Expected: remote updated; GitHub Pages rebuilds in 1–2 minutes.
```
