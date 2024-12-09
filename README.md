# EmPowerFlow
Doing POC with standard version java 17 along with spring security 6 and Spring Boot 3


**Empower**: Highlights the idea of enabling and strengthening HR teams, employees, and organizations. It implies giving them the tools and capabilities to take control of their HR processes and make informed decisions.

**Flow**: Represents seamless, efficient, and streamlined operations. It conveys the notion of smooth workflows, ensuring HR tasks and processes are conducted without interruptions or bottlenecks.
Together, EmpowerFlow suggests a solution that empowers organizations with efficient, hassle-free HR management systems, promoting productivity and ease of use in managing human resources.



# Spring Boot JWT Authentication example with Spring Security & Spring Data JPA

## User Registration, User Login and Authorization process.
The diagram shows flow of how we implement User Registration, User Login and Authorization process.

<img width="551" alt="image" src="https://github.com/user-attachments/assets/d94639aa-3004-4fab-be4b-2a648c5386ea">

## Spring Boot Server Architecture with Spring Security
You can have an overview of our Spring Boot Server with the diagram below:

<img width="525" alt="image" src="https://github.com/user-attachments/assets/9ab26a15-8389-4590-84bd-320a4104b38d">

**Scripts**:


CREATE TABLE users (
    id BIGSERIAL PRIMARY KEY,
    username VARCHAR(20) NOT NULL UNIQUE,
    email VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(120) NOT NULL
);

CREATE TABLE user_roles (
    user_id BIGINT NOT NULL,
    role_id INT NOT NULL,
    PRIMARY KEY (user_id, role_id),
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
    FOREIGN KEY (role_id) REFERENCES roles(id) ON DELETE CASCADE
);

CREATE TABLE roles (
    id SERIAL PRIMARY KEY,
    name VARCHAR(20) NOT NULL
);

INSERT INTO roles(name) VALUES('ROLE_USER');

INSERT INTO roles(name) VALUES('ROLE_ADMIN');




