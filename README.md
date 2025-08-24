# 🏡 Airbnb Clone Project (Backend)

## 📌 Project Overview
This is a backend-focused Airbnb Clone project.  
The goal is to design and simulate a robust booking platform that includes:  
- Backend architecture with Django.  
- Relational database design with MySQL.  
- Secure API development.  
- CI/CD pipeline integration.  

---

## 👥 Team Roles
- **Backend Developer**: Implements the core backend logic, APIs, and integrations.  
- **Database Administrator (DBA)**: Designs, manages, and optimizes the database schema.  
- **DevOps Engineer**: Sets up CI/CD pipelines, manages Docker, and deployment.  
- **Security Engineer**: Ensures API security, authentication, and authorization.  
- **Project Manager**: Coordinates tasks, ensures milestones are delivered on time.  

---

## 🛠️ Technology Stack
- **Django** → Backend web framework to build APIs.  
- **MySQL** → Relational database for storing users, bookings, and properties.  
- **GraphQL** → Alternative query language for flexible data fetching.  
- **Docker** → Containerization for consistent environment setup.  
- **GitHub Actions** → CI/CD automation for testing and deployment.  

---

## 🗄️ Database Design
**Entities & Key Fields:**  
- **User** → `id`, `name`, `email`, `password_hash`  
- **Property** → `id`, `title`, `location`, `price_per_night`, `owner_id`  
- **Booking** → `id`, `user_id`, `property_id`, `start_date`, `end_date`  
- **Review** → `id`, `user_id`, `property_id`, `rating`, `comment`  
- **Payment** → `id`, `user_id`, `booking_id`, `amount`, `status`  

**Relationships:**  
- A **User** can own many **Properties**.  
- A **Property** can have many **Bookings**.  
- A **Booking** belongs to one **User** and one **Property**.  
- A **Review** is linked to a **User** and a **Property**.  
- A **Payment** is linked to a **User** and a **Booking**.  

---

## 📋 Feature Breakdown
- **User Management** → Signup, login, profile management.  
- **Property Management** → Add, edit, and list properties.  
- **Booking System** → Users can book properties for given dates.  
- **Reviews & Ratings** → Users can review properties.  
- **Payment Processing** → Secure payments for bookings.  

---

## 🔒 API Security
- **Authentication** → JWT-based or OAuth2 login.  
- **Authorization** → Role-based access (e.g., admin vs. user).  
- **Rate Limiting** → Prevent abuse by limiting requests per user.  
- **Data Validation** → Input sanitization to prevent SQL injection/XSS.  
- **Secure Payments** → Encrypted payment processing (HTTPS, PCI compliance).  

---

## ⚙️ CI/CD Pipeline
- **Continuous Integration (CI)**: Every push triggers automated tests.  
- **Continuous Deployment (CD)**: If tests pass, code is built and deployed automatically.  
- **Tools**: GitHub Actions + Docker + Deployment to AWS/Heroku.  

---

## ✅ Ready for Review
This project is part of the **ProDev Backend Journey**.  
