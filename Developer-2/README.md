\# Developer 2: Database and Persistent Queue



\## Purpose

Hedwig CNMS database and persistent delivery queue (MySQL 8.4 + SQLx). Stores notifications, manages delivery jobs, and retries failed jobs safely.



\## Topics

\- Software Architecture: table design, queue design (claim, lease, retry), at-least-once delivery

\- DevOps Engineer: MySQL service setup, SQLx migrations, `.env`, Git branches and Pull Requests

\- QA Engineer: manual tests (5-worker concurrent claim, lease recovery, retry, dead jobs)

\- UI/UX Designer: backend module; status names and error messages should be clear to API users

\- AI Engineer: delivery history in `delivery\_attempts` can be used for analytics later



\## Contributions

\- D2-01 to D2-08 completed: setup, migrations, 6 tables, repository functions, safe queue claiming, leases and recovery, retry with backoff

\- Code: https://github.com/yashharie/Hedwig-Centralized-Notification-Management-System/pull/1

\- Docs: `docs/DATABASE.md` in the Hedwig repo



\## Goal

A reliable queue where multiple workers never process the same job at once, crashed workers do not block jobs, and failed deliveries are retried in a controlled way.

