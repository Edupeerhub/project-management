# Project Management via GitHub — Hybrid Model for PMs

## 🔁 Hybrid Option: Centralized Planning Repo + Per-Repo Engineering Assignment

**Description:**
This model separates planning and execution by using a centralized project-management repo for PMs to organize deliverables, while still assigning engineers directly in the relevant code repositories (e.g., frontend, backend).

## 🛠 How to Set It Up:

**1. Create a Central Planning Repo (e.g., `project-management`)**

* Create a new private repo for high-level planning and coordination.
* Add all PMs as collaborators.
* Set up GitHub Projects (Table/Kanban) to track features, deliverables, milestones, or sprints.

**2. Create Issues in the Planning Repo**

* Each issue represents a feature, initiative, or deliverable (e.g., “User onboarding flow”).
* Use checklists or linked issues to break it into frontend/backend work.

**3. Link Out to Implementation Repos**

* Create corresponding issues in engineering repos (frontend, backend, etc.).
* Reference them in the planning issue (e.g., `Related to org/backend#42`).
* Assign developers to implementation issues directly.

**4. Use Labels and Milestones**

* Use consistent labels (e.g., `PM-owned`, `Q3-goal`, `needs-spec`) across all repos.
* Use milestones to group related work in both the planning and engineering repos.

**5. Track Progress via GitHub Projects**

* Optionally connect GitHub Projects to all relevant repos for unified tracking.
* Use filters to view progress per team, PM, milestone, or deliverable.

## ✅ Pros:

* Clear separation between planning (PM-focused) and execution (dev-focused).
* PMs don’t have to dig through technical issues to manage timelines.
* Engineering teams stay focused on their respective repos with relevant context.
* Cross-functional coordination is easier to visualize.

## ⚠ Cons:

* Requires discipline to keep planning issues synced with dev issues.
* Slightly more overhead managing links between repos.
* PMs may need light GitHub training to maintain planning boards effectively.

## ✅ Best For:

* Mid-sized or growing teams.
* Organizations needing both high-level visibility and engineering repo autonomy.
* PMs who want control over planning without disrupting dev workflows.

---

# Project Management via GitHub — Hybrid Model for PMs (Continued)

## 📁 Folder Structure for Central Planning Repo

To organize planning content clearly across PMs, designers, and devs:

```

project-planning/
│ ├── README.md ← Repo overview and instructions
│ ├── .github/ ← Issue templates, workflows, PR templates
│ ├── design/ ← Design assets and links
│ │ ├── onboarding-flow/
│ │ │ ├── README.md ← Design links and notes
│ │ │ └── wireframe-v1.png ← (optional export)
│ │ ├── dashboard-redesign/
│ │ │ └── figma-link.txt ← Direct Figma URL
│ │ └── shared-assets/
│ │ ├── icons/
│ │ └── typography-guide.pdf
│ ├── specs/ ← Feature specs or planning documents
│ │ ├── onboarding.md
│ │ ├── dashboard.md
│ │ └── billing-update.md
│ ├── docs/ ← Process guides, roadmap
│ │ ├── roadmap.md
│ │ └── process-guides/
│ │ ├── issue-triage.md
│ │ └── design-handoff.md

````

## 🏷 Suggested GitHub Labels for Planning Repo

Use consistent labels across planning and dev repos to help filter and manage tasks:

| Label           | Purpose                                    |
| :-------------- | :----------------------------------------- |
| `design`        | Design tasks or reviews                    |
| `spec-needed`   | Issue needs a feature or tech spec         |
| `ready-for-dev` | Design/spec approved, ready for build      |
| `backend`       | Dev task related to backend                |
| `frontend`      | Dev task related to frontend               |
| `blocked`       | Issue is blocked by another dependency     |
| `q3`            | Time-based label (e.g., quarter)           |
| `epic`          | Tracks large initiatives or features       |

## 🔗 Saving and Managing Design Files

Design files should generally not be stored as heavy source files in GitHub, but here’s the best way to handle them:

**✅ Use Markdown (.md) Files for Links and Context**

Example: `design/onboarding-flow/README.md`

```markdown
# Onboarding Flow – Design Assets

## Figma Links
- [Wireframes v1](https://www.figma.com/file/abc123)
- [Final UI Mockups](https://www.figma.com/file/xyz789)

## Notes
- Owner: @designer
- Status: Final (as of July 25, 2025)
- Last reviewed: July 27 by PM team
````

**🟡 Use Plain Text (.txt) for Quick Links**

Example: `figma-link.txt`

```
[https://www.figma.com/file/xyz789/dashboard-v3](https://www.figma.com/file/xyz789/dashboard-v3)
```

**🟢 Also: Embed Design Links in Issues/PRs**

Include design assets in the body of GitHub issues for clarity:

```
📎 Figma: [https://www.figma.com/file/xyz123](https://www.figma.com/file/xyz123)
🧠 Notion spec: [https://notion.so/projectX-flow](https://notion.so/projectX-flow)
```

## 🧭 Summary of File Strategy

| Type              | Where to store      | When to use                                |
| :---------------- | :------------------ | :----------------------------------------- |
| Markdown (`.md`)  | `design/` or `specs/` | Long-term links + context                  |
| Text (`.txt`)     | Inside `design/` folders | One-off links or quick references          |
| Images (`.png`)   | `design/`           | Wireframes, exported visuals               |
| Links in Issues   | GitHub Issues or PRs | Collaboration and tracking                 |
