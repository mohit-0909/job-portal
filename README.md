# Job Portal
A microservices-based job portal platform with a Next.js frontend and Node.js/TypeScript backend services.
## Architecture
- `frontend` - Next.js 16 + React 19 client application
- `services/auth` - authentication service
- `services/user` - user profile/user management service
- `services/job` - job posting and listing service
- `services/payment` - payment integration service (Razorpay)
- `services/utils` - shared utility service (mail, cloud, AI, Kafka helpers)
## Tech Stack
- Frontend: Next.js, React, TypeScript, Tailwind CSS
- Backend: Node.js, Express, TypeScript
- Messaging: Kafka (`kafkajs`)
- Database driver: Neon serverless client
- Caching/queue helpers: Redis (used in auth service)
- File/media utilities: Multer, Cloudinary
- Payments: Razorpay
- Email: Nodemailer
## Prerequisites
- Node.js 18+ (recommended: latest LTS)
- npm 9+
- Kafka running locally or remotely
- Redis (if required by your auth flow)
- Service-specific environment variables
## Project Setup
### 1) Clone the repository
```bash
git clone https://github.com/mohit-0909/job-portal.git
cd job-portal
2) Install dependencies
Install per package:

cd frontend && npm install
cd ../services/auth && npm install
cd ../job && npm install
cd ../user && npm install
cd ../payment && npm install
cd ../utils && npm install
Run the Project
Open separate terminals for each service.

Frontend
cd frontend
npm run dev
Backend services (example)
cd services/auth
npm run dev
Repeat the same for:

services/user
services/job
services/payment
services/utils
Build and Start (Production mode)
For each backend service:

npm run build
npm start
For frontend:

cd frontend
npm run build
npm start
Environment Variables
Create .env files in each service as needed.

Typical values used across services may include:

PORT
DATABASE_URL
JWT_SECRET
REDIS_URL
KAFKA_BROKER
RAZORPAY_KEY_ID
RAZORPAY_KEY_SECRET
CLOUDINARY_*
MAIL_*

Available Scripts
Frontend (frontend/package.json)
npm run dev
npm run build
npm run start
npm run lint
Services (services/*/package.json)
npm run dev - TypeScript watch + nodemon
npm run build - install deps + compile TypeScript
npm run start - run compiled output
Notes
Ensure Kafka topics/brokers are configured before running event-driven flows.
Start utils service if other services depend on shared messaging/email utilities.
Update this README with endpoint docs when APIs are finalized.
