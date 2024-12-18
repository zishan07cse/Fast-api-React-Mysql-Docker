﻿# Fast-api-React-Mysql-Docker
 # Docker Compose Setup for Full-Stack Application

This project sets up a full-stack application with a MySQL database, a FastAPI backend, and a frontend. Each component runs in a separate Docker container, allowing for isolated development and seamless communication between services.

## Project Structure

The project contains three main services:

1. **Database**: A MySQL container that serves as the application's database.
2. **Backend**: A FastAPI application that interacts with the database and serves API endpoints.
3. **Frontend**: A frontend application that communicates with the backend API.

## Services

### Database

- **Image**: Built from the Dockerfile in the `./sql` directory.
- **Port**: Exposes port `3306` for MySQL access.
- **Environment Variables**:
  - `MYSQL_ROOT_PASSWORD`: Set to `root` (adjust as needed).
  - `MYSQL_DATABASE`: Name of the database, set to `my_database` by default.

### Backend

- **Image**: Built from the Dockerfile in the `./backend` directory.
- **Port**: Exposes port `8000`.
- **Dependency**: Depends on the `database` service to ensure the database is ready before the backend starts.

### Frontend

- **Image**: Built from the Dockerfile in the `./frontend` directory.
- **Port**: Exposes port `3000`.
- **Dependency**: Depends on the `backend` service to ensure the backend is ready before the frontend starts.

## Usage

1. Ensure Docker and Docker Compose are installed.
2. Clone this repository and navigate to the root directory.
3. Run the following command to start all services:

   ```bash
   docker-compose up --build

