<h1 align="center">FORMORA</h1>
<p align="center"><b>Secure AI-Powered Fitness Coaching App</b><br>
Real-Time Exercise Analysis &amp; Personalized Plans</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow" />
  <img src="https://img.shields.io/badge/Graduation%20Project-Fall%202026-blue" />
  <img src="https://img.shields.io/badge/Platform-Mobile-green" />
</p>

---

## 📌 Overview
**FORMORA** is a mobile fitness coaching app that works like a personal trainer in your pocket.
It uses the phone camera and AI to watch your exercises in real time, correct your form,
count your reps, and build a workout plan that adapts to your goals and progress,
while keeping your personal and health data secure.

## ❗ Problem
- Personal trainers are expensive and not always available.
- Wrong exercise form leads to injuries and poor results.
- Most fitness apps give generic plans and no feedback on how you actually move.
- Fitness apps collect sensitive data (body measurements, health info, camera video) without strong privacy guarantees.

## 🎯 Objectives
- Detect and analyze exercise form in real time using computer vision.
- Give instant corrective feedback (visual + audio).
- Generate personalized workout plans based on the user's goals, level, and history.
- Track progress over time.
- Protect user data with security built in from the start.

## ✨ Key Features
| Feature | Description |
|---|---|
| 🎥 Real-Time Form Analysis | Pose estimation detects body joints and checks exercise form live |
| 🔢 Rep Counting | Automatic repetition and set counting |
| 🗣️ Instant Feedback | Visual and voice cues to fix mistakes during the workout |
| 📋 Personalized Plans | AI-generated plans that adapt to goals, fitness level and progress |
| 📈 Progress Tracking | Workout history, statistics and performance trends |
| 🔒 Secure by Design | Encrypted data, secure authentication, on-device video processing |

## 🏗️ System Architecture
```
┌──────────────┐     ┌─────────────────────┐     ┌──────────────────┐
│  Mobile App  │ ──▶ │  On-Device AI       │ ──▶ │  Feedback Engine │
│  (Camera/UI) │     │  (Pose Estimation)  │     │  (Form + Reps)   │
└──────┬───────┘     └─────────────────────┘     └──────────────────┘
       │ HTTPS (encrypted)
       ▼
┌──────────────┐     ┌─────────────────────┐
│  Backend API │ ──▶ │  Plan Recommendation│
│  + Auth      │     │  Model              │
└──────┬───────┘     └─────────────────────┘
       ▼
┌──────────────┐
│  Secure DB   │
└──────────────┘
```

## 🛠️ Tech Stack
<!-- EDIT: change to the technologies you actually chose -->
| Layer | Technology |
|---|---|
| Mobile App | Flutter |
| Pose Estimation | MediaPipe Pose / MoveNet |
| AI / ML | Python, TensorFlow Lite |
| Backend | FastAPI |
| Database | Firebase / PostgreSQL |
| Security | JWT auth, AES encryption, HTTPS/TLS |

## 🔒 Security &amp; Privacy
- Camera video is processed **on the device**; raw video never leaves the phone.
- Secure authentication and authorization.
- Sensitive data encrypted at rest and in transit.
- Users control their own data (view / export / delete).

## 🗓️ Project Timeline
| Phase | Milestone | Status |
|---|---|---|
| Senior Project 1 | Proposal | ✅ Done |
| Senior Project 1 | Market Visibility Study | ✅ Done |
| Senior Project 1 | Mid-Semester Presentation (Milestone 4) | 🔄 In progress |
| Senior Project 1 | System Design &amp; Prototype | ⏳ Planned |
| Senior Project 2 | Full Implementation | ⏳ Planned |
| Senior Project 2 | Testing &amp; Final Delivery | ⏳ Planned |

## 📂 Repository Structure
```
├── docs/
│   ├── 32DSAI_Proposal.pdf
│   └── Market_Visibility_32CSAI.pdf
├── app/          # Mobile application (coming soon)
├── ai/           # Pose estimation & recommendation models (coming soon)
├── backend/      # API & database (coming soon)
└── README.md
```

## 📄 Documents
- [Project Proposal](docs/32DSAI_Proposal.pdf)
- [Market Visibility Study](docs/Market_Visibility_32CSAI.pdf)

## 👥 Team
<!-- EDIT: put your team names -->
| Name | Role |
|---|---|
| Name 1 | Team Leader / AI |
| Name 2 | Mobile Development |
| Name 3 | Backend &amp; Security |
| Name 4 | UI/UX &amp; Testing |

**Supervisor:** Dr. ____ <!-- EDIT -->

## 📬 Contact
📧 aiformora1@gmail.com

---
<p align="center"><i>Graduation Project — Fall 2026</i></p>
