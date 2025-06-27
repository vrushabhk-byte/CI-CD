# Flask CI/CD Pipeline with Jenkins and Docker

This project demonstrates a full CI/CD pipeline for a simple Flask web application using:
- Jenkins
- Docker
- GitHub
- Pytest (for unit tests)

## 💻 Project Structure
- `app/`: Flask source code
- `tests/`: Unit tests with pytest
- `Dockerfile`: Containerization
- `Jenkinsfile`: CI/CD Pipeline definition
- `requirements.txt`: Python dependencies

## 🛠️ Pipeline Stages
1. Clone code from GitHub
2. Install dependencies
3. Run unit tests with Pytest
4. Build Docker image
5. Push image to Docker Hub
6. (Optional) Deploy to server or Kubernetes

## 🧪 Run Locally

```bash
pip install -r requirements.txt
python app/app.py
