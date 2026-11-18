# Fieldline

**Jobsite administration for general contractors and their subcontractors, in one workspace.**

Fieldline is a front-end prototype that replaces the daily pile of emails, texts, and paper forms on a commercial jobsite: pre-work reports, permits, look-aheads, job restraints, and near-miss reporting. A GC project team and the trade partners each get a view built around what they need to do today.

**Live demo:** https://mhart664.github.io/fieldline/

The demo project is *Northpoint Medical Center, Building 2 (Phase 04)*. All companies, people, and data are fictional.

---

## What it does

Fieldline has two roles, switchable with the **GC team / Subcontractor** toggle in the top bar.

| Area | GC project team | Subcontractor |
|---|---|---|
| **Overview / Today** | Action list across the whole job: permits awaiting review, trades with incomplete pre-work, restraints past need-by, unreviewed near misses, overlapping hot work | A company-only daily checklist: pre-task hazard analysis, daily work plan, permit requests, tomorrow's look-ahead, and the previous day's close-out |
| **Pre-work reports** | See which trades have submitted their hazard analysis and work plan, and who has not | Submit a hazard analysis (hazards, controls, PPE) and a work plan (areas, crew, tasks, permits needed, equipment) |
| **Permits** | Approve or deny with conditions; overlap detection flags conflicting work in the same area | Request permits and see decisions and conditions as they come back |
| **Look-ahead** | Tomorrow's planned work by trade and area, with conflicts flagged before crews arrive; printable | Submit tomorrow's plan from the Today page |
| **Restraints** | Track obstacles by need-by date, owner ("who has the ball"), status, and days open | My restraints: raise them and comment on them |
| **Near misses** | Private review queue with corrective actions, owners, and due dates | My near misses: submit privately to the GC and follow the thread |
| **Meetings** | Coordination and safety meeting views, with a full-screen **present mode** and print layouts | n/a |
| **Submissions** | Full report history with a printable record | n/a |
| **Notifications** | Bell for permits to review, items needing attention | Bell for permit decisions, restraint comments, and a missing close-out or look-ahead |

### Permit types

The permit catalog covers common commercial and healthcare construction scenarios, grouped by hazard:

- **Fire / heat:** hot work, fire protection impairment, torch-applied roofing
- **Energy:** lockout / tagout, utility shutdown / tie-in, temporary power
- **Ground / structure:** excavation, coring and saw cutting, shoring, selective demolition
- **Access / fall:** floor and roof openings, leading-edge work, scaffolds, roof access
- **Lifting:** critical lift / crane setup
- **Environmental / health:** confined space, ICRA, ILSM, silica, asbestos / lead, dewatering
- **Site:** after-hours work, road and lane closures, X-ray / NDT exclusion zones

Each type asks for the fields that matter for that hazard (for example, hot work asks for the fire watch name and post-work watch duration).

---

## Run it locally

No build step, no dependencies, no install.

1. Download or clone this repo.
2. Open `index.html` in any modern browser.

```bash
git clone https://github.com/mhart664/fieldline.git
cd fieldline
# then open index.html
```

## Tech

- Single-file app: plain HTML, CSS, and vanilla JavaScript in `index.html`
- Fonts: DM Sans and Manrope via Google Fonts
- State: saved in the browser's `localStorage` (key `fieldline-northpoint-v5`)
- Hosted on GitHub Pages

## Demo data and reset

The app loads with seeded demo data (trades such as electrical, concrete, HVAC, plumbing, framing, and roofing). Anything you enter is stored only in your own browser. Use **Reset demo data** at the bottom of the sidebar to return to the starting state.

---

## Current limitations

This is a prototype, and it is worth being clear about what it does not do yet:

- **No shared backend.** Data lives in each user's browser, so a GC and a sub cannot see each other's entries. The role switch simulates both sides from one device.
- **No accounts or authentication.**
- **No file or photo attachments.**
- **No push or email notifications.** The notification bell is in-app only.

Closing the first gap, a real shared data layer with accounts, is what turns this from a demo of the workflow into a usable tool.

## Project structure

```
fieldline/
├── index.html   # the entire app
└── README.md
```

## Author

Built by Mason, Building Science, Auburn University.
