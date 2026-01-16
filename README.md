# Dockerized Three-Tier Web Application :

##  Project Overview -
This project demonstrates a Dockerized Three-Tier Web Application deployed using Docker Compose.  
The application is hosted on an AWS EC2 instance and follows a standard industry-level architecture.

**The project includes:** :
- Web Layer (Nginx) – Serves the signup form
- Application Layer (PHP-FPM) – Processes form submission
- Database Layer (MySQL) – Stores user data
- Docker Compose – Orchestrates containers and networking

##  Project Architecture:
![](/img/architecture.png)

**Flow :**
*User → Nginx (Web) → PHP-FPM (App) → MySQL (DB)*
---

##  Project Directory Structure :

```
threetier/
├── web/
│   ├── code/
│   │   └── signup.html
│   └── config/
│       └── default.conf
│
├── app/
│   └── code/
│       └── submit.php
│
├── db/
│   ├── Dockerfile
│   └── init.sql
│
└── docker-compose.yml
```
---

##  Tools & Technologies :

| Tool / Technology | Purpose |
|-------------------|--------|
| Docker | Containerization |
| Docker Compose | Multi-container orchestration |
| Nginx | Web server |
| PHP-FPM | Backend processing |
| MySQL | Database |
| AWS EC2 | Cloud hosting |

---

##  Docker Configuration Details :
- MySQL database initialized using Dockerfile and init.sql
- Separate Docker networks for web and database layers
- Persistent volume used for MySQL data
- Container dependency managed using depends_on

---

##  Database Details :
- Database Name: FCT
- Table Name: users
- Columns: id, name, email, website, comment, gender

---

##  Step-by-Step Implementation :


| Step | Description | Command / Action | Screenshot |
|-----|------------|----------------|-----------|
| 1 | Create project directories | mkdir web app db | ![](./img/project-directory-structure.png) |
| 2 | Start Nginx container | docker run -d nginx | ![](./img/nginx-container-running.png) |
| 3 | Configure app and DB files | HTML, PHP, SQL setup | — |
| 4 | Run Docker Compose | docker compose up -d |  —  |
| 5 | Verify running containers | docker ps | ![](./img/containers-status.png) |
| 6 | Open signup form | http://<EC2-IP>/signup.html | ![](./img/signup-form.png)|
| 7 | Submit form | Fill and submit form | ![](./img/form-submission.png) |
| 8 | Verify DB entry | SELECT * FROM users; | ![](./img/mysql-db-record.png) |



##  Learning Outcomes :

| Concept | Description |
|-------|-------------|
| Docker Containers | Created and managed containers |
| Docker Compose | Orchestrated multi-container application |
| Three-Tier Architecture | Implemented web, app, and DB separation |
| PHP & MySQL Integration | Stored form data into database |
| Docker Networking | Used multiple Docker networks |
| AWS EC2 | Deployed application on cloud server |

---

## Screenshots/Outputs :

 ![](/img/Output.png)
 ![](/img/data_insert.png)

##  Conclusion :
This project provides hands-on experience with real-world Docker-based deployment using a three-tier architecture.  
It demonstrates container orchestration, networking, persistent storage, and cloud deployment using AWS EC2.

---
