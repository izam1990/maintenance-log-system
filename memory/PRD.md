# Maintenance Log System - Product Requirements Document

## Original Problem Statement
Build a daily maintenance log application that allows users to enter: date, machine, location, work description, spare parts used, and who performed the work. The primary feature is to automatically generate an Excel file of the logs on a month-wise basis.

## Live Deployment URLs
- **Frontend:** https://maintenance-frontend-gn0w.onrender.com
- **Backend:** https://maintenance-backend-k8mp.onrender.com
- **Database:** MongoDB Atlas (Cluster0)

## Completed Features

### Core Features
- [x] Maintenance log entry form (date, machine, location, work description, spare parts, technician)
- [x] Month-wise Excel export functionality
- [x] "Total Time" field for maintenance duration tracking

### Authentication & Authorization
- [x] JWT-based user authentication (login/register)
- [x] Role-based access control (Admin/User)
- [x] Admin: Full control - add, edit, delete logs, manage dropdowns
- [x] User: Limited access - add logs and view data only
- [x] Admin password reset feature

### Configuration Management
- [x] Admin-managed dropdown options (machines, technicians, spare parts)
- [x] Dynamic configuration without code changes

### Progressive Web App (PWA)
- [x] Installable on mobile devices and desktop
- [x] Service worker for offline caching
- [x] App manifest for native-like experience

### Deployment
- [x] Backend deployed to Render (Python/FastAPI)
- [x] Frontend deployed to Render (React Static Site)
- [x] Database hosted on MongoDB Atlas (Free Tier)
- [x] Accessible from anywhere on the internet

## Technical Architecture

### Frontend (React)
- React 19 with React Router
- Tailwind CSS for styling
- Shadcn/UI components
- Axios for API calls

### Backend (FastAPI)
- Python FastAPI framework
- Motor (async MongoDB driver)
- JWT authentication with bcrypt password hashing
- RESTful API design

### Database (MongoDB Atlas)
- Cloud-hosted MongoDB
- Collections: users, maintenance_logs, config_items

## API Endpoints
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user info
- `GET /api/auth/users` - List all users (admin only)
- `POST /api/auth/reset-password` - Reset user password (admin only)
- `GET /api/logs` - Get all maintenance logs
- `POST /api/logs` - Create new log
- `PUT /api/logs/{id}` - Update log (admin only)
- `DELETE /api/logs/{id}` - Delete log (admin only)
- `GET /api/config` - Get dropdown options
- `POST /api/config` - Add dropdown option (admin only)
- `DELETE /api/config/{id}` - Remove dropdown option (admin only)

## User Credentials
- First registered user automatically becomes admin
- Subsequent users get "user" role

## Important Notes
- Render FREE plan: Services sleep after 15 minutes of inactivity
- First visit after sleep may take 30-60 seconds to wake up
- MongoDB Atlas FREE tier: 512MB storage limit

## GitHub Repository
https://github.com/izam1990/maintenance-log-system-

## Project Status: COMPLETE ✅
All requested features have been implemented and deployed successfully.
