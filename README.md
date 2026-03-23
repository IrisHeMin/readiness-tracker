# 📊 Readiness Plan Tracker

**A visual, self-service team readiness management dashboard — track technical skill development across your team with zero infrastructure cost.**

> 🔗 **Live Demo**: [https://irishemin.github.io/readiness-tracker/](https://irishemin.github.io/readiness-tracker/)

---

## 💡 Why This Exists

Technical teams need a lightweight way to:
- Help each member **plan their own skill development** journey
- Let managers **track team-wide readiness** at a glance
- Turn learning plans into **actionable, trackable milestones** with visual progress

Most existing tools are either too heavy (Jira, ADO boards) or too generic (spreadsheets). Readiness Plan Tracker is purpose-built for **technical skill growth tracking** — it's simple enough for anyone to use, yet rich enough to provide meaningful insights.

---

## ✨ Core Features

### 🏠 Team Dashboard — Manager's View
| Feature | Description |
|---------|-------------|
| 📊 **Stats Overview** | Team size, average progress, completed plans, at-risk count |
| 🗺️ **Readiness Heatmap** | Members × Plans matrix — color-coded completion at a glance |
| 📈 **Progress Leaderboard** | All members ranked by completion %, with live sync indicators |
| 👤 **Member Detail Cards** | Per-person breakdown showing each plan's phase-level progress |
| 🔄 **Auto Refresh** | Dashboard refreshes every 30s to reflect latest updates |

### 🚀 Personal Workspace — Member's View
| Feature | Description |
|---------|-------------|
| 📋 **Plan Creator** | Choose from built-in templates or create fully custom plans from scratch |
| 🧩 **Flexible Structure** | Add/edit/delete Phases and Milestones freely — your plan, your way |
| ✅ **Sub-task Breakdown** | Break each Milestone into smaller action items (private to you) |
| 🔄 **Smart Progress** | Check off sub-tasks → Milestone auto-completes → Charts auto-update |
| 📊 **Personal Charts** | Donut chart, phase progress bars, and status summary |
| 📑 **Multi-Plan Support** | Run multiple readiness plans in parallel with tab switching |
| ✏️ **Edit Anytime** | Modify plan structure, add new milestones, adjust goals on the fly |
| 📤 **Export** | Export milestone-level progress as JSON (sub-tasks excluded for privacy) |

### ⚙️ Team Management
| Feature | Description |
|---------|-------------|
| ➕ **Add/Remove Members** | Manage team roster directly from the dashboard UI |
| ✏️ **Edit Profiles** | Update member names and roles inline |
| 🏷️ **Team Naming** | Customize your team name |
| 🔄 **Shared Config** | Team roster syncs across all pages automatically |

### 🔒 Privacy Model
| Data | Visibility |
|------|-----------|
| Sub-task breakdown (todo items) | 🔒 **Private** — only the individual can see |
| Milestone completion status | 🌐 **Team-wide** — visible on dashboard |
| Phase progress percentage | 🌐 **Team-wide** — visible on dashboard |
| Overall completion rate | 🌐 **Team-wide** — visible on dashboard |

---

## 🎨 Built-in Templates

| Template | Coverage |
|----------|----------|
| 🌐 **Azure Networking** | VNet, NSG, VPN Gateway, DNS, Load Balancer, Firewall — 3 phases, 11 milestones |
| 💾 **Azure Storage** | Blob, File, Queue, Table, NetApp Files, performance tuning — 3 phases, 9 milestones |
| 🖥️ **Azure Compute / VM** | VM management, RDP/SSH connectivity, performance diagnostics — 3 phases, 9 milestones |
| ✨ **Blank** | Start from scratch with a fully custom plan |

> Templates are starting points — every phase and milestone can be customized after creation.

---

## 🛠️ Tech Stack

| Layer | Technology | Why |
|-------|-----------|-----|
| **Frontend** | HTML / CSS / JavaScript | Zero build step, zero dependencies to install |
| **Styling** | Tailwind CSS (CDN) | Rapid UI development, responsive by default |
| **Charts** | Chart.js | Lightweight, beautiful charts with minimal config |
| **Data** | localStorage | Client-side persistence, no backend needed |
| **Hosting** | GitHub Pages | Free, automatic deployment via GitHub Actions |
| **CI/CD** | GitHub Actions | Auto-deploy on every push |

### Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    GitHub Pages                          │
│                                                         │
│  ┌─────────────────┐         ┌────────────────────┐    │
│  │   index.html     │ ◄────► │   my-plan.html      │    │
│  │ Team Dashboard   │  sync  │ Personal Workspace   │    │
│  │                  │  via   │                      │    │
│  │ • Heatmap        │ local  │ • Plan Creator       │    │
│  │ • Progress bars  │Storage │ • Sub-task Checklist  │    │
│  │ • Member cards   │        │ • Charts & Stats     │    │
│  │ • Team settings  │        │ • Multi-plan Tabs    │    │
│  └─────────────────┘         └────────────────────┘    │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## 🚀 Getting Started

### Quick Start (Local)
```bash
git clone https://github.com/IrisHeMin/readiness-tracker.git
cd readiness-tracker
# Just open in browser - no build needed!
open index.html        # macOS
start index.html       # Windows
```

### Deploy to GitHub Pages
1. Fork or push this repo to your GitHub account
2. Go to **Settings → Pages → Source**: select `GitHub Actions`
3. The included workflow (`.github/workflows/deploy.yml`) will auto-deploy
4. Access at `https://<your-username>.github.io/readiness-tracker/`

### For Enterprise / Private Use
1. Create a **Private** repo in your GitHub Organization
2. Push the code
3. Enable GitHub Pages (requires GitHub Enterprise or GitHub Pro)
4. Only org members with repo access can view the site

---

## 📁 Project Structure

```
readiness-tracker/
├── index.html                  # Team Dashboard (manager view)
├── my-plan.html                # Personal Workspace (member view)
├── data/                       # Sample data files
│   ├── team.json               # Team roster (reference)
│   ├── templates/              # Plan template definitions
│   │   └── azure-networking.json
│   └── plans/                  # Individual plan samples
│       ├── alice.json
│       ├── bob.json
│       └── ...
└── .github/
    └── workflows/
        └── deploy.yml          # GitHub Pages auto-deployment
```

---

## 🗺️ Roadmap

### Current (v2.1) — Client-Side MVP
- [x] Team dashboard with dynamic data sync
- [x] Personal workspace with plan creator
- [x] Sub-task breakdown with privacy
- [x] Built-in templates (Networking, Storage, Compute)
- [x] Team member management
- [x] Export progress as JSON
- [x] GitHub Pages deployment

### Next (v3.0) — Multi-User Production
- [ ] **GitHub API integration** — auto-commit progress JSON, no Git knowledge needed
- [ ] **Authentication** — GitHub OAuth login, role-based access
- [ ] **Cross-device sync** — real-time data via GitHub API or lightweight backend
- [ ] **Notification** — email/Teams alerts for milestone deadlines
- [ ] **Manager tools** — assign templates, set deadlines, bulk operations
- [ ] **Analytics** — team trend over time, velocity metrics, risk prediction

### Future Ideas
- [ ] Copilot CLI Skill integration — generate readiness plans from natural language
- [ ] Microsoft Teams tab integration
- [ ] PDF/PowerPoint report export for leadership reviews
- [ ] Gamification — badges, streaks, team leaderboards

---

## 🎯 Use Cases

| Scenario | How It Helps |
|----------|-------------|
| **New hire onboarding** | Manager assigns a readiness template, new hire tracks their own progress |
| **Certification prep** | Team members create study plans, break exams into sub-topics, track completion |
| **Technology ramp-up** | When the team takes on a new product area, everyone creates a learning plan |
| **Quarterly reviews** | Export progress data for 1:1 discussions and performance conversations |
| **Team planning** | Manager sees heatmap to identify skill gaps and allocate training resources |

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

<p align="center">
  Built with ❤️ for technical support teams who believe in continuous learning.<br/>
  <strong>Readiness Plan Tracker</strong> — Plan it. Track it. Own it.
</p>
