# Docker Configuration Files

This project includes various **Docker Compose** files to set up a **full-stack application** consisting of a **Next.js frontend**, a **Node.js backend**, **MongoDB**, and **Redis**.

## Docker Files and What They Do

### 1. `frontend.yml`

- **Purpose**: Sets up and runs the **Next.js frontend** in a Docker container.
- **Key Features**:
  - Exposes the frontend on port `3000`.
  - Passes required environment variables to the frontend.

### 2. `backend.yml`

- **Purpose**: Sets up and runs the **Node.js backend** in a Docker container.
- **Key Features**:
  - Exposes the backend on port `3002`.
  - Connects to **MongoDB** and **Redis**.
  - Passes environment variables like MongoDB URI, Redis URL, SMTP settings, etc.

### 3. `samenetwork_mongo.yml`

- **Purpose**: Runs **Frontend**, **Backend**, and **MongoDB** on the **same Docker network**.
- **Key Features**:
  - Ensures all services (frontend, backend, MongoDB) can communicate with each other by being on the same network.
  - Runs **MongoDB** for the backend.

### 4. `redis.yml`

- **Purpose**: Sets up and runs **Redis** in a Docker container.
- **Key Features**:
  - Exposes Redis on port `6379`.
  - Optionally persists Redis data with Docker volumes.

## How to Use

1. **Start Redis**:

   ```bash
      docker-compose -f redis.yml up -d
   ```

2.**Start the Frontend, Backend, and MongoDB Services:**

   ```bash
    docker-compose -f samenetwork_mongo.yml up -d
   ```

3.**Start the Backend:**

  ```bash
docker-compose -f backend.yml up -d
 ```

4.**Start the Frontend:**

  ```bash
docker-compose -f frontend.yml up -d
   ```
