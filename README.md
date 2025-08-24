# Airbnb Clone Project

## Project Overview
This project is a full-stack web application clone of Airbnb, built as part of the ALX Software Engineering program. The goal is to create a platform where users can browse properties, make bookings, and manage their listings, applying core software engineering principles including database design, API development, security, and deployment.

**Tech Stack:** Python, Django, Django REST Framework, PostgreSQL, GraphQL, JWT, Docker, Nginx, React (for front-end, out of backend scope)

## Team Roles and Responsibilities

*   **Backend Developer:** Responsible for developing the server-side logic, designing and implementing RESTful/GraphQL APIs, integrating with the database, and ensuring application performance and responsiveness.
*   **Database Administrator (DBA):** Designs the database schema, optimizes queries for performance, ensures data integrity and security, and manages database migrations.
*   **DevOps Engineer:** Sets up and maintains the CI/CD pipeline, containerizes the application using Docker, manages cloud infrastructure (e.g., AWS, GCP), and ensures high availability and scalability.
*   **Quality Assurance (QA) Engineer:** Develops test plans, writes and executes automated tests (unit, integration, end-to-end), and performs manual testing to identify bugs and ensure product quality.
*   **Project Manager/Scrum Master:** Facilitates agile ceremonies (sprint planning, standups, retrospectives), removes impediments for the team, and ensures project goals and deadlines are met.

## Technology Stack Overview

*   **Django & Django REST Framework:** The primary Python web framework used to build the backend logic and RESTful APIs. It provides security, ORM, and a structured architecture out-of-the-box.
*   **PostgreSQL:** A powerful, open-source relational database system chosen for its reliability, robust feature set, and ability to handle complex queries and relationships efficiently.
*   **GraphQL:** Used as an alternative to REST for more efficient data fetching, allowing clients to request exactly the data they need, reducing over-fetching and under-fetching.
*   **JWT (JSON Web Tokens):** The chosen method for stateless user authentication. Securely transmits user information between the client and server.
*   **Docker:** Used to containerize the application, ensuring consistent environments across development, testing, and production stages.
*   **Nginx:** A high-performance web server that will act as a reverse proxy for our Django application, handling static files and load balancing.

## Database Design Overview

*   **Users**
    *   Fields: `id`, `username`, `email`, `password_hash`, `profile_picture`, `phone_number`
    *   Relations: A User can have many Properties, Bookings, and Reviews.

*   **Properties**
    *   Fields: `id`, `title`, `description`, `price_per_night`, `location`, `host_id` (FK to Users)
    *   Relations: A Property belongs to one User (host). A Property can have many Bookings and Reviews.

*   **Bookings**
    *   Fields: `id`, `start_date`, `end_date`, `total_price`, `guest_id` (FK to Users), `property_id` (FK to Properties)
    *   Relations: A Booking belongs to one User (guest) and one Property.

*   **Reviews**
    *   Fields: `id`, `rating`, `comment`, `created_at`, `user_id` (FK to Users), `property_id` (FK to Properties)
    *   Relations: A Review belongs to one User and one Property.

*   **Payments**
    *   Fields: `id`, `amount`, `status`, `stripe_payment_intent_id`, `booking_id` (FK to Bookings)
    *   Relations: A Payment belongs to one Booking.

## Feature Breakdown

*   **User Management:** Allows users to register, log in, view, and update their profiles. This is the foundation for personalization and security on the platform.
*   **Property Management:** Enables hosts to create, read, update, and delete property listings. This feature populates the platform with bookable content.
*   **Booking System:** The core functionality that allows guests to search for properties, check availability, and reserve them for specific dates. It directly facilitates transactions.
*   **Review & Rating System:** Allows guests to leave feedback and ratings for properties they've booked, building trust and community quality control.
*   **Payment Processing:** Integrates with a payment gateway (e.g., Stripe) to securely handle financial transactions for bookings, which is critical for a commercial platform.

## API Security Overview

*   **Authentication (JWT):** Verifies the identity of users accessing the API. This is crucial to ensure that only legitimate users can perform actions like making bookings or managing properties.
*   **Authorization (Role-Based Access Control - RBAC):** Controls what authenticated users are allowed to do (e.g., only a property's host can edit it). This protects data from unauthorized modifications.
*   **Data Validation & Sanitization:** Ensures all incoming data is correct and safe, preventing common vulnerabilities like SQL Injection and Cross-Site Scripting (XSS).
*   **Rate Limiting:** Protects the API from abuse and Denial-of-Service (DoS) attacks by limiting how many requests a user can make in a given time window.
*   **HTTPS:** Encrypts all data in transit between the client and server, protecting sensitive information like passwords and payment details from eavesdroppers.

## CI/CD Pipeline Overview

A CI/CD (Continuous Integration/Continuous Deployment) pipeline automates the steps from code commit to production deployment.

*   **Why it's important:** It enables frequent and reliable code releases, automates testing to catch bugs early, and reduces manual errors, leading to a more stable and agile development process.
*   **Tools:** For this project, we will use **GitHub Actions** for CI to automatically run tests on every pull request. For CD, we will use **Docker** to create container images and a tool like **AWS CodeDeploy** or a simple script to deploy the container to a production server.
# airbnb-clone-project
