# Running Node.js Application in Production
## Table of Contents
1. Introduction
2. Prerequisites
3. Deployment Environment
4. Configuration
5. Deployment Process

### 1. Introduction
This documentation provides guidelines on running a Node.js application built with Express.js and using PostgreSQL as the database in a production environment. It covers everything from setting up the deployment environment to monitoring and maintenance.

### 2. Prerequisites
Before proceeding, make sure you have the following prerequisites:

- Node.js and npm installed (latest LTS version recommended).
- PostgreSQL database server installed and configured.
- Basic knowledge of Linux command-line operations.
- Domain or subdomain for your application (for setting up a production URL).

### 3. Deployment Environment
#### 3.1. Server Setup
1. Choose a reliable hosting provider or cloud service (e.g., AWS, DigitalOcean, Heroku).
2. Provision a server instance with the desired specifications, considering the application's requirements.
3. Set up SSH access to the server securely.

#### 3.2. Domain Setup
1. Configure DNS settings to point your domain or subdomain to the server's IP address.
2. Ensure that your SSL certificate is installed and configured properly for secure HTTPS communication.

### 4. Configuration
#### 4.1. Environment Variables
Store sensitive configuration data (e.g., database credentials, API keys) as environment variables. Use a `.env` file or a configuration manager like `dotenv`.

Create a `.env` file with the necessary variables and values. Example:

```shell
PORT=3000
DATABASE_URL=postgres://username:password@localhost:5432/database_name
SECRET_KEY=your_secret_key
```

#### 4.2. Sequelize Configuration
1. Install the Sequelize library and PostgreSQL driver:
```sh
npm install sequelize pg pg-hstore
```

#### 4.3. Nginx (Optional)
If you are using Nginx as a reverse proxy, configure it to route traffic to your Node.js application. Create a server block that listens on port 80 and forwards requests to your Node.js application running on a specific port.


### 5. Deployment Process
#### 5.1. Application Deployment
1. Clone your application's source code to the server using Git or another version control system.
2. Install Node.js dependencies by running `npm install --production`.
3. Start the Node.js application using a process manager like PM2.

Using PM2:

```shell
pm2 start app.js
```

#### 5.2. Database Migration
1. Ensure that you have the **Sequelize CLI** (sequelize-cli) installed globally on your server:
```sh
npm install -g sequelize-cli
```
1. Apply the migration to your production database:

```sh
sequelize db:migrate --env production
```


#### 5.3. Proxy Configuration (Nginx)
If using Nginx, configure it to proxy requests to your Node.js application.

#### 5.4. Firewall Configuration
Ensure that your server's firewall allows traffic on the required ports (e.g., 80, 443, 22).