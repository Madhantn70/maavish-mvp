# Maavish — High Level Design

## Tech choices (MVP)
- Frontend: Next.js (React) — easier to run and deploy; PWA-capable.
- Backend: NestJS (Node + TypeScript) — modular, good for APIs and background jobs.
- Database: PostgreSQL (can use Supabase for hosted Postgres + Auth).
- Background jobs: Redis + BullMQ (or use a hosted job runner).
- Auth: Firebase OTP or simple OTP via backend + Twilio (Firebase is easiest).
- Payments: Razorpay sandbox for wallet top-up.
- Storage: S3 or local during dev.
- Notifications: Firebase Cloud Messaging.

## Architecture (short)
Frontend (Next.js) <--> Backend (REST) (NestJS) <--> Postgres
                           |
                        Redis (jobs)
                           |
                      Background worker

## Dev environment
- Monorepo layout:
  /frontend (Next.js)
  /backend (NestJS)
  /infra (docker-compose with postgres + redis)
- Docker-compose for local dev.

## Deploy
- Frontend -> Vercel
- Backend -> Render / Railway / Heroku
- Postgres -> Supabase / ElephantSQL
