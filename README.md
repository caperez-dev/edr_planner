# EDR MOP & Application Planner

A lightweight, zero-install, single-file web application for managing, scheduling, and executing Enterprise Disaster Recovery (EDR) Methods of Procedure (MOPs) and application failover/failback workflows.

---

## 🚀 Quick Start / How to Use

1. **Open the App**:
   - Double-click [`edrplanner.html`](file:///c:/Dev%20Projects/edr_planner/edrplanner.html) to open directly in any modern browser (Chrome, Edge, Firefox), or serve locally:
     ```bash
     npx serve -l 8080
     # then open http://localhost:8080/edrplanner.html
     ```
2. **Load Applications / MOPs**:
   - **Single MOP**: Click **`Add App`** on the left sidebar to upload an individual JSON/JS MOP file.
   - **Multi-App Workspace**: Click **`Import JSON`** on the top banner to load complete multi-application plans exported previously.
3. **Navigate & Filter**:
   - Switch between **All Applications** or click a specific app in the left sidebar.
   - Use the global search bar (`Search tasks, owners, issues...`) to filter tasks across phases.
4. **Edit Tasks & Options**:
   - **Edit any cell**: Double-click, right-click, or press `Enter`/`Space` on any task row to update schedules, duration, task details, assignees (Owner/Backup/Checker), comments, or issues.
   - **Edit App Details**: Hover over an app in the sidebar and click the **Pencil icon**.
   - **Configure Dropdowns**: Click **`Settings`** on the top banner to add or delete Dependency and Task Type options.
5. **Timeline & Views**:
   - Toggle **`Timeline`** to view a synchronized, side-by-side 24-hour visual schedule alongside the table.
   - Switch to **`Calendar`** view (Day, Week, Month, Year) to inspect planned vs. actual milestone windows.
6. **Export & Share**:
   - **`Export JSON`**: Exports portable state (`edr-planner-table.json`) to transfer plans to another user/device.
   - **`Export XLSX`**: Generates a formatted multi-sheet Excel spreadsheet (one sheet per application).

---

## 🛠️ Tech Stack & Justification

| Technology | Role | Why It Was Chosen |
| :--- | :--- | :--- |
| **Vanilla HTML5 & JavaScript (ES6+)** | Core Application & State Engine | Runs out of the box in any browser without Node.js, build tools, bundlers, or runtime dependencies. Easy handoff and instant portability. |
| **Tailwind CSS (CDN)** | Responsive UI & Design System | Rapid enterprise-grade styling with seamless dark/light mode toggle, clean typography, and zero CSS build pipeline needed. |
| **SheetJS (`xlsx.full.min.js`)** | Excel Workbook Export | Client-side Excel `.xlsx` generation with automatic multi-sheet structure and tailored column widths. |
| **Lucide Icons** | Visual UI Iconography | Lightweight, crisp SVG icons rendered on-the-fly without font asset dependencies. |
| **Browser `localStorage`** | Local State Persistence | Automatically saves uploaded applications, custom dropdowns, freeze states, column visibility, and theme across sessions without a database server. |

---

## 🌟 Key Features

- **Side-by-Side Dual View**: 75% interactive data table aligned 1:1 with a 25% hourly visual Gantt timeline.
- **Failover & Failback Hierarchy**: Pre-structured phases (`Failover`, `Failback`) and sub-phases (`Pre Failover`, `Failover`, `Testing`, `Post Failover`, etc.) with expandable/collapsible groupings.
- **Unified Inline Cell Editor**: Double-click or right-click cell editing with searchable team member pickers, datetime pickers, and auto-computed timestamps.
- **Dynamic Column Controls**: Right-click header context menu to toggle column visibility and lock button to freeze columns with sticky horizontal scrolling.
- **Multi-Day Timeline**: Configurable date range filter with horizontally pinned sticky date headers and sleek gradient task duration bars.
- **Multi-View Calendar**: Drill-down calendar (Year ➔ Month ➔ Week ➔ Day) with color-coded milestone filters (`Planned Start`, `Planned End`, `Actual Start`, `Actual End`).
- **Backup & Handoff**: Dedicated JSON import/export for cross-device portability, plus XLSX export for executive reporting.

---

## 📑 Views & Modals Included

1. **Table View (`#tableWorkspace`)**: Primary planning interface featuring 15 data columns with inline editing and side-by-side Gantt timeline.
2. **Calendar View (`#calendarContainer`)**: Interactive scheduling calendar with Year, Month, Week, and Day drill-downs.
3. **Upload / Import Modal (`#uploadModal`)**: Drag-and-drop zone with mode switching between single-app MOP upload and multi-app bundle import.
4. **Settings Modal**: Manages custom drop-down chips for Task Dependencies and Task Types with hover-to-delete.
5. **App Attributes Modal**: Edits application name, description, and displays automated last-updated timestamps.
6. **Timeline Range Modal**: Custom start and end date selector for the timeline view with an auto-detect reset button.
7. **Action Confirmation Modal (`#confirmActionModal`)**: Clean verification dialog for destructive or export actions (Clear Plan, Delete App, Export).
