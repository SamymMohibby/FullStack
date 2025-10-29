# Workout Buddy — MERN Stack (with JWT Auth) BY SAMYM MOHIBBY

Simple workout tracking app (MERN). Backend provides REST API with JWT authentication. Frontend is a React SPA.

## Features
- Create / Read / Update / Delete workouts
- User signup & login with JWT-based authentication
- Protected routes on backend using JWT middleware
- Frontend context/hooks for auth and workouts

## Tech stack
- Frontend: React
- Backend: Node.js, Express
- Database: MongoDB (Mongoose)
- Auth: JSON Web Tokens (JWT)
- Dev tooling: ESLint/Prettier recommended

## Repository structure
```
/frontend
  package.json
  src/
    components/
      Navbar.js
      WorkoutDetails.js
      WorkoutForm.js
    context/
      AuthContext.js
      WorkoutContext.js
    hooks/
      useAuthContext.js
      useLogin.js
      useLogout.js
      useSignup.js
      useWorkoutsContext.js
    pages/
      Home.js
      Login.js
      Signup.js

/backend
  package.json
  server.js
  .env               # local: DO NOT COMMIT
  controllers/
    userController.js
    workoutController.js
  middleware/
    requireAuth.js
  models/
    userModel.js
    workoutModels.js
  routes/
    user.js
    workouts.js
```

## Setup (local)

Prerequisites: Node.js, npm, MongoDB (or Atlas).

1. Backend
```bash
cd backend
npm install
# create a backend/.env file with:
# PORT=4000
# MONG_URI=<your-mongo-connection-string>
# JWT_SECRET=<a-strong-secret>
npm run start
```

2. Frontend
```bash
cd frontend
npm install
npm start
# in the package.json add: "proxy": "http://localhost:4000"
# Opens at http://localhost:3000 (default)
```

## Environment variables (backend)
- PORT (4000)
- MONG_URI (MongoDB connection string)
- JWT_SECRET (used to sign JWTs)

## Routes (summary)
- POST /api/user/signup — create user
- POST /api/user/login — login (returns JWT)
- GET /api/workouts — get all workouts (protected)
- GET /api/workouts/:id — get single workout (protected)
- POST /api/workouts — create workout (protected)
- PATCH /api/workouts/:id — update (protected)
- DELETE /api/workouts/:id — delete (protected)
