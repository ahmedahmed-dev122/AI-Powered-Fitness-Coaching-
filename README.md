<h1 align="center">FORMORA</h1>
<p align="center"><b>Secure AI-Powered Fitness Coaching App</b><br>
Real-Time Exercise Analysis &amp; Personalized Plans</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow" />
  <img src="https://img.shields.io/badge/Graduation%20Project-Fall%202026-blue" />
  <img src="https://img.shields.io/badge/Platform-Mobile-green" />
  <img src="https://img.shields.io/badge/Project%20ID-32CSAI-lightgrey" />
</p>

---

## 📌 Overview
**FORMORA** is a mobile fitness coaching app that works like a personal trainer in your pocket.
It uses the phone camera and on-device AI to recognize your exercise, count your reps and flag
visible form errors in real time. It also builds personalized workout plans, tracks your progress
and personal records, supports Egyptian meals with budget-aware nutrition suggestions, and offers
privacy-controlled challenges and workout-partner matching, while keeping your personal and health data secure.

> ⚠️ FORMORA is a wellness tool, **not** a medical device. It does not diagnose, prevent injuries or guarantee weight loss.

## ❗ Problem
- Personal trainers are expensive and not always available, so many people train without anyone checking their form.
- Wrong exercise form leads to poor technique habits and weak results.
- Users need separate apps for workout plans, nutrition, progress tracking and social motivation.
- Most food apps do not cover everyday Egyptian meals (koshary, ful medames, falafel) or local budgets.
- Fitness apps handle sensitive data (camera video, location, gym schedules, progress) without strong privacy guarantees.

## 🎯 Objectives
| # | Objective | Target |
|---|---|---|
| O1 | Real-time exercise recognition and rep counting for 3–5 exercises | Rep-count error (MAE) ≤ 1 per set |
| O2 | Confidence-gated feedback on visible form errors | Precision ≥ 95%, coverage ≥ 80% |
| O3 | Constraint-checked workout planner with progress and PR tracking | 0 invalid plans in tests |
| O4 | Nutrition assistant with Egyptian foods and budget-aware ranking | 0 allergy / restriction violations |
| O5 | Secure platform (MFA, RBAC, encryption, account deletion) | All authorization and deletion tests pass |
| O6 | Full system evaluation | 30-min camera stability test, usability study, backup-restore drill |

## ✨ Key Features
| Feature | Description |
|---|---|
| 🎥 Real-Time Form Analysis | Pose estimation detects 33 body landmarks and checks visible form errors live |
| 🔢 Rep Counting | Automatic counting of complete and partial repetitions |
| 🗣️ Instant Feedback | One short, coach-reviewed cue after a rep; says "cannot assess" instead of guessing when unsure |
| 📋 Personalized Plans | Plans based on goals, level, equipment and schedule (Push/Pull/Legs, Upper/Lower) |
| 📈 Progress Tracking | Sets, reps, weights, weekly progress and personal records (PRs) |
| 🥗 Nutrition Assistant | Calories and macros, Egyptian meals, allergy filters and affordable food suggestions |
| 🤝 Community | Opt-in challenges, leaderboards and workout-partner matching by gym/area and time |
| 🔒 Secure by Design | MFA, role-based access, encryption, on-device video processing |

> No LLM is used: every message the user sees is a fixed, pre-reviewed message.

## 🧠 AI Pipeline
```
Camera ──▶ MediaPipe Pose ──▶ Feature Extraction ──▶ Causal TCN ──▶ State Machine ──▶ Form-Error ──▶ Confidence Gate
(on device)  (33 landmarks)    (angles, velocities)   (exercise +     (rep counting)    Classifier      ├─ ✅ Show cue
                                                        phase)                                          └─ ❓ Cannot assess
```

## 🏗️ System Architecture
```
┌─────────────────────┐     ┌─────────────────────┐     ┌──────────────────┐
│  Mobile App         │ ──▶ │  On-Device AI       │ ──▶ │  Feedback Engine │
│  (Flutter, Camera)  │     │  (Pose + Models)    │     │  (Form + Reps)   │
└──────────┬──────────┘     └─────────────────────┘     └──────────────────┘
           │ HTTPS / TLS (encrypted)
           ▼
┌─────────────────────┐     ┌─────────────────────┐
│  Backend API        │ ──▶ │  Planner, Nutrition │
│  FastAPI + MFA/RBAC │     │  & Matching Logic   │
└──────────┬──────────┘     └─────────────────────┘
           ▼
┌─────────────────────┐
│  PostgreSQL         │
│  (row-level security│
│   + encryption)     │
└─────────────────────┘
```

## 🛠️ Tech Stack
| Layer | Technology |
|---|---|
| Mobile App | Flutter |
| Pose Estimation | MediaPipe Pose Landmarker |
| AI / ML | Python, Temporal Convolutional Networks (TCN), LiteRT |
| Backend | FastAPI (versioned REST API) |
| Database | PostgreSQL (row-level security) |
| Security | MFA, role-based access control, HTTPS/TLS, encryption at rest, managed secrets |

## 🔒 Security &amp; Privacy
- Camera video is processed **on the device**; raw video never leaves the phone by default.
- Multi-factor authentication and role-based access control (user / admin).
- PostgreSQL row-level security so each user can only access their own data.
- Sensitive data encrypted at rest and in transit.
- Location sharing is opt-in and approximate (user-selected gym/area only).
- Messaging only after both users agree to match; block and report controls.
- Users control their own data (edit / delete account and history).
- Designed against the OWASP Mobile (MASVS) and API Security Top 10 standards.

## 🗓️ Project Timeline
| Phase | Milestone | Status |
|---|---|---|
| Senior Project 1 | Proposal | ✅ Done |
| Senior Project 1 | Market Visibility Study | ✅ Done |
| Senior Project 1 | Mid-Semester Presentation (Milestone 4) | 🔄 In progress |
| Senior Project 1 | Requirements (SRS) | ⏳ Planned |
| Senior Project 1 | System Design &amp; Proof of Concept | ⏳ Planned |
| Senior Project 1 | First-Term Prototype | ⏳ Planned |
| Senior Project 2 | Full Implementation (nutrition, community, security) | ⏳ Planned |
| Senior Project 2 | Testing &amp; Final Delivery | ⏳ Planned |

## 📂 Repository Structure
```
├── docs/
│   ├── 32DSAI_Proposal.pdf
│   └── Market_Visibility_32CSAI.pdf
├── app/          # Flutter mobile application (coming soon)
├── ai/           # Pose estimation, exercise & form models (coming soon)
├── backend/      # FastAPI service & database (coming soon)
└── README.md
```

## 📄 Documents
- [Project Proposal](docs/32DSAI_Proposal.pdf)
- [Market Visibility Study](docs/Market_Visibility_32CSAI.pdf)

## 👥 Team
| Name | Program |
|---|---|
| Farida Ehab Ashour | Data Science &amp; AI (DSAI) |
| Ahmed Ragheb | Data Science &amp; AI (DSAI) |
| Mostafa Magdy | Data Science &amp; AI (DSAI) |
| Mohamed Saleh | Information Technology (IT) |

**Supervisor:** Dr. Yousry Abdelazeem<br>
**Co-Supervisor:** Eng. Sama Mohamed

School of Computational Sciences and Artificial Intelligence, Zewail City of Science, Technology and Innovation

## 📬 Contact
📧 aiformora1@gmail.com

---
<p align="center"><i>Graduation Project — Fall 2026</i></p>
