# CineWave Movie Ticket Booking App (Pega Platform)

![Pega Enterprise Architecture](https://img.shields.io/badge/Platform-Pega%20Platform%20v8.x-blue.svg)
![License-MIT](https://img.shields.io/badge/License-MIT-green.svg)
![Status-Production%20Ready](https://img.shields.io/badge/Status-10%2F10%20Production%20Ready-brightgreen.svg)

## 📌 Executive Summary
**CineWave Movie Ticket Booking Engine** is an enterprise-grade Pega Platform case management application designed to streamline customer ticket reservations, inventory seat availability verification, dynamic price calculation, automated ticket dispatch, SLA turnaround governance, and exception handling (cancellations & notifications).

---

## 📂 Repository Structure

```plaintext
pega-movie-ticket-booking/
│
├── .gitattributes               <-- Git LFS configuration for binary media & archives
├── .gitignore                   <-- Version control exclusion rules
├── LICENSE                      <-- MIT Open-Source License
├── README.md                    <-- Project portfolio & system architecture documentation
│
├── demo/                        <-- Video and GIF visual walkthroughs
│   ├── cinewave_pega_demo.mp4
│   └── demo_walkthrough.gif
│
├── screenshots/                 <-- Step-by-step Pega App Studio UI & Case Artifacts
│   ├── 01_case_lifecycle.png
│   ├── 02_case_data_model.png
│   ├── 03_movie_show_data_records.png
│   ├── 04_stage_sla_configuration.png
│   ├── 05_runtime_enter_details.png
│   ├── 06_runtime_present_summary.png
│   ├── 07_runtime_resolved_completed.png
│   ├── 08_runtime_resolved_cancelled.png
│   ├── 09_explore_data_status_insight.png
│   └── 10_work_queue_routing.png
│
├── exports/                     <-- Enterprise Application Export Archive
│   └── CineWave_Booking_App_v1.zip
│
└── docs/                        <-- Business requirements & user stories
    └── user_stories.md
```

---

## 📑 Requirements & Business User Stories
Detailed acceptance criteria, SLA urgency escalation specs, and business requirements are documented in [`docs/user_stories.md`](docs/user_stories.md).

### Summary of Core User Stories:
- **US-001 (Customer Booking Submission):** Capture movie selection, show time, ticket class, and quantity.
- **US-002 (Dynamic Cost Calculation & Inventory Check):** Calculate total cost (`Count * Unit Price`) and validate remaining seat count.
- **US-003 (Customer Review & Decision):** Present read-only summary for final Confirmation or Cancellation.
- **US-004 (Automated Seat Allocation & Execution):** Generate unique Ticket ID (`TKT-####`), decrement inventory, and resolve as `Resolved-Completed`.
- **US-005 (Cancellation & Notification Handling):** Alternate stage flow sending email alerts and resolving as `Resolved-Cancelled`.
- **US-006 (SLA Governance):** Enforce 1-day Goal (+10 urgency) and 2-day Deadline (+20 urgency) on pending processing tasks.

---

## 🛠️ System Architecture & Pega Artifacts

| Component | Pega Implementation |
| :--- | :--- |
| **Case Type** | `Booking` (Class: `CineWave-Work-Booking`) |
| **Data Types** | `Movie`, `Show`, `Customer`, `Ticket` |
| **Data Views & Lookup** | Data Page `D_MovieList`, `D_ShowDetails` |
| **SLA Service Level** | `BookingSLA` (Goal: 24h / Deadline: 48h) |
| **Work Routing** | Work Queue `BookingProcessingWB` |

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
