# TEAM NO.349-Healthcare Profiling for Patient Appointment Authorization in Secure Automation System
## About
Healthcare Profiling for Patient Appointment Authorization is a secure, automated web-based system designed to streamline patient appointment management while ensuring authorized and safe access to healthcare services.

The system leverages Spring Boot for backend services, React for frontend interaction, and secure authentication mechanisms to verify patient identity, profile risk levels, and automate appointment approvals.

1. It enables hospitals and clinics to:

2. validate patient records,

3. authorize appointments based on eligibility,

4. prevent unauthorized access,

5. and maintain secure healthcare data handling.

The platform enhances security, efficiency, and reliability in hospital appointment workflows while reducing manual administrative overhead.

## Features
🏥 Secure patient registration and login

🧾 Patient health profile creation

📅 Smart appointment booking & scheduling

✅ Automated appointment authorization

🔐 JWT-based authentication & role-based access

👨‍⚕️ Role management (Admin / Doctor / Patient)

🛡️ Encrypted medical data storage

⚛️ Responsive React-based user interface

🌐 RESTful API communication

## Development Requirements
### Backend
Java 17+

Spring Boot

Spring Security

JWT Authentication

Hibernate / JPA

MySQL / PostgreSQL

### Frontend
React.js

Axios

React Router

HTML, CSS, JavaScript

### Tools
Maven

Node.js & npm

Postman

IntelliJ IDEA / VS Code

## System Architecture
## Architecture Overview
### 1️⃣ React Frontend
Handles patient & admin interaction

Sends appointment and authorization requests

### 2️⃣ Spring Boot Backend
Manages authentication & authorization

Validates patient profiles

Processes appointment approval logic

Generates and validates JWT tokens

### 3️⃣ Database
Stores patient details

Medical profiles

Appointment history

Authorization logs

### 4️⃣ Automation Engine

Applies business rules

Verifies patient eligibility

Automatically approves/rejects appointments

## Authorization Flow
```
Patient → React UI → Spring Boot API → Profile Validation → Authorization Engine → Appointment Confirmation
```

## Methodology
### 1. Patient Registration & Profile Creation

i) Patient registers with personal and medical details

ii) Password is encrypted using BCrypt

iii) Health profile is securely stored in database

### 2. Authentication & JWT Generation

i) Patient logs in with valid credentials

ii) Spring Security authenticates the user

iii) JWT token is generated

iv) Token used for secure API access

### 3. Appointment Request & Authorization

i) Patient selects doctor/date

ii) System checks eligibility rules

iii) Automation verifies availability & profile

iv) Appointment approved or rejected automatically

### 4. Role-Based Access

Admin → Manage system & users

Doctor → View assigned appointments

Patient → Book & track appointments

## Setup Instructions
### Backend (Spring Boot)
```
mvn clean install
mvn spring-boot:run
```
### Frontend (React)
```
npm install
npm start
```
### Access Application
```
http://localhost:3000   (Frontend)
http://localhost:8080   (Backend API)
```

## Key Implementation Code
### JWT Utility
```
public String generateToken(UserDetails userDetails) {
    return Jwts.builder()
            .setSubject(userDetails.getUsername())
            .setIssuedAt(new Date())
            .setExpiration(new Date(System.currentTimeMillis() + 86400000))
            .signWith(SignatureAlgorithm.HS256, secretKey)
            .compact();
}
```
### Secure Password Encoding
```
@Bean
public PasswordEncoder passwordEncoder() {
    return new BCryptPasswordEncoder();
}
```
### Appointment Authorization Logic
```
public boolean authorizeAppointment(Patient patient) {
    return patient.isEligible() && checkSlotAvailability();
}
```

## Results

✔️ Secure patient authentication

✔️ Automated appointment approval

✔️ Reduced manual hospital workload

✔️ Fast and reliable scheduling

✔️ Protected healthcare data

✔️ Improved patient experience

The system successfully demonstrates a secure, automated, and scalable healthcare appointment authorization framework suitable for hospitals and clinics.

## Future Enhancements

🔹 AI-based patient risk prediction

🔹 SMS/Email appointment reminders

🔹 Telemedicine integration

🔹 Cloud deployment

🔹 Audit & analytics dashboard

🔹 Biometric authentication

## References

[1] Spring Security Documentation

[2] JSON Web Token (JWT) Standards

[3] RESTful Web Services Architecture

[4] Healthcare Information Security Guidelines
