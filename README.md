## Local Database Setup with Docker Compose

This project provides a Docker Compose configuration for running a local PostgreSQL database.

### Prerequisites
- Docker installed
- Docker Compose available

### Files
- `docker-compose.yml` - defines the PostgreSQL container
- `.env` - stores configurable and sensitive values

### Configuration
Create a `.env` file in the project root using the following structure:

```env
DB_NAME=mydatabase
DB_USER=myuser
DB_PASSWORD=mypassword
DB_PORT=5433