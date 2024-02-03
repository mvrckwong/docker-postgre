# Docker Compose for PostgreSQL

This project simplifies the setup of PostgreSQL and pgAdmin within Docker containers, making it easier to manage databases through a web interface. By utilizing Docker and docker-compose, we can create isolated environments for our database server (PostgreSQL) and database management interface (pgAdmin), ensuring that our setup is easily reproducible and portable. This setup is ideal for development, testing, and production environments, providing a straightforward method to spin up database services.

## Getting Started
To get your local environment set up with this project, follow these instructions. The process involves installing necessary software, cloning the repository, and configuring the environment.

### Prerequisites
Before you begin, you'll need to have Docker installed on your machine. Docker will manage the creation and running of the containers for PostgreSQL and pgAdmin. Additionally, you'll need docker-compose to orchestrate the containers based on the docker-compose.yml file provided in this project.

- Docker: Follow the installation guide for your operating system on the Docker website.
- Docker Compose: Usually included with Docker Desktop for Windows and Mac. For Linux, follow the installation instructions on the Docker Compose website.

### Installation
1. **Environment Variables:** Before starting, you'll need to create an `.env` file in the `/environment` directory. This file should contain the necessary environment variables:
    ```
    POSTGRES_DB=your_db_name
    POSTGRES_USER=your_username
    POSTGRES_PASSWORD=your_password
    PGADMIN_DEFAULT_EMAIL=your_email
    PGADMIN_DEFAULT_PASSWORD=your_pgadmin_password
    ```
   Replace the placeholders with your desired values.

2. **Clone the Repository:** Clone this project's repository to your local machine:
    ```sh
    git clone https://github.com/your_username/Project-Name.git
    ```

3. **Launch the Services:** Navigate to the directory containing the `docker-compose.yml` file and launch the services:
    ```sh
    docker-compose up -d
    ```
   This command will download the required Docker images (if not already present), create the containers, and start the PostgreSQL and pgAdmin services.

4. **Access pgAdmin:** Once the containers are running, you can access pgAdmin by navigating to `http://localhost:5050` in your web browser. Log in using the `PGADMIN_DEFAULT_EMAIL` and `PGADMIN_DEFAULT_PASSWORD` you set in your `.env` file.

5. **Connect to PostgreSQL:** Within pgAdmin, create a new server connection to PostgreSQL. Use `postgres` as the host name (the service name defined in `docker-compose.yml`), and enter the `POSTGRES_USER` and `POSTGRES_PASSWORD` from your `.env` file.
