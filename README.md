# 💼 Full Stack Job Portal App

A complete **full-stack job portal web application** built with **Java Spring Boot (Backend)** and **React + Vite (Frontend)**.  
It supports **secure authentication**, job browsing, filtering, saving, applying, and **role-based access** for job seekers and employers.  

This project is designed to provide a **real-world job marketplace experience** — from a job seeker discovering, applying, and tracking jobs,  
to an employer posting jobs, managing applicants, and making hiring decisions.  

Every feature was **planned, built, and tested end-to-end**, covering frontend, backend, database, and API integration.

---
🌐 **Live Demo:** [jobportal.dev](https://www.jobportal.dev/)  
📁 **GitHub:** [FullStackJobPortal](https://github.com/ahmedhossam32/FullStackJobPortal)
---

## 📖 About the Project

This application simulates the core workflows of modern job platforms like LinkedIn or Indeed but built entirely from scratch.  
It includes **secure JWT authentication**, dynamic job listing, saving and applying features, applicant management, and a fully interactive dashboard for employers.  

The project required:  
- Building a **REST API** with authentication, file upload handling, and relational data modeling in the backend.  
- Designing and implementing a **responsive React UI** from scratch without pre-made templates.  
- Managing **real-time-like updates** (e.g., notifications, application status changes).  
- Writing clean, maintainable code with modular architecture.

---
## 🛠️ Built With

### 🧠 Backend
- Java 17
- Spring Boot
- Spring Security with JWT + OAuth2
- Hibernate (JPA)
- MySQL
- Cloudinary (cloud file storage)
- Docker & Docker Compose
- Lombok

For the full backend documentation and implementation details,  
please navigate to the [Backend README](./Backend/JobPortal/README.md).

### 🎨 Frontend
- React.js
- Vite
- Axios
- Formik
- Context API
- Tailwind CSS

### ☁️ Deployment
- DigitalOcean — Backend (Spring Boot + MySQL)
- Vercel — Frontend (React)
- Cloudinary — File & image storage
- Custom domain — [jobportal.dev](https://www.jobportal.dev/)

---

## ✨ Features

### 👤 Job Seeker
- **Authentication:** Secure sign up, sign in, and logout flows.
- **Job Discovery:** Browse, filter, and search jobs by title, location, and type.
- **Job Details:** View full job descriptions, responsibilities, and required skills.
- **Job Saving:** Save and unsave jobs with instant visual feedback.
- **Applications:** Apply to jobs, answer optional screening questions, and upload a resume.
- **Tracking:** View saved jobs, applied jobs, and detailed application status.
- **Management:** Withdraw applications at any time.
- **Profile Editing:** Update profile picture, resume, username, email, etc.
- **Notifications:** Get notified when application status changes, and mark notifications as read.

### 🧑‍💼 Employer
- **Authentication:** Sign up, sign in, and logout.
- **Job Posting:** Create and publish jobs with full details, responsibilities, skills, and optional screening questions.
- **Job Management:** Edit and delete posted jobs.
- **Applicant Management:** View applicants per job or across all jobs.
- **Decision Making:** Accept or reject applicants and notify them automatically.
- **Resume Review:** View resumes directly in-browser.
- **Dashboard:** View statistics for total jobs, applicants, accepted, rejected, and pending applications.

---
## 🌟 Why This Project Stands Out

- **60+ unique UI screens** designed and implemented manually.
- **Fully functional backend** with clean service-layer architecture and DTO separation (request/response).
- **Real database integration** (MySQL) with optimized queries and entity relationships.
- **Cloud file storage** via Cloudinary for profile pictures and resume uploads.
- **Pagination** on all job listing endpoints for optimized performance and reduced server load.
- **Notification system** that mimics real-time updates using efficient state management.
- **Role-based access control** with @PreAuthorize annotations protecting every endpoint (JOB_SEEKER / EMPLOYER).
- **Global exception handling** ensuring consistent, proper error responses across the app.
- **Dockerized backend** for consistent and portable deployment.
- **CORS security** restricted to specific allowed origins only.
- **Responsive design** that adapts to all screen sizes including mobile.
- **Deployed with a custom domain** — fully accessible at [jobportal.dev](https://www.jobportal.dev/).



## 📂 Project Structure
project-root/
│ README.md
│ Full_Walkthrough.md
│ backend/
│ frontend/
└── ScreenShots/
