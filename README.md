# PostgreSQL Automated Backup API (`pg_dump` + Node.js)

![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat-square&logo=nodedotjs&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-pg__dump-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Nodemailer](https://img.shields.io/badge/Email-Nodemailer-0F9D58?style=flat-square)

## Executive Summary

A lightweight **Node.js & Express** backend service demonstrating programmatic **PostgreSQL** database backups via native `pg_dump` shell execution (`src/controller/scripts/backup.sh`), paired with timestamped `.sql` snapshot archiving and **Nodemailer** email notifications.

---

## Architecture & Key Features

- **Automated Shell Orchestration:** Invokes `backup.sh` (`pg_dump`) from Node.js controller logic (`src/controller/functions.js`, `index.controller.js`) to generate timestamped `.sql` snapshots under `src/controller/backups/`.
- **REST Trigger & Status Routes (`src/routes/index.js`):** Exposes clean Express endpoints to trigger on-demand database snapshots.
- **Email Alerting (`nodemailer`):** Sends automated confirmation or error reports via SMTP configured through environment variables (`dotenv`).
- **Sample Schema Included:** Ships with `database.sql` for quick local PostgreSQL setup and testing.

---

## Project Structure

```text
pg_dump_backup_example/
├── database.sql                    # Sample PostgreSQL schema
├── src/
│   ├── index.js                    # Express server entry point
│   ├── routes/index.js             # Backup API routes
│   └── controller/
│       ├── index.controller.js     # HTTP request handlers
│       ├── functions.js            # Backup & email orchestration helpers
│       ├── scripts/backup.sh       # pg_dump shell script
│       └── backups/                # Generated timestamped SQL snapshots
└── package.json
```

---

## Getting Started

```bash
# Install dependencies
npm install

# Configure PostgreSQL & SMTP variables in .env
# Start development server
npm run dev
```

---

## Author & Contact

**Héctor Joann Murillo Mejía** — Mobile & Full-Stack Software Engineer (React Native · TypeScript · Node.js)

- **Email:** [joannmurillo@icloud.com](mailto:joannmurillo@icloud.com)
- **LinkedIn:** [linkedin.com/in/hector-joann-murillo-mejia](https://www.linkedin.com/in/hector-joann-murillo-mejia/)
- **GitHub:** [github.com/jomudev](https://github.com/jomudev)
- **Portfolio:** [joannmurillo.com](https://www.joannmurillo.com)
