# RakshaCircle

Production-ready women safety and emergency coordination platform powered by Stellar Soroban.

## Live Deployment

- Frontend: https://raksha-circle.vercel.app
- Backend API: https://rakshacircle-backend.onrender.com
- Soroban Contract ID (testnet): `CCTDYXR5HVBLHG6ZZ3XSSZHBGUUFVPWLN36RVDNRNJVKLQQPPUXUN747`

## Submission Proof Pack

- Metrics dashboard endpoint: https://rakshacircle-backend.onrender.com/api/v1/raksha/metrics
- Monitoring dashboard endpoint: https://rakshacircle-backend.onrender.com/api/v1/raksha/monitoring
- Production readiness endpoint: https://rakshacircle-backend.onrender.com/api/v1/raksha/production-readiness
- Metrics dashboard screenshot placeholder: `docs/proofs/metrics-dashboard.png`
- Monitoring dashboard screenshot placeholder: `docs/proofs/monitoring-dashboard.png`

## What RakshaCircle Delivers

- Wallet-based identity and profile setup
- Trusted contacts circle management
- SOS trigger and acknowledgement workflow
- On-chain integrity anchoring for critical safety events
- Production readiness surface with monitoring, indexing, and checklist visibility

## Tech Stack

- Frontend: React + TypeScript + Vite
- Backend: Node.js + Fastify
- Smart Contract: Rust + Soroban SDK (Stellar testnet)
- Auth model: Stellar wallet identity

## User Onboarding and Excel Export

- Google Form (collects name, email, wallet, rating, feedback): https://docs.google.com/forms/d/e/1FAIpQLScY0pVw0yrBbj1bjyf264mom1KSEumZsAjLCVGmVS1GOfWPVA/viewform?usp=sharing&ouid=110772656009502976350
- Response sheet (live): https://docs.google.com/spreadsheets/d/1ldTPP8M3xJDpWhhRNaDlsAwYa-4BgBCcrk_oJpqiKuA/edit?usp=sharing
- Excel export (.xlsx): https://docs.google.com/spreadsheets/d/1ldTPP8M3xJDpWhhRNaDlsAwYa-4BgBCcrk_oJpqiKuA/export?format=xlsx


## Data and Monitoring Endpoints

- Health: `/health`
- Blockchain status: `/api/v1/raksha/blockchain-status`
- Monitoring: `/api/v1/raksha/monitoring`
- Indexing: `/api/v1/raksha/indexing`
- Dashboard: `/api/v1/raksha/dashboard/:wallet`

## Metrics and Monitoring Submission Proof

- Metrics dashboard proof link: https://rakshacircle-backend.onrender.com/api/v1/raksha/metrics
- Monitoring dashboard proof link: https://rakshacircle-backend.onrender.com/api/v1/raksha/monitoring

### Metrics Dashboard Screenshot

![Metrics Dashboard](metrics%20and%20monitoring.png)

### Monitoring Dashboard Screenshot

![Monitoring Dashboard](MVP%20dashboard%20flow.png)

## Community and Improvement Evidence

- Community contribution package: [docs/COMMUNITY_CONTRIBUTION.md](docs/COMMUNITY_CONTRIBUTION.md)
- Live X post: https://x.com/georgian_deep/status/2040429057754685647?s=20
- Feedback-driven improvement commit: https://github.com/DeepSaha25/RakshaCircle/commit/e070bbe

## Feedback-Driven Improvement Roadmap 

Reference commit implemented from feedback:
- https://github.com/DeepSaha25/RakshaCircle/commit/e070bbe

## Deployment and Operations

- Deployment runbook: [DEPLOYMENT.md](DEPLOYMENT.md)
- Architecture and data flow: [ARCHITECTURE.md](ARCHITECTURE.md)
- Security controls: [docs/SECURITY_CHECKLIST.md](docs/SECURITY_CHECKLIST.md)
- Production readiness summary: [docs/PRODUCTION_READINESS.md](docs/PRODUCTION_READINESS.md)
- End-user operating guide: [docs/USER_GUIDE.md](docs/USER_GUIDE.md)

## Local Run (Quick)

```bash
# backend
npm install
npm run dev

# frontend (new terminal)
cd frontend
npm install
npm run dev
```

## License

MIT
