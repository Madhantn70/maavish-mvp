# Maavish — Implementation Tasks (Priority order)

1. Project scaffolding (monorepo, README, docker-compose).
2. Backend: NestJS init + DB connection + basic auth (JWT stub).
3. Backend: products module (entity, CRUD API).
4. Frontend: Next.js init + product list page.
5. Cutoff logic: implement in backend (service) + frontend display.
6. Cart & checkout API + frontend flow (simple UI).
7. Subscriptions: model + allocate job (nightly).
8. Wallet: ledger model + Razorpay sandbox integration.
9. Admin UI: product CRUD + stock entry + order board.
10. Background jobs: setup Redis + Bull + 22:00 allocation + 05:00 auto-debit.
11. Testing + edge case checks (cutoff 1:59 vs 2:01, wallet race conditions).
12. Deployment scripts + README runbook.
