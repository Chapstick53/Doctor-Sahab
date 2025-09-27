# Doctor Appointment Portal (Doctor Sahab) - Backend

A robust and scalable backend system for a telemedicine platform built with **Node.js**, **Express**, and **MySQL**.  
This system supports appointment scheduling, patient management, doctor profiles, prescriptions, and real-time communication.

---

## 🚀 Features

### Core Functionality
- **User Authentication**: JWT-based authentication with Google OAuth integration  
- **Role-Based Access**: Patient, Doctor, and Admin roles with appropriate permissions  
- **Appointment Management**: Schedule, reschedule, cancel appointments with multiple status tracking  
- **Prescription System**: Digital prescriptions with report uploads and medication tracking  
- **Payment Integration**: Secure payment processing with transaction tracking  
- **Real-time Chat**: In-app messaging between doctors and patients  
- **Notifications**: Automated email and in-app notifications  

### Advanced Features
- **Multi-consultation Modes**: Online (video) and in-person appointments  
- **Doctor Availability**: Flexible scheduling system with time slot management  
- **Review System**: Patient feedback and rating system  
- **Admin Dashboard**: Comprehensive platform management and analytics  
- **Security**: bcrypt password hashing, input validation, and secure API endpoints  

---

## 🛠 Technology Stack
- **Backend**: Node.js, Express.js  
- **Database**: MySQL with optimized queries  
- **Authentication**: JWT, Google OAuth  
- **Security**: bcrypt, input validation, CORS  
- **Documentation**: Comprehensive API documentation  

---

## 📋 Prerequisites
- Node.js (v18 or higher)  
- MySQL (v8.0 or higher)  
- npm or yarn  

---

## ⚙️ Installation & Setup

### 1. Clone the Repository
    git clone <your-repo-url>
    cd doctor-appointment-portal/backend

### 2. Install Dependencies
    npm install

### 3. Database Setup
**Option A: Using the provided SQL dump**
    
    mysql -u root -p < doctor_appointment_app.sql

**Option B: Manual database creation**
    
    CREATE DATABASE doctor_appointment_app;
    USE doctor_appointment_app;

### 4. Environment Configuration
Create a `.env` file in the root directory:
    
    DB_HOST=localhost
    DB_USER=root
    DB_PASSWORD=your_mysql_password
    DB_NAME=doctor_appointment_app
    PORT=5000
    JWT_SECRET=your_very_secure_jwt_secret_key_here
    JWT_EXPIRES_IN=1d
    GOOGLE_CLIENT_ID=your_google_oauth_client_id

### 5. Start the Application
**Development mode (with auto-reload):**
    
    npm run dev

**Production mode:**
    
    npm start

Server runs on: **http://localhost:5000**

---

## 📡 API Endpoints

### Authentication
- POST /api/auth/register – User registration  
- POST /api/auth/login – User login  
- POST /api/auth/google – Google OAuth authentication  
- GET /api/auth/verify – Verify JWT token  

### Users
- GET /api/users – Get all users (Admin only)  
- GET /api/users/:id – Get user by ID  
- PUT /api/users/:id – Update user profile  
- DELETE /api/users/:id – Delete user (Admin only)  

### Appointments
- GET /api/appointments – Get appointments (with filters)  
- POST /api/appointments – Create new appointment  
- PUT /api/appointments/:id – Update appointment status  
- DELETE /api/appointments/:id – Cancel appointment  

### Patients
- GET /api/patients – Get patient profiles  
- POST /api/patients – Create patient profile  
- GET /api/patients/:id – Get specific patient details  

### Doctors
- GET /api/doctors – Get all doctors  
- POST /api/doctors – Register doctor profile  
- GET /api/doctors/:id – Get doctor details  
- PUT /api/doctors/:id – Update doctor profile  

### Admin
- GET /api/admin/dashboard – Admin dashboard statistics  
- GET /api/admin/users – Manage users  
- PUT /api/admin/users/:id – Update user status  

---

## 🗄 Database Schema
The system uses a normalized database with **12+ tables**.  

### Key Tables
- users – User accounts with role-based authentication  
- patients – Patient-specific information and medical history  
- doctors – Doctor profiles with specialization and availability  
- appointments – Appointment scheduling with status tracking  
- prescriptions – Digital prescriptions and medical records  
- payments – Payment transaction records  
- chat_messages – Real-time messaging system  
- reviews – Patient feedback and ratings  

---

## 🔒 Security Features
- Password hashing with bcrypt  
- JWT token-based authentication  
- Google OAuth integration  
- Input validation and sanitization  
- SQL injection prevention  
- CORS configuration  
- Environment variable protection  

---

## 🧪 Testing the API
You can test with Postman or Thunder Client.  

**Sample API Call – User Registration:**
    
    POST http://localhost:5000/api/auth/register
    Content-Type: application/json

    {
      "name": "John Doe",
      "email": "john@example.com",
      "password": "securepassword123",
      "phone_number": "9876543210",
      "role": "patient"
    }

**Sample API Call – Create Appointment:**
    
    POST http://localhost:5000/api/appointments
    Content-Type: application/json
    Authorization: Bearer <your_jwt_token>

    {
      "patient_id": 1,
      "doctor_id": 1,
      "appointment_date": "2024-01-15",
      "start_time": "10:00:00",
      "reason_for_visit": "Regular checkup",
      "consultation_mode": "online"
    }

---

## 📊 Project Structure
    backend/
    ├── config/
    │   └── db.js
    ├── controllers/
    │   ├── adminController.js
    │   ├── appointmentsController.js
    │   ├── authControllers.js
    │   ├── doctorsController.js
    │   ├── patientsController.js
    │   ├── reviewsController.js
    │   └── usersController.js
    ├── middleware/
    │   └── authMiddleware.js
    ├── routes/
    │   ├── admin.js
    │   ├── appointments.js
    │   ├── auth.js
    │   ├── doctors.js
    │   ├── patients.js
    │   └── users.js
    ├── utils/
    │   └── dbHelpers.js
    ├── docs/
    ├── app.js
    └── doctor_appointment_app.sql

---

## 🎯 Visuals to Showcase on GitHub
1. Database Schema Diagram – ER diagram for table relationships  
2. API Documentation Screenshots – Postman / Swagger examples  
3. Architecture Diagrams – System flow + API structure  
4. Code Quality Metrics – Folder structure, clean code snippets  
5. Performance Metrics – API response times, query optimizations, load testing  
6. Security Implementation – JWT flow diagram, password hashing, validation examples  

---

## 🚀 Deployment
Production `.env` example:
    
    NODE_ENV=production
    DB_HOST=your_production_db_host
    DB_USER=your_production_db_user
    DB_PASSWORD=your_production_db_password
    DB_NAME=your_production_db_name
    JWT_SECRET=your_production_jwt_secret
    GOOGLE_CLIENT_ID=your_production_google_client_id

---

## 🤝 Contributing
1. Fork the repository  
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)  
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)  
4. Push to the branch (`git push origin feature/AmazingFeature`)  
5. Open a Pull Request  

---

## 📝 License
This project is licensed under the **ISC License**.

---

## 👥 Authors
- Your Name – Initial work  

---

## 🙏 Acknowledgments
- Express.js team for the robust framework  
- MySQL community for database support  
- JWT for secure authentication  
