# 📋 CRUD Project with Frontend

This project implements a basic CRUD (Create, Read, Update, Delete) form for managing items. The Frontend is built using HTML, CSS, and JavaScript. The components are containerized in Docker and orchestrated with Docker Compose to facilitate deployment with NGINX as a Proxy Server.

## 🗂️ Table of Contents

- [📋 CRUD Project with Frontend](#-crud-project-with-frontend)
  - [🗂️ Table of Contents](#️-table-of-contents)
  - [📖 Project Description](#-project-description)
    - [🛑 Considerations](#-considerations)
    - [📂 Project Structure](#-project-structure)
  - [✅ Requirements](#-requirements)
  - [🔧 Installation and Setup](#-installation-and-setup)
  - [🚀 Running the Project](#-running-the-project)
  - [⚙️ CI/CD and Deployment on Render](#️-cicd-and-deployment-on-render)
    - [CI Pipeline](#ci-pipeline)
    - [🌐 Deployment on Render](#-deployment-on-render)
    - [How to run the pipeline locally](#how-to-run-the-pipeline-locally)
  - [🛠️ Technologies Used](#️-technologies-used)
  - [🏗️ Architecture](#️-architecture)
  - [🤝 Contributing](#-contributing)
  - [📜 License](#-license)

## 📖 Project Description

This project allows the management of items via a basic CRUD form, where you can:

- Add a new item.
- View a list of items.
- Edit an existing item.
- Delete an item.

The data can be stored in either a JSON file or a database.

### 🛑 Considerations

- **Security**: For this test, advanced security mechanisms such as authentication or thorough data validation have not been included.

### 📂 Project Structure

```plaintext
.
├── .github
│   ├── dependabot.yml
│   └── workflows
│       ├── cd-pipeline.yml
│       └── ci-pipeline.yml
├── src/
│   ├── templates
│   │   └── index.html
│   └── static
│       ├── styles.css
│       └── script.js
├── docker-compose.yml
└── README.md

```

## ✅ Requirements

- [node](https://nodejs.org/en).
- 🐳 [Docker](https://www.docker.com/get-started).
- [Docker Compose](https://docs.docker.com/compose/).
- Git.
- [GitHub Actions](https://docs.github.com/en/actions).

## 🔧 Installation and Setup

1. Clone the frontend and backend repositories from GitHub:

    ```bash
    git clone https://github.com/omaciasd/frontend-crud.git
    git clone https://github.com/omaciasd/backend-crud.git

    ```

2. Navigate to each project folder and build the Docker images:

    ```bash
    cd ../backend-crud
    docker build -t backend .

    ```

3. Configure the required environment variables for the backend in a `.env` file.

## 🚀 Running the Project

To start the complete application using Docker Compose:

1. Navigate to the folder where the `docker-compose.yml` file is located and run:

    ```bash
    docker-compose up

    ```

2. ## 🌐 Accessing the Application

- The **frontend** will be available by NGINX as inverse proxy [http://localhost:80](http://localhost:80).

## ⚙️ CI/CD and Deployment on Render

This project uses **GitHub Actions** for Continuous Integration (CI) and **Render** for Continuous Deployment (CD).

### CI Pipeline

Every time a *push* is made to the `main` branch, the following pipeline is triggered:

1. **Unit testing**: Automated tests are run to ensure code integrity.
2. **Docker image build**: Docker images for both frontend and backend are built.
3. **Render deployment**: If all steps pass successfully, the application is deployed to **Render**.

### 🌐 Deployment on Render

The project is configured to be deployed on **Render**, which provides a managed server infrastructure for both applications (frontend and backend).

- **Frontend** is deployed as a web service accessible at [https://frontend-crud.render.com](https://frontend-crud-onyv.onrender.com).

### How to run the pipeline locally

You can test the CI pipeline locally by running:

```bash
cd backend

python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt

python3 app.py
pytest

docker-compose up --build

```

## 🛠️ Technologies Used

- **Frontend**: HTML, CSS, JavaScript.
- **DevOps**: Docker, Docker Compose.
- **CI/CD**: GitHub Actions, Render.
- **🚧 TDD**: Postman, CURL.

## 🏗️ Architecture

For detailed information on the system's architecture, including design decisions and component interactions, refer to the [Architecture Guide](./docs/guides/ARCHITECTURE.md).

## 🤝 Contributing

To contribute to this project, please check out our [Contribution Guide](./docs/guides/CONTRIBUTING.md) for instructions on setting up your development environment and the process for submitting contributions.

Describe how to contribute to the project’s documentation

## 📜 License

This project is licensed under the MIT License.
