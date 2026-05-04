# AGENTS.md

Context and conventions for AI coding agents (Claude Code, GitHub Copilot, etc.) working in this repository.

---

## Repository Purpose

This is a GitHub profile README repository. The `README.md` is displayed publicly on [github.com/nitrocode](https://github.com/nitrocode). It functions as a portfolio and professional landing page.

---

## Owner

RB, Cloud Architect, CEO of RB Consulting.

Focus areas:
- AWS multi-account architectures, FinOps
- Infrastructure as Code (Terraform, OpenTofu)
- Platform Engineering (Kubernetes, GitOps, internal developer platforms)
- AI-native engineering teams and agentic workflows
- Security: policy enforcement, compliance automation, zero-trust
- Leadership: project management, team building, client advisory

---

## Writing Style

Write in a direct, technical, first-person voice. Match the tone already established in `README.md`.

Avoid these AI writing artifacts:
- Filler openers: "Certainly!", "Of course!", "Great question!", "Happy to help!"
- Redundant summaries that restate what was just said
- Hedge phrases: "I'll help you with that", "Let me assist you"
- Em-dashes
- Bold text for emphasis
- Vague superlatives: "cutting-edge", "robust", "seamless", "game-changer"
- Passive constructions where active voice reads better
- Bullet lists that pad short ideas into three-word fragments

Preferred patterns:
- Short sentences. Active voice.
- Technical precision over marketing language
- Concrete examples over abstract claims
- If something can be said in one sentence, use one sentence

---

## Content Guidelines

- Keep the profile focused on Cloud, IaC, Platform Engineering, and AI-native engineering
- Highlight Claude Code and Claude Skills: these are current, in-use tools, not just listed buzzwords
- Do not add LangChain, CrewAI, or similar orchestration frameworks unless RB explicitly requests them
- Do not add technologies or skills that are not already present in the README unless explicitly asked
- Badges use `style=for-the-badge` and pull colors from each tool's official brand palette
- The "If you touched it twice, it should be code." quote is intentional. Do not modify or remove it.
- The profile links (Resume, Blog, Contact) point to: `https://0xfeed.gitlab.io/resume.html`, `https://0xfeed.gitlab.io`, and `https://bit.ly/2K7e76D` respectively

---

## Link and Image Health

A weekly GitHub Actions workflow (`.github/workflows/link-check.yml`) uses [lychee](https://github.com/lycheeverse/lychee-action) to verify all links and images in `README.md`.

Dynamic badge widgets are excluded from checks because they return SVG rather than standard HTTP responses:
- `https://komarev.com`
- `https://streak-stats.demolab.com`
- `https://github-readme-stats.shion.dev`
- `https://readme-typing-svg.demolab.com`

If adding a new link or image, make sure it resolves to a stable URL. Avoid short-lived demo URLs or localhost references.

---

## File Structure

```
README.md                  # public GitHub profile page
AGENTS.md                  # this file; AI agent context and conventions
CLAUDE.md                  # symlink to AGENTS.md
renovate.json5             # Renovate config; inherits best-practices, pins actions to SHAs
LICENSE
.github/
  workflows/
    link-check.yml         # weekly dead-link/image checker
```

---

## Dependency Management

GitHub Actions are pinned to full commit SHAs (`uses: owner/action@<sha> # vX.Y.Z`). Renovate manages these via `renovate.json5`, which inherits `config:best-practices` and sets `pinDigests: true`.

When adding a new workflow step, pin the action to its SHA and add a version comment. Find the SHA with:

```sh
gh api repos/<owner>/<repo>/git/ref/tags/<tag> --jq '.object.sha'
```

---



- Do not rewrite large portions of `README.md` speculatively. Make targeted, minimal changes.
- Do not add sections, stats widgets, or third-party integrations without being asked
- Do not remove the GitHub Stats or Streak sections
- Do not commit secrets, tokens, or personal contact details not already in the file
- Do not change badge colors or styles without an explicit reason
