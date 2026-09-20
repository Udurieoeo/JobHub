# JobHub

A full-stack job portal and applicant tracking app. Employers post jobs and review applicants; job seekers search, save, and apply with a resume and get email updates when their application status changes.

**Stack:** Java 17+ · Spring Boot 3 · Spring Security (JWT) · Spring Data JPA / Hibernate · MySQL · React 19 · Vite · Tailwind CSS

> **Attribution:** JobHub is built on top of [ahmedhossam32/FullStackJobPortal](https://github.com/ahmedhossam32/FullStackJobPortal). Credit for the original application goes to its author. See [What I changed](#what-i-changed) for my work on top of it.

---

## Features

**Job seeker**
- Sign up and log in (JWT authentication)
- Browse, search, and filter jobs by title, location, and type, with pagination
- Save and unsave jobs
- Apply with a resume upload and answer optional screening questions
- Track applications and withdraw them
- In-app notifications and email updates when the status changes

**Employer**
- Sign up and log in
- Post, edit, and delete jobs (responsibilities, required skills, screening questions)
- View applicants per job and review resumes
- Change an application's status
- Dashboard with job and application counts

**Application statuses:** `PENDING` → `REVIEWED` → `INTERVIEW` → `OFFERED` / `REJECTED` (or `WITHDRAWN` by the applicant)

## Tech stack

| Layer | Technology |
|-------|-----------|
| Backend | Java 17+, Spring Boot 3.5, Spring Security + JWT, Spring Data JPA (Hibernate), Bean Validation |
| Database | MySQL 8 |
| File storage | Cloudinary (resumes and profile pictures) |
| Email | Spring Mail over SMTP (Gmail app password or any SMTP provider) |
| Extras | Bucket4j + Caffeine rate limiting on auth endpoints, global exception handling, DTO layer |
| Frontend | React 19, Vite, Tailwind CSS 4, React Router 7, Axios, React-Toastify |

## What I changed

- Migrated the database layer to **MySQL** (driver, connection settings, and test containers)
- Moved all configuration into environment variables (`.env`) with a committed `application.properties` that contains no secrets
- Configured **SMTP email notifications** for application confirmations and status updates
- Added an optional `docker-compose.yml` (MySQL + backend)
- Removed the original author's tooling files and screenshots

## Run it locally

**Prerequisites:** JDK 17 or newer, Node.js 20 or newer, MySQL 8 running on `localhost:3306`.

### 1. Clone

```bash
git clone https://github.com/Udurieoeo/JobHub.git
cd JobHub
```

### 2. Backend

```bash
cd Backend/JobPortal
```

Create your settings file from the template (Windows: `copy .env.example .env`, Mac/Linux: `cp .env.example .env`) and fill in the values:

| Variable | Required | Notes |
|----------|----------|-------|
| `DB_USERNAME` | yes | usually `root` |
| `DB_PASSWORD` | yes | your MySQL password |
| `JWT_SECRET` | yes | at least 32 characters |
| `CLOUDINARY_CLOUD_NAME`, `CLOUDINARY_API_KEY`, `CLOUDINARY_API_SECRET` | for uploads | free account at cloudinary.com |
| `MAIL_HOST`, `MAIL_PORT`, `MAIL_USERNAME`, `MAIL_PASSWORD`, `MAIL_SMTP_AUTH`, `MAIL_SMTP_STARTTLS`, `MAIL_FROM` | for emails | see the comments in `.env.example` |

The database `jobhub` is created automatically on first run. The app starts without the Cloudinary and mail values, but uploads and emails need them.

Start the backend (port 8080):

```bash
# Windows
.\mvnw.cmd spring-boot:run

# Mac / Linux
./mvnw spring-boot:run
```

### 3. Frontend

In a second terminal:

```bash
cd Frontend/JobPortalFront
npm install
npm run dev
```

Open http://localhost:5173. The frontend calls the API at `http://localhost:8080` by default (override with `VITE_API_URL`).

### Optional: Docker

```bash
docker compose --env-file Backend/JobPortal/.env up --build
```

Starts MySQL and the backend. This setup is experimental and not fully tested.

## Project structure

```
JobHub/
├── Backend/JobPortal/          Spring Boot API (controller → service → repository → entity)
├── Frontend/JobPortalFront/    React + Vite app
└── docker-compose.yml          Optional MySQL + backend containers
```

## Planned

- Recruiter pipeline board: move candidates between stages and keep a status history
- Recruiter notes on applications

<!-- Add your own screenshots to a docs/screenshots folder and link them here. -->

## Credits

Original application by [ahmedhossam32](https://github.com/ahmedhossam32/FullStackJobPortal).
