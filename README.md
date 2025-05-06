Sample Python App with CI/CD Pipeline

This is a simple python web application with a basic CI/CD pipeline using **GitHub Actions**, **Docker**, and **DockerHub**.

---
Features

- Lightweight Flask web app
- Unit testing with `pytest`
- Linting with `flake8`
- Dockerized with `Dockerfile`
- CI/CD pipeline using GitHub Actions
- Docker image pushed to DockerHub
- Optional manual approval and rollback logic for production deployment

---

**## 🧪 Running Locally

### 1. Clone the Repository**

```bash
git clone https://github.com/your-username/sample-flask-cicd.git
cd sample-flask-cicd

2. **Install Dependencies**
pip install -r requirements.txt

3. Run Tests
pytest

4. Run the Application
python app/main.py

5.Build Docker Image
docker build -t sample-flask-app .

6.Run Docker Container
docker run -p 5000:5000 sample-flask-app

**CI/CD with GitHub Actions**

This project uses GitHub Actions to:

Run tests and linter on every push to main

Build a Docker image

Push it to DockerHub

(Optional) Deploy to a production environment with manual approval


**Secrets Required**

Set the following secrets in your GitHub repository:

DOCKERHUB_USERNAME – Your DockerHub username


DOCKERHUB_PASSWORD – Your DockerHub password or access token

**Rollback Strategy**

Before each deployment, the previous Docker image is tagged as previous. In case of a failure, the deployment workflow can roll back to the last stable version.


.
├── app/
│   └── main.py
├── tests/
│   └── test_main.py
├── Dockerfile
├── requirements.txt
├── .github/
│   └── workflows/
│       └── ci-cd.yaml
└── README.md

