#  Containerized 3-Tier Web App with Docker Compose

A simple **3-Tier Web Application** deployed using **Docker Compose**, demonstrating how frontend, backend, and database services communicate within a containerized environment.

---

## Overview

Modern applications are commonly built using a **3-Tier Architecture** to improve scalability, security, and maintainability. This project deploys:

| Tier | Technology | Responsibility |
|------|-----------|----------------|
| **Frontend (Web Layer)** | Nginx + HTML | Serves the signup form |
| **Application (App Layer)** | PHP | Processes form submissions |
| **Database (DB Layer)** | MySQL | Stores user data |

---

##  Architecture


<img width="1100" height="733" alt="image" src="https://github.com/user-attachments/assets/db031488-ebb6-4d5c-8ad3-cabd78a8aae4" />


---

##  Project Structure

```
three-tier/
│
├── app/
│   └── code/
│       └── submit.php          # PHP backend logic
│
├── db/
│   ├── Dockerfile              # MySQL custom image
│   └── init.sql                # DB & table initialization
│
├── web/
│   ├── code/
│   │   └── signup.html         # Frontend signup form
│   └── config/
│       └── default.conf        # Nginx configuration
│
└── docker-compose.yml          # Multi-container orchestration
```

---

##  Technologies Used

-  **Docker** — Containerization platform
-  **Docker Compose** — Multi-container management
   **Nginx** — Web server for the frontend
-  **PHP** — Backend scripting language
-  **MySQL** — Relational database
-  **HTML** — Frontend signup form
-  **Docker Network** — Inter-container communication

---

## Getting Started

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/) installed
- [Docker Compose](https://docs.docker.com/compose/install/) installed

### Run the Application

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/three-tier-docker.git
   cd three-tier-docker
   ```

2. **Build and start all containers**
   ```bash
   docker-compose up -d
   ```

3. **Verify containers are running**
   ```bash
   docker ps
   ```

4. **Open the app in your browser**
   ```
   http://localhost
   ```

---

##  Testing the Application

1. Open `http://localhost` in your browser
2. Fill in the **Name** and **Email** fields
3. Click **Register**
4. You should see a **"Registration Successful"** message

### Verify Database Entries

```bash
# Access the MySQL container
docker exec -it db-tier bash

# Login to MySQL
mysql -u root -p
# Password: root123

# Query the stored data
USE userdata;
SELECT * FROM users;
```

---

## Stopping the Application

```bash
docker-compose down
```

To remove volumes as well:
```bash
docker-compose down -v
```

---

##  Key Features

-  Multi-container deployment with Docker Compose
-  Clean 3-tier architecture separation
-  Automated database and table initialization
-  Container networking for secure inter-service communication
-  Scalable and extensible architecture

---

## Use Cases

This architecture pattern is widely used in:
- Enterprise web applications
- Cloud-native deployments
- Microservices environments
- DevOps CI/CD workflows

---
## summary

A simple 3-Tier Web Application deployed using Docker Compose, where the frontend, backend, and database run in separate containers and communicate seamlessly within a containerized 
environment. This project demonstrates multi-container architecture, service networking, and scalable deployment using Docker.


