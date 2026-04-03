# Digital Phil-IRI: School-Based Reading Assessment System

A fully offline-capable Progressive Web App (PWA) for administering Philippine Informal Reading Inventory (Phil-IRI) assessments in secondary schools.

---

## 🚀 Quick Start

### Option 1: Open Directly (Single Device)
1. Open `index.html` in any modern browser (Chrome, Edge, Firefox)
2. Login as teacher: username `admin` / password `admin123`
3. All data saves automatically to browser storage (offline)

### Option 2: LAN / Network Deployment
To run on a local school network so multiple devices can connect:

```bash
# Install Node.js (https://nodejs.org) then run:
npx serve .

# Or with Python:
python -m http.server 8080
```
Then connect other devices via: `http://[YOUR-IP]:8080`

### Option 3: USB Drive
Copy the entire `philiri-pwa` folder to a USB drive. Open `index.html` on any computer — no installation required.

---

## 👥 User Accounts

| Role | Username | Password | Access |
|------|----------|----------|--------|
| Admin | `admin` | `admin123` | Full access |
| Teacher | `teacher1` | `teacher123` | Full access |
| Student | _(any name)_ | Session code | Assessment only |

Create additional teacher accounts in **Settings → Manage Teacher Accounts**.

---

## 📋 Phil-IRI Phases Supported

1. **Word Recognition** — Graded word lists; click each word to mark correct/wrong/skipped
2. **Oral Reading** — Passage display with audio recording + teacher error logging (mispronunciation, omission, substitution, insertion)
3. **Comprehension** — Multiple-choice questions with automatic scoring
4. **Fluency** — 1-minute timed reading with WPM calculation

---

## 🔑 Reading Level Calculation

| Level | Word Recognition | Comprehension |
|-------|-----------------|---------------|
| Independent | ≥ 97% | ≥ 75% |
| Instructional | 91–96% | 50–74% |
| Frustration | < 91% | < 50% |

*Thresholds are configurable in Settings.*

---

## 📁 Data Management

All data is stored in **browser localStorage** (IndexedDB-compatible):
- Students, passages, word lists, sessions, and results persist across sessions
- Export to **CSV, JSON, or TXT** from the Export button (top right)
- Data survives browser restarts on the same device

### Backup Data
Go to **Export → JSON** to download a full backup of all assessment data.

---

## ✏️ Customizing Materials

### Passages
- Go to **Passages & Materials → Add Passage**
- Supports pre-test and post-test designation
- Lock individual passages to prevent unauthorized editing

### Word Lists
- Go to **Word Lists → Add Word List**
- Enter words one per line or comma-separated
- Assign to grade levels

### Comprehension Questions
- Go to **Passages & Materials → Comprehension Questions tab**
- Edit existing questions inline

---

## 🔒 Lock Feature

In **Settings → Access Control**:
- Lock Answer Keys — hides correct answers from students
- Lock Scoring Formulas — prevents editing of passing thresholds
- Enable/disable immediate feedback after assessment

Individual passages can also be locked via the passage editor.

---

## 📊 Features

- ✅ Pre-test & Post-test management
- ✅ Role-based access (Admin / Teacher / Student)
- ✅ Automatic reading level determination
- ✅ Audio recording for oral reading phase
- ✅ Error type logging (mispronunciation, omission, substitution, insertion)
- ✅ Analytics dashboard with class performance overview
- ✅ Pre/Post comparison charts
- ✅ Data export (CSV, JSON, TXT)
- ✅ Fully offline (PWA with service worker)
- ✅ Responsive design (works on tablets and phones)
- ✅ Editable passages, word lists, and scoring parameters

---

## 🖨️ Printing Reports

Use **Export → Text Report** to generate a printable report, or use your browser's Print function (Ctrl+P) on the Results or Analytics page.

---

## ⚙️ Technical Stack

- **Frontend**: Pure HTML5 + CSS3 + Vanilla JavaScript
- **Storage**: localStorage (no database required)
- **Offline**: Service Worker + PWA manifest
- **Audio**: Web Audio API (MediaRecorder)
- **Export**: Blob API for CSV/JSON/TXT download
- **Fonts**: Google Fonts (cached after first load)

No server, no installation, no internet required after first load.

---

## 📱 Installing as App (Optional)

On Chrome/Edge: click the install icon in the address bar to install as a desktop/mobile app for a native-like experience.

---

*Developed for Philippine secondary schools in compliance with DepEd Phil-IRI framework.*
