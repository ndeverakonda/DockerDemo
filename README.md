# Docker Compose Local Database Setup

This project includes a **Docker Compose configuration** that runs a PostgreSQL database locally.
Using Docker ensures the database environment is consistent and easy to reproduce on any machine without installing PostgreSQL directly on the host system.

---

## Prerequisites

Before running the database container, make sure the following tools are installed:

* Docker
* Docker Compose

You can verify the installation with:

```bash
docker --version
docker compose version
```

---

## Project Files

The setup uses the following files:

* `compose.yaml` – Docker Compose manifest for running PostgreSQL
* `.env` – configuration file for database credentials and settings

---

## Configuration

Create a `.env` file in the project root directory with the following variables:

```env
DB_PORT=5432
DB_NAME=mydatabase
DB_USER=myuser
DB_PASSWORD=mypassword
```

These environment variables are used by Docker Compose to configure the PostgreSQL container.

---

## Start the Database

Run the following command in the project directory:

```bash
docker compose up -d
```

This command will:

* Pull the PostgreSQL image (if not already available)
* Create the container
* Start the database in detached mode

---

## Verify the Container is Running

To check if the container started successfully:

```bash
docker compose ps
```

You should see the PostgreSQL container listed with the **running** status.

---

## Connecting to the Database

You can connect to the database using any database client such as **DBeaver**, **DataGrip**, or **psql** with the following settings:

| Parameter | Value      |
| --------- | ---------- |
| Host      | localhost  |
| Port      | 5432       |
| Database  | mydatabase |
| Username  | myuser     |
| Password  | mypassword |

---

## Stop the Database

To stop the container:

```bash
docker compose down
```

---

## Remove Database and Stored Data

If you want to remove the container and delete the database data volume:

```bash
docker compose down -v
```

---

## Data Persistence

The PostgreSQL container uses a **Docker volume** to store database data.
This ensures that the data is preserved even if the container is stopped or recreated.

---

## Summary

Using Docker Compose for the local database provides several advantages:

* No manual PostgreSQL installation required
* Reproducible environment across machines
* Easy startup and shutdown of the database
* Persistent database storage using Docker volumes
