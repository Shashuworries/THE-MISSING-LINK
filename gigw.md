# System Context: GIGW 3.0 UI/UX Compliance Rules for Civic Complaint Portal

This document defines the layout, visual design, accessibility standards, and structural guidelines based on the **Guidelines for Indian Government Websites (GIGW 3.0)** and **WCAG 2.1 AA** standards. 

Use these rules as a system context prompt when generating frontend code (React, HTML/Tailwind, Vue, Flutter, Figma wireframes) for the Civic Complaint Portal prototype (Smart India Hackathon).

---

## 1. Core Header & Footer Rules

### 1.1 Header Requirements
* **Skip to Main Content:** A mandatory hidden anchor link at the very top of the DOM (`href="#main-content"`), visible on keyboard focus (`Tab`).
* **Accessibility Controls:** Quick toggles for:
  * Text Size adjustment (`A-`, `A`, `A+`)
  * Color theme toggle (Standard / High Contrast Dark Mode)
* **Language Switcher:** Toggle between `English` and `Hindi` (or regional languages) prominently placed in the header.
* **Branding Area:**
  * Left: Target Ministry / Civic Authority name (e.g., *Nagrik Seva Portal / Municipal Corporation*).
  * Center/Right: Portal title and national initiative branding (e.g., *Digital India*).
  * *Note:* Avoid the official State Emblem (*Ashoka Stambh*) on non-official prototypes; use a standard civic icon/logo mockup.

### 1.2 Footer Requirements
* **Mandatory Policy Links:**
  * `Privacy Policy`
  * `Terms of Use`
  * `Website Policies`
  * `Help & FAQs`
  * `Contact Us`
  * `Disclaimer`
* **Ownership & Metadata:**
  * Department ownership statement (e.g., *"Designed & Developed for Smart India Hackathon Prototype"*).
  * `Last Updated: [Date]` stamp.
  * Copyright notice and version details.

---

## 2. Visual Design System & Styling

### 2.1 Color Palette Guidelines
* **Primary Color:** Deep Government Blue (e.g., `#003366` or `#1A365D`) for trust, security, and official tone.
* **Secondary Color:** Muted Slate/Navy (e.g., `#2B6CB0` or `#4A5568`).
* **Accent Colors:** Warm Saffron/Gold (`#D69E2E` or `#DD6B20`) for call-outs and highlight buttons.
* **Background:** Clean White (`#FFFFFF`) or Soft Off-White (`#F7FAFC`) to reduce eye strain.
* **Contrast Threshold:** All text-to-background combinations MUST satisfy a minimum contrast ratio of **4.5:1** for regular text and **3:1** for large bold headings.

### 2.2 Typography & Spacing
* **Font Family:** Clear, highly legible sans-serif fonts (e.g., `Noto Sans`, `Roboto`, or system-ui `sans-serif`) supporting Devanagari and Latin scripts.
* **Font Sizing Baseline:**
  * Body text: Minimum `16px` (`1rem`).
  * Form inputs: Minimum `16px` (prevents auto-zoom on mobile devices).
  * Headings (`H1` to `H4`): Clearly hierarchical and scalable.
* **Focus Outline:** High-visibility outline ring (`2px solid #D69E2E` or `3px solid #0056B3` with `outline-offset: 2px`) on all focusable elements during keyboard navigation.

---

## 3. Accessibility Standards (WCAG 2.1 Level AA)

### 3.1 Keyboard Navigation & Focus
* Every interactive component (buttons, inputs, dropdowns, modals, tabs) MUST be reachable and actionable via `Keyboard` (`Tab`, `Shift+Tab`, `Enter`, `Space`, Arrow keys).
* **No Keyboard Traps:** Focus must be able to move into and out of any component smoothly.

### 3.2 Screen Reader Support & ARIA
* **Semantic HTML:** Use native tags (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<button>`) instead of generic `<div>` wrappers.
* **Alt Text:** Every image, logo, and icon must have descriptive `alt` attributes. Decorative icons should use `aria-hidden="true"`.
* **Form Field Labels:** Every `<input>`, `<select>`, and `<textarea>` must have an explicit matching `<label for="...">`.
* **Dynamic Content:** Use `aria-live="polite"` for dynamic updates (e.g., status changes, error alerts, live complaint tracking updates).

---

## 4. Forms & Civic Complaint Submission Flow

### 4.1 Form Design Rules
* **Clear Input Grouping:** Group related fields logically (e.g., *1. Citizen Details*, *2. Complaint Category*, *3. Location & Media Upload*).
* **Explicit Help Text:** Instructions must appear below or alongside the label, not solely as placeholder text inside the input box.
* **Accessible CAPTCHA:** If CAPTCHA is included, an audio CAPTCHA option or visual refresh button must be provided.
* **Error Handling:** Form errors must be inline, highlighted in red (`#C53030`), clearly labeled with descriptive text, and announced to screen readers.

### 4.2 File Upload & Media Handling
* Allow image uploads (e.g., photos of potholes, fused lights, drainage issues).
* State explicit file constraints: allowed file types (JPG, PNG, PDF) and max size (e.g., *"Max 5MB"*).

### 4.3 Complaint Status & Badges
Use distinct, high-contrast badges for status tracking:
* **Pending / Submitted:** Muted Amber / Yellow (`#B7791F` on `#FEFCBF`)
* **In Progress / Assigned:** Informative Blue (`#2B6CB0` on `#EBF8FF`)
* **Resolved / Closed:** Success Green (`#2F855A` on `#F0FFF4`)
* **Rejected / Escalated:** Danger Red (`#C53030` on `#FFF5F5`)

---

## 5. Security, Usability & Hackathon Constraints

* **HTTPS Enforcement:** Protocol must strictly be encrypted.
* **Data Sanitization:** Strict frontend validation for inputs to prevent XSS and SQL injection attacks.
* **Responsive Layout:** 100% mobile-responsive layout for field usage by citizens and municipal staff.
* **Hackathon Prototype Disclaimer:** Include a small footer badge:
  > *"Prototype developed for Smart India Hackathon. Not an official Government of India product."*
