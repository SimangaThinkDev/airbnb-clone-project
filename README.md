# Airbnb Clone Project
The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security

## Project Goals

- Build a robust backend system to handle user authentication, listings, bookings, and payments.
- Design and manage a relational database to store application data efficiently.
- Develop secure and well-documented RESTful and/or GraphQL APIs.
- Practice collaborative development using GitHub workflows and version control.
- Implement CI/CD pipelines for automated testing and deployment.
- Integrate security best practices and scalable design principles.

## Tech Stack

- Backend Framework: Django
- Database: MySQL
- API Design: Django REST Framework and GraphQL
- Version Control & Collaboration: Git, GitHub
- CI/CD: GitHub Actions, Docker
- Containerization: Docker
- Documentation: Markdown (README.md)

## Team Roles

### Backend Developer(Me)
Responsibilities:
- Develop and maintain the application’s core logic using Django.
- Implement RESTful and GraphQL APIs for features like user authentication, listings, and bookings.
- Ensure code quality, scalability, and adherence to security best practices.

### Database Administrator
Responsibilities:
- Design and optimize the MySQL database schema to support application features.
- Manage data integrity, indexing, migrations, and performance tuning.
- Ensure backup, recovery, and security of database systems.

### Security Engineer
Responsibilities:
- Implement secure authentication and authorization mechanisms.
- Conduct security audits and apply best practices (e.g., preventing SQL injection, XSS).
- Manage secure API access and data protection protocols.

### DevOps Engineer
Responsibilities:
- Set up and manage CI/CD pipelines using GitHub Actions.
- Containerize the application using Docker and orchestrate deployments.
- Monitor infrastructure performance and automate deployment workflows.

###  Documentation Specialist
Responsibilities:
- Maintain clear, concise project documentation (e.g., README.md, API docs).
- Ensure onboarding materials, system design diagrams, and endpoint references are updated.
- Use tools like Markdown and Swagger for structured technical documentation.


## Database Design

### 1. User
Represents people using the platform (guests and hosts).

Important Fields:

- id: Unique identifier
- name: Full name
- email: Unique user email
- password_hash: Securely stored password
- is_host: Boolean flag indicating if user is a host

Relationships:

- A user can create multiple properties (if they are a host).
- A user can make multiple bookings (as a guest).
- A user can write multiple reviews.

### 2. Property

Represents a listing (home, apartment, room, etc.) available for booking.

Important Fields:
- id: Unique identifier
- title: Name or headline of the property
- description: Detailed description
- location: Address or coordinates
- price_per_night: Cost to book for one night

Relationships:

- A property belongs to one user (host).
- A property can have many bookings.
- A property can have many reviews.

### 3. Booking

Represents a reservation made by a user for a specific property.

Important Fields:

- id: Unique identifier
- user_id: ID of the guest who made the booking
- property_id: ID of the booked property
- start_date: Booking start date
- end_date: Booking end date

Relationships:

- A booking belongs to one user.
- A booking belongs to one property.
- A booking may have one payment record.

### 4. Review

Represents feedback given by a user after a stay.

Important Fields:

- id: Unique identifier
- user_id: Author of the review
- property_id: Reviewed property
- rating: Numerical score (e.g., 1–5)
- comment: Written feedback

Relationships:

- A review belongs to one user.
- A review belongs to one property.

### 5. Payment

Represents the transaction for a booking.

Important Fields:

- id: Unique identifier
- booking_id: Associated booking
- amount: Total amount paid
- payment_method: (e.g., credit card, PayPal)
- status: (e.g., pending, completed, failed)

Relationships:

- A payment belongs to one booking.

#### Summary of Relationships
TODO: Summarize the relationships in this database, me

## Feature Breakdown

1. User Management:

   Handles user registration, login, and profile management. It ensures users can securely access the platform as guests or   hosts, and manage their account details.

3. Property Management:

    Allows hosts to list, update, and remove properties. This feature is key to building the marketplace by letting users share available spaces for rent.

4. Booking System:

    Enables guests to view property availability and make reservations. It manages booking dates and ensures properties can’t be double-booked.

5. Review System:

    Lets guests leave ratings and comments after staying at a property. This helps improve trust and decision-making for future users.

5. Payment Processing:

    Handles the payment for bookings. It ensures secure and accurate transactions between guests and hosts.

6. Authentication and Authorization:

    Protects user data and actions through secure login and role-based access. Only authorized users can perform certain actions (e.g., only hosts can list properties).

7. API Access (REST & GraphQL):

    Provides endpoints for interacting with the system programmatically. This supports integration with frontend apps or external services.

8. CI/CD Integration:

    Uses GitHub Actions and Docker for testing and deployment automation. This ensures updates are safely and efficiently pushed to production.
