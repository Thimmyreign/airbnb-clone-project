# airbnb-clone-project
AirBnB Clone project for ALX Prodev 

## Team Roles

This section outlines the roles within our project team and their key responsibilities. Each role contributes to ensuring the success, quality, and reliability of the project.

- **Backend Developer**  
  Responsible for designing and implementing API endpoints, database schemas, and core business logic that power the application.

- **Database Administrator (DBA)**  
  Manages the database systems, ensuring efficient design, indexing, backup, security, and optimization for performance and reliability.

- **DevOps Engineer**  
  Handles deployment pipelines, monitoring, automation, and scaling of backend services to maintain stability and availability.

- **QA Engineer**  
  Ensures backend functionalities are thoroughly tested through manual and automated testing, maintaining quality, performance, and compliance with requirements.

## Technology Stack

This project leverages modern tools and frameworks to ensure scalability, performance, and maintainability. Below is a breakdown of each technology and its role in the project:

- **Django**  
  A high-level Python web framework used to build the RESTful API and handle server-side logic.  

- **Django REST Framework (DRF)**  
  Provides powerful tools for creating, managing, and documenting RESTful APIs efficiently.  

- **PostgreSQL**  
  A robust relational database system used for reliable data storage and management.  

- **GraphQL**  
  Enables flexible and efficient querying of data, allowing clients to request only the information they need.  

- **Celery**  
  Handles asynchronous tasks such as background job processing, notifications, and scheduled tasks.  

- **Redis**  
  An in-memory data store used for caching, session management, and as a Celery message broker.  

- **Docker**  
  Provides containerization for consistent

  ## Database Design

The database is structured around five core entities: Users, Properties, Bookings, Payments, and Reviews. Below is a breakdown of each entity, its key fields, and relationships with other entities.

### Users
- **Fields:** id, name, email, password_hash, created_at  
- **Relationships:**  
  - A user can own multiple properties.  
  - A user can make multiple bookings.  
  - A user can leave multiple reviews.  

### Properties
- **Fields:** id, title, description, location, price, owner_id (FK → Users)  
- **Relationships:**  
  - A property belongs to one user (the owner).  
  - A property can have many bookings.  
  - A property can have many reviews.  

### Bookings
- **Fields:** id, user_id (FK → Users), property_id (FK → Properties), start_date, end_date, status  
- **Relationships:**  
  - A booking belongs to one user.  
  - A booking belongs to one property.  
  - A booking can have one payment.  

### Payments
- **Fields:** id, booking_id (FK → Bookings), amount, payment_date, status  
- **Relationships:**  
  - A payment is linked to one booking.  

### Reviews
- **Fields:** id, user_id (FK → Users), property_id (FK → Properties), rating, comment, created_at  
- **Relationships:**  
  - A review belongs to one user.  
  - A review belongs to one property.  

