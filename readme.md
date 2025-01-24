![alt text](image.png)

# Prisma with PostgreSQL

This project demonstrates the use of **Node.js**, **Express.js**, **Prisma**, and **PostgreSQL** for building a backend service. It also uses **Docker** for containerization to simplify the setup and deployment process.

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (v14 or higher)
- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Features

- **Express.js**: A minimalist web framework for building APIs.
- **Prisma**: A modern ORM (Object Relational Mapper) for database management.
- **PostgreSQL**: A powerful, open-source relational database.
- **Docker**: Containerized environment for consistent development and deployment.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/THEYASHGAUR/prisma-with-postgres.git
cd prisma-with-postgres
```

### 2. Install Dependencies
Install the required Node.js packages:
```bash
npm install
```

### 3. Environment Variables

Create a `.env` file in the root directory and add the following:
```env
DATABASE_URL="postgresql://postgres:password@localhost:5432/mydatabase"
```
Replace `password` and `mydatabase` with your PostgreSQL password and database name.

### 4. Run Docker Containers

Use Docker to set up PostgreSQL and Prisma Studio. Run the following commands:

#### Build the Docker image:
```bash
docker-compose build
```

#### Start the containers:
```bash
docker-compose up
```

The PostgreSQL database will be available at `localhost:5432`.

#### Stop the containers:
```bash
docker-compose down
```

### 5. Prisma Setup

#### Initialize Prisma:
```bash
npx prisma init
```

This will create a `prisma` folder with `schema.prisma` inside.

#### Generate Prisma Client:
```bash
npx prisma generate
```

#### Run Migrations:
Create a migration to set up your database schema:
```bash
npx prisma migrate dev --name init
```

#### Open Prisma Studio:
To interact with your database visually, use:
```bash
npx prisma studio
```

### 6. Start the Server

Run the Express.js server:
```bash
npm start
```

The server will be running at `http://localhost:3000`.

## Docker Commands

### Build and Start Containers
```bash
docker-compose up --build
```

### Stop Containers
```bash
docker-compose down
```

### Check Running Containers
```bash
docker ps
```

### Remove Stopped Containers
```bash
docker container prune
```

## Prisma Commands

### Initialize Prisma
```bash
npx prisma init
```

### Generate Prisma Client
```bash
npx prisma generate
```

### Run Database Migrations
```bash
npx prisma migrate dev --name <migration_name>
```

### Open Prisma Studio
```bash
npx prisma studio
```

## Project Structure

```
prisma-with-postgres/
├── prisma/
│   ├── schema.prisma  # Prisma schema file
├── src/
│   ├── index.js       # Entry point for the server
├── .env               # Environment variables
├── docker-compose.yml # Docker Compose configuration
├── package.json       # Node.js dependencies and scripts
```

## Contributing

Contributions are welcome! Feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
