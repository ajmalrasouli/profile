# Flask Application with Docker and GitHub Actions Demo

This repository contains a simple Flask application that is built and deployed using Docker and GitHub Actions.

## Description

This project is a demo user profile application built with Flask. It demonstrates the usage of GitHub Actions for continuous integration and continuous deployment (CI/CD) to Docker Hub.

## Features

- Simple Flask application
- Dockerized for easy deployment
- Automated CI/CD pipeline using GitHub Actions

![Profile Snippet](/static/image2.png) 

## Getting Started

### Prerequisites

- [Python 3.9](https://www.python.org/downloads/)
- [Docker](https://www.docker.com/get-started)
- [Git](https://git-scm.com/)

### Setup

1. Clone the repository:

    ```sh
    git clone https://github.com/ajmalrasouli/profile-app.git
    cd your-repo-name
    ```

2. Create a virtual environment and activate it:

    ```sh
    python3 -m venv venv
    source venv/bin/activate
    ```

3. Install the dependencies:

    ```sh
    pip install -r requirements.txt
    ```

4. Run the Flask application:

    ```sh
    flask run
    ```

    The application will be accessible at `http://127.0.0.1:5000/`.

### Docker

#### Build Docker Image

1. Build the Docker image:

    ```sh
    docker build -t your-dockerhub-username/my-flask-app:latest .
    ```

2. Run the Docker container:

    ```sh
    docker run -p 5000:5000 your-dockerhub-username/my-flask-app:latest
    ```

    The application will be accessible at `http://127.0.0.1:5000/`.

### GitHub Actions CI/CD

This repository uses GitHub Actions to build and deploy the Docker image to Docker Hub.

#### Setup GitHub Secrets

1. Go to your GitHub repository.
2. Click on `Settings` > `Secrets and variables` > `Actions`.
3. Add the following secrets:
    - `DOCKER_USERNAME`: Your Docker Hub username.
    - `DOCKER_PASSWORD`: Your Docker Hub password.

#### GitHub Actions Workflow

The workflow file is located at `.github/workflows/deploy-to-dockerhub.yml`. It triggers on every push to the `main` branch and performs the following steps:

1. Checks out the repository code.
2. Sets up Docker Buildx.
3. Logs in to Docker Hub.
4. Builds and pushes the Docker image to Docker Hub.
5. Logs out from Docker Hub.

## Repository Structure

```plaintext
/project-directory
    /static
        profile.jpg
        styles.css
    /templates
        index.html
    .github
        /workflows
            deploy-to-dockerhub.yml
    app.py
    Dockerfile
    requirements.txt
    README.md



## Acknowledgments

- [Flask](https://flask.palletsprojects.com/)
- [Docker](https://www.docker.com/)
- [GitHub Actions](https://github.com/features/actions)
