# Project Instructions: NVJ Studio POS & Management System

## 1. Project Overview
A minimalist, high-performance web-based management system for NVJ Studio. The system handles lead tracking, collaboration management (Models/MUAs), and automated invoicing.

**Brand Identity:**
- **Primary Palette:** #000000 (Black), #FFFFFF (White).
- **Secondary Palette:** #1F2937 (Deep Gray), #F3F4F6 (Light Gray).
- **Vibe:** Editorial, Clean, Professional.

---

## 2. Business Requirements

### A. Lead & Project Management
- **Lead Intake:** Capture client name, event type (Wedding/Concept), date, and budget.
- **Workflow Status:** Track projects through: `Inquiry` → `Booked` → `Shot` → `Editing` → `Delivered`.
- **Collaboration Directory:** A dedicated space to store contact details and social handles for Models and Makeup Artists (MUAs).

### B. POS & Invoicing
- **Invoice Generation:** Create professional invoices with auto-calculated totals and taxes.
- **Payment Tracking:** Log "Advance Payment" vs. "Balance Due."
- **Export:** Generate a "Print-friendly" or "Save as PDF" view for clients.

### C. Creative Briefing
- **Concept Notes:** A text area for each project to store "Creative Look" ideas or mood board links.

---

## 3. Technical Requirements

### A. Tech Stack
- **Frontend:** HTML5, Tailwind CSS (via CDN or CLI).
- **Database:** Dexie.js (Wrapper for IndexedDB) for local-first data storage.
- **Icons:** Lucide-icons or Heroicons (Minimalist line style).

### B. Database Schema (Dexie.js)
```javascript
const db = new Dexie('NVJStudioDB');
db.version(1).stores({
  leads: '++id, clientName, type, date, status',
  collaborators: '++id, name, role, instagram',
  invoices: '++id, leadId, totalAmount, amountPaid, status'
});