# Sihhah — صحة
### AI-Powered Smart Hospital Discharge Workflow

**MedHack UAE Engineering Challenge**

---

## The Problem

Hospital discharge instructions are traditionally handed to patients as static paper printouts — dense, unstructured, and difficult to follow. With nearly **15% of patients readmitted within 30 days**, and studies showing that **68% of patients** struggle to understand their discharge notes, the gap between clinical communication and patient comprehension is a critical healthcare failure.

Low health literacy, complex multi-drug schedules, and the absence of a post-discharge safety net mean patients leave the hospital with a piece of paper they can't act on — and no way to signal for help when things go wrong.

---

## The Solution

**Sihhah** (صحة — Arabic for "Health") is a dual-portal web application that transforms raw, unstructured clinical notes into an interactive, mobile-friendly care plan in seconds — with a built-in real-time red-flag safety net connecting patients back to their clinical team.

### How It Works

1. **Clinical staff** paste raw discharge notes into Sihhah
2. **The AI parsing engine** automatically structures notes into medications (grouped by time of day), follow-up appointments, diet guidelines, activity restrictions, lab tests, and warning signs with severity classification
3. **A unique shareable link** is generated — no app download required
4. **Patients** open the link on any device to see an interactive checklist with progress tracking
5. **If a patient reports a red-flag symptom**, an alert instantly appears on the staff dashboard for acknowledgment

---

## Key Features

### For Clinical Staff
- **AI Note Parser** — Paste unstructured notes, get a structured care plan in ~3 seconds
- **Live Dashboard** — Monitor all active patients, plan completion rates, and unacknowledged alerts
- **Red Flag Alert System** — Real-time notifications when patients report warning symptoms, with one-click acknowledge workflow
- **One-Click Link Sharing** — Generate a unique URL for each patient's care plan

### For Patients
- **Zero Friction** — No app download, no account creation. Just open a link
- **Time-Grouped Medications** — Meds organized by Morning, Evening, As Needed, etc.
- **Interactive Checklist** — Tap to mark items complete with live progress tracking
- **Warning Signs Section** — Clearly flagged symptoms with one-tap "Report This" to notify care team
- **Collapsible Sections** — Focus on what matters, hide what's done

---

## Architecture & Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML5, Tailwind CSS, Vanilla JavaScript |
| Data Persistence | localStorage (Supabase/PostgreSQL ready) |
| AI Processing | Mock NLP parser (API-ready for OpenAI/Gemini) |
| Routing | Hash-based SPA router |
| Deployment | Single HTML file — zero build step |

---

## Demo Credentials

| Role | Name | Password |
|------|------|----------|
| Clinical Staff | Dr. Ahmed Ali | `doctor123` |
| Patient | Ayesha | `patient123` |

The app comes pre-loaded with **3 seed patients** covering COPD, post-operative knee replacement, and heart failure — each with realistic medications, follow-ups, and warning signs.

---

## Getting Started

No installation required. Simply open `index.html` in any modern browser.

To reset demo data, open your browser console and run:
```
localStorage.removeItem('sihhah_db')
```
Then refresh the page.

---

## Project Structure

Everything lives in a single `index.html` file — intentionally designed for rapid hackathon deployment:

- **Data Layer** — localStorage-backed patient records with seed data
- **Mock AI Parser** — Regex-based state machine that detects clinical sections (Medications, Follow-ups, Diet, Activity, Labs, Warning Signs) and extracts structured data
- **Hash Router** — SPA navigation between Landing, Login, Staff Portal, and Patient Portal
- **Event Delegation** — Single click handler on `#app` and `#modal-root` for all UI interactions
- **Toast & Modal System** — Custom non-blocking notifications and dialogs

---

## Red Flag Safety Net — Flow

```
Patient taps "Report This" on a warning symptom
        ↓
Alert saved with timestamp in patient record
        ↓
Staff dashboard badge updates with pulse animation
        ↓
Staff opens patient detail → sees alert → taps "Acknowledge"
        ↓
Patient view updates to show "Team Responded" in green
```

---

## What's Next (Production Roadmap)

- [ ] Integrate real LLM (OpenAI/Gemini) for robust note parsing
- [ ] Supabase backend for multi-user data persistence
- [ ] SMS/WhatsApp notifications for red flag alerts
- [ ] Arabic language toggle (صحة branding ready)
- [ ] Medication reminder push notifications
- [ ] Patient weight/vitals logging with trend alerts
- [ ] PDF export of care plan for offline use
- [ ] Role-based access control with hospital SSO

---

## Team

Built for **MedHack UAE Engineering Challenge**

---

*Transforming discharge from a handoff into a handshake.*
