# 🎓 Education Platform Backend

Backend service for the **Education Platform**, built with **NestJS**, **TypeORM**, and **PostgreSQL**.  
This backend provides APIs for authentication, user management, courses, groups, attendance, and integrations (Zoom, Stripe, etc.).

---

## 🚀 Features
- **Authentication & Authorization**  
  - JWT-based authentication  
  - Role-based access control (Admin, Teacher, Student, Parent)  

- **Course & Group Management**  
  - Students, Teachers, Groups, and Sessions  
  - Attendance tracking  

- **Integrations (planned / partial)**  
  - Zoom API for live classes  
  - Stripe for payments  
  - File upload system  

---

## 🛠️ Tech Stack
- **Framework**: [NestJS](https://nestjs.com/) (Node.js)  
- **Database**: PostgreSQL (hosted externally, not in Docker)  
- **ORM**: TypeORM  
- **Authentication**: JWT & Bcrypt  
- **Containerization**: Docker  
- **Environment Management**: `.env` file  

---

## 📂 Project Structure
```
backend/
├── src/
│   ├── modules/         # Feature-based modules (auth, users, groups, sessions, etc.)
│   ├── common/          # Shared utilities, interceptors, guards
│   ├── main.ts          # App entry point
│   └── app.module.ts    # Root module
├── dist/                # Compiled files (after build)
├── Dockerfile           # Multi-stage Docker build
├── package.json         # Dependencies
├── tsconfig.json        # TypeScript config
├── .env                 # Environment variables
└── README.md            # Documentation
```

---

## ⚙️ Environment Variables

Create a `.env` file in the project root:

```env
# Database
DB_HOST=
DB_PORT=
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=

# JWT
JWT_SECRET=your-super-secret-jwt-key-change-in-production
JWT_EXPIRES_IN=7d

# Zoom API
ZOOM_ACCOUNT_ID=
ZOOM_CLIENT_ID=
ZOOM_CLIENT_SECRET=

# Google APIs
GOOGLE_CALENDAR_CLIENT_ID=
GOOGLE_CALENDAR_CLIENT_SECRET=
YOUTUBE_API_KEY=

# Email
MAILCHIMP_API_KEY=
SMTP_HOST=
SMTP_PORT=587
SMTP_USER=
SMTP_PASS=

# Payment
STRIPE_SECRET_KEY=
STRIPE_PUBLISHABLE_KEY=

# Application
NODE_ENV=development
PORT=5000
FRONTEND_URL=http://localhost:3000

# Files
MAX_FILE_SIZE=50MB
UPLOAD_PATH=./uploads

# Security
BCRYPT_ROUNDS=12
SESSION_SECRET=your-session-secret-change-in-production
```

🐳 Running with Dock

1. Build the Docker image
```
docker build -t education-backend .
```
2. Run the container
```
docker run -d \
  --name education-backend \
  --env-file .env \
  -p 5000:5000 \
  education-backend
```
3. Check logs
```
docker logs -f education-backend
```

🧑‍💻 Running Locally (without Docker)
```
# Install dependencies
npm install

# Run in development
npm run start:dev

# Build for production
npm run build

# Run in production
npm run start:prod
```

🔑 Authentication
	•	All protected endpoints use JWT authentication.
	•	Include your token in the Authorization header








