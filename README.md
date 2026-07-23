# 🚀 FastAPI Calculator with Secure User Authentication

This project extends a FastAPI calculator application by implementing a secure user management system using SQLAlchemy, Pydantic, PostgreSQL, and bcrypt password hashing.

The application includes user registration, authentication, password verification, database persistence, automated testing, Docker containerization, and a complete CI/CD pipeline using GitHub Actions.

---

# ✨ Features

* FastAPI web application
* SQLAlchemy User model with database persistence
* Unique username and email constraints
* Secure password hashing and verification using bcrypt
* Pydantic schemas for request validation and response serialization
* PostgreSQL database integration
* Unit, integration, and end-to-end testing
* Playwright browser testing
* Docker containerization
* Docker Compose development environment
* GitHub Actions CI/CD pipeline
* Docker Hub deployment
* Trivy security scanning

---

# 📁 Project Structure

```
.
├── app/
│   ├── auth/              # Authentication dependencies
│   ├── models/            # SQLAlchemy database models
│   └── schemas/           # Pydantic schemas
│
├── tests/
│   ├── unit/              # Unit tests
│   ├── integration/        # Database and authentication tests
│   └── e2e/               # End-to-end browser tests
│
├── .github/
│   └── workflows/          # GitHub Actions CI/CD workflow
│
├── docker-compose.yml      # FastAPI + PostgreSQL environment
├── Dockerfile
├── requirements.txt
└── main.py
```

---

# 🛠️ Local Setup

## Install Python 3.10+

Verify Python installation:

```bash
python --version
```

---

## Create and Activate Virtual Environment

Create the environment:

```bash
python -m venv venv
```

Activate:

### Linux / Mac

```bash
source venv/bin/activate
```

### Windows

```bash
venv\Scripts\activate
```

---

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🐘 Database Setup

This project uses PostgreSQL.

The included Docker Compose file starts:

* FastAPI application
* PostgreSQL database
* pgAdmin database interface

Start the application stack:

```bash
docker compose up --build
```

The application will be available at:

```
http://localhost:8000
```

pgAdmin will be available at:

```
http://localhost:5050
```

---

# 🧪 Running Tests Locally

Make sure your virtual environment is activated:

```bash
source venv/bin/activate
```

Run the complete test suite:

```bash
pytest
```

Run individual test categories:

### Unit Tests

```bash
pytest tests/unit/
```

### Integration Tests

```bash
pytest tests/integration/
```

### End-to-End Tests

```bash
pytest tests/e2e/
```

The integration tests use PostgreSQL, and the CI pipeline automatically creates a PostgreSQL service container during GitHub Actions runs.

---

# 🐳 Docker Usage

## Build Docker Image

```bash
docker build -t fastapi-calculator .
```

## Run Docker Container

```bash
docker run -p 8000:8000 fastapi-calculator
```

For local development with PostgreSQL, use Docker Compose:

```bash
docker compose up --build
```

---

# 🐳 Docker Hub Repository

The Docker image for this project is available on Docker Hub:

https://hub.docker.com/r/colinsherman/601_module9

Pull the latest image:

```bash
docker pull colinsherman/601_module9:latest
```

---

# ⚙️ Continuous Integration / Continuous Deployment

This project uses GitHub Actions to automate:

* Dependency installation
* Unit testing
* Integration testing
* End-to-end testing
* PostgreSQL test database setup
* Docker image building
* Security scanning with Trivy
* Docker Hub deployment

The deployment workflow runs after successful tests and security checks.

---

# 🔐 Security Implementation

The application implements secure authentication practices including:

* Password hashing with bcrypt
* Password verification against stored hashes
* JWT token generation and validation
* Pydantic input validation
* Database uniqueness constraints for usernames and emails

Plain-text passwords are never stored in the database.

---

# 📦 Submission Information

Repository:

```
<your GitHub repository link>
```

Docker Hub:

```
https://hub.docker.com/r/colinsherman/601_module9
```

---

# Useful Commands

| Action                   | Command                                            |
| ------------------------ | -------------------------------------------------- |
| Activate environment     | `source venv/bin/activate`                         |
| Install packages         | `pip install -r requirements.txt`                  |
| Run tests                | `pytest`                                           |
| Start Docker environment | `docker compose up --build`                        |
| Build image              | `docker build -t fastapi-calculator .`             |
| Push Git changes         | `git add . && git commit -m "message" && git push` |

---

# 📋 Notes

* Python 3.10+ is recommended.
* Docker Desktop should be running before using Docker commands.
* PostgreSQL is required for integration testing.
* GitHub Actions automatically validates the project before deployment.
