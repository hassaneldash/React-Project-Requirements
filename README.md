# 🏥 React Project: Medical Booking App

**Deadline:** 7 Days  
**Tech Stack:** React, Laravel/Django Backend, TailwindCSS/Material UI

---

## ⭐ Project Overview
The application is a role-based medical appointment booking system. Patients can browse doctors and book slots, doctors can manage their availability and view schedules, and administrators have full oversight of the platform's users and configurations. You will utilize the React ecosystem libraries and best practices to deliver these requirements.

> **UI Framework:** You must build the UI using Material UI or any other UI library except Bootstrap (Don't use Bootstrap). All routing should utilize Role-based routing using React Router.

---

## 🗺️ Frontend Routes
Configure your React Router implementation with the following paths, ensuring a 404 Not Found page is properly handled and Role-Based Access Control (RBAC) is enforced.

| Type | Page Description | Route Path |
| :--- | :--- | :--- |
| `ROUTE` | **Doctor Search** (Main page with specialty/name filters) | `/` |
| `ROUTE` | **Doctor Profile & Booking** (View availability and book slot) | `/doctor/:id` |
| `PRIVATE` | **Patient Dashboard** (View, cancel, or reschedule appointments) | `/patient/dashboard` |
| `PRIVATE` | **Doctor Dashboard** (Set availability, view upcoming/past appointments) | `/doctor/dashboard` |
| `PRIVATE` | **Admin Dashboard** (System management, approve/block users) | `/admin/dashboard` |
| `ROUTE` | **Login** (Authentication for all roles) | `/login` |
| `ROUTE` | **Register** (Patients and Doctors can register) | `/register` |
| `PRIVATE` | **Profile Edit** (Logged-in user info) | `/profile` |
| `ERROR` | **404 Not Found** (Catch-all for invalid URLs) | `*` |

---

## 👥 Suggested Work Division

### 1️⃣ Data & Auth Lead
* JWT Token-based authentication
* Login & Register pages
* Global state setup (Context/Redux Toolkit)
* Role-Based Access Control logic

### 2️⃣ Patient UX Lead
* Doctor search, sorting & filtering
* Appointment booking logic
* Real-time availability validation
* Pagination implementation

### 3️⃣ Doctor & Admin Lead
* Doctor availability scheduling
* Admin Dashboard (Approve/Block)
* CRUD on system configs
* React Router (Lazy Loading)

### 4️⃣ UI/UX Lead
* Material UI/Tailwind implementation
* Dark Mode & Dynamic Titles
* i18n (Language LTR/RTL)
* Loading Skeletons & Global Toasts

---

## ⚙️ Core Functional Requirements

### 1. Patient Capabilities
* **Discovery:** View list of available doctors with functional filters for specialty and name.
* **[Bonus] Sorting:** Sort doctors by rating, specialty, or availability using query parameters (e.g., `sort_by=rating`).
* **[Bonus] Pagination:** Paginate between doctor list pages and admin master lists by sending a query parameter (e.g., `page=2`).
* **Booking:** View a doctor's availability and book an appointment (date/time slot).
* **Management:** View, cancel, or reschedule existing appointments. Edit personal profile.
* **Validation:** Ensure real-time validation of availability to completely avoid double booking.
* **[Bonus] Search Debouncing:** Implement a debounce utility (e.g., 500ms delay) on the search input to protect backend API rate limits.

### 2. Doctor & Admin Capabilities
* **Doctor Scheduling:** Set availability schedule (days/times).
* **Doctor Dashboard:** View upcoming and past appointments. Manage profile (specialty, bio, contact). Optionally mark appointments as approved or rejected, and add notes.
* **Admin Moderation:** View all users (doctors & patients). Approve or block doctors/patients.
* **Admin Config:** Perform CRUD operations on specialties, doctors, and other system configurations. View all appointments system-wide.

### 3. UI Enhancements & Auth
* **UI Components:** Use Material UI or another UI library except Bootstrap.
* **Authentication:** Secure login/authentication handling (JWT) via Django Rest Framework or Laravel Sanctum.
* **State & Forms:** Strict form validation and state management via Context API or Redux Toolkit.
* **[Bonus] Enhancements:** Implement Dynamic Page Titles (updating the browser tab to match the view) and a Back to Top Button.
* **[Bonus] Notifications:** Provide user feedback via a Snackbar/Toast library for successful bookings or form errors.
* **[Bonus] Empty States & Skeletons:** Display Skeleton components while fetching doctor availability. Show a clear "Empty State" graphic if no appointments exist.

### 4. Architecture & Best Practices
* **Role-Based Routing:** Implement role-based routing using React Router to strictly secure Patient, Doctor, and Admin views.
* **[Bonus] API Error Handling:** Implement global or component-level error handling. Display user-friendly error messages (via Toasts) if fetching fails.
* **[Bonus] Custom Hooks:** Create custom hooks or utility files (e.g., Axios instances) to separate backend API requests from UI components.
* **[Bonus] i18n:** Language dropdown (e.g., English, Arabic) changing the text and dynamically switching layout to RTL for Arabic.
* **[Bonus] Dark Mode Toggle:** Implement a functional dark mode switch for the medical platform.
* **[Bonus] Lazy Loading:** Use `React.lazy()` and `<Suspense>` to code-split page routes, ensuring the Admin Dashboard code is only loaded for Admins.

---

## 📡 Expected Backend API Reference

| Method | Endpoint Purpose | Suggested URL Structure |
| :--- | :--- | :--- |
| `GET` | Available Doctors List | `/api/doctors?specialty={id}&sort_by={rating}&page={page}` |
| `GET` | Doctor Availability | `/api/doctors/{id}/availability` |
| `POST` | Book Appointment | `/api/appointments/book` |
| `GET` | User Appointments | `/api/appointments` |
| `PUT` | Update Appointment Status | `/api/appointments/{id}/status` |
| `GET` | Admin: All Users | `/api/admin/users` |
| `POST` | Register (Patient/Doctor) | `/api/auth/register` |
| `POST` | Login (Obtain JWT) | `/api/auth/login` |
| `GET` | Profile Data | `/api/auth/profile` |

---

## 📦 Submission Guidelines

### 1. Timeline & Estimate
* Provide an estimate sheet with features, initial estimates, and actual spent time.
* Use the provided Google Sheet link (make a copy).
* Maximum of `7 days` to complete and submit.

### 2. Version Control & Hosting
* Link project with GitHub, pushing commits per feature.
* Deliver the GitHub link and add `hassaneldash` to the repository as a collaborator.
* Host using Cloudflare, Vercel, Netlify, or GitHub Pages and provide the live link.

### 3. Final Submission
* Send everything to `hassanmeldash@gmail.com`.
* **Email subject:** `ITI Menofia | OS46 | React Project | Medical App | Group No.?`
* **Evaluation:** Record a comprehensive video walkthrough detailing your entire application. Your final grade will be evaluated on functional completeness, the structural quality of your code, and a consistent GitHub commit history.

---

## 💡 Developer Checklist
* 🚀 **Component Reusability:** Create reusable React components for doctor profile cards and appointment list items.
* 🛜 **Debounce API Calls:** Don't spam the backend API. Ensure your debounce hook is working before testing doctor search extensively.
* 🎨 **Graceful Loading:** Implement UI Skeletons early so the interface never looks broken while fetching doctor schedules or appointments.
* 📁 **Project Structure:** Maintain clear separation of Custom Hooks for Axios, Global States for Auth, and UI components.

---
**Good Luck!** *Hassan ELDash💖*
