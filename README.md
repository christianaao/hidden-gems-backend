# Hidden Gems API

## **Table of Contents**  
- [**About This Project**](#about-this-project)
- [**Project Links**](#project-links)
- [**Available Endpoints**](#available-endpoints)
- [**Running This Project Locally**](#running-this-project-locally)
     * [**Database Setup**](#database-setup)
     * [**Installation**](#installation)
- [**Technology**](#technology)
- [**Dependencies and Software Requirements**](#dependencies-and-softwares-requirements)
     * [**Dev Dependencies**](#dev-dependencies)
     * [**Dependencies**](#dependencies)

## **About This Project**

Hidden Gems API is a RESTful API built for the purpose of accessing application data programatically for a front end application.
This is the backend service which provides information about events and places in Manchester, user information, and comment information, and provides this information to the front end architecture. 
The backend is built with PostgreSQL, node-postgres and Node.js, using the Express framework.

## Project Links

Backend API: https://hidden-gems-cd0h.onrender.com/api <br>
Backend Repo: https://github.com/christianaao/hidden-gems-backend <br>
Original Repo Link: https://github.com/espiers13/hidden-gems <br>

Frontend APP: https://hidden-gems-frontend.vercel.app/ <br>
Frontend Repo: https://github.com/christianaao/hidden-gems-frontend <br>
Original Repo Link: https://github.com/flynnjim/hidden-gems-frontend <br>

## Available Endpoints

* GET /api <br>
* GET /api/users <br>
* GET /api/users/:user_id <br>
* POST /api/users <br>
* PATCH /api/users <br>
* GET /api/comments <br>
* GET /api/comments/:gem_id <br>
* POST /api/comments <br>
* DELETE /api/comments/:comment_id <br>
* GET /api/gems <br>
* GET /api/gems/:gem_id <br>
* POST /api/gems <br>
* PATCH /api/gems <br>

 _Please see `endpoints.json` for all available endpoints and example responses_

## Running This Project Locally
### Database Setup

To set up PostgreSQL on your system, please follow this guide: [Install PostgreSQL](https://www.w3schools.com/postgresql/postgresql_install.php)

To install npm: run `npm install npm@latest -g` in your terminal

### Installation

1. In your terminal, locate the directory you would like to save the code to and enter the following. This command will clone this repo:
   ```bash
   git clone https://github.com/christianaao/hidden-gems-backend
   ```

2. In the cloned directory, type `npm install` in your terminal to install all dependencies.

3. Enter the following Dev-Dependency Scripts into your packet.json file:
    - "setup-dbs": "psql -f ./db/setup.sql",
    - "seed": "node ./db/seeds/run-seed.js",
    - "test": "jest",
    - "prepare": "husky install",
    - "start": "node listen.js",
    - "seed-prod": "NODE_ENV=production npm run seed"

4. To connect to the databases locally, create two dotenv files:

  .env.development:
  ```makefile
  PGDATABASE=hidden_gems 
  ```
  .env.test:
  ```makefile
  PGDATABASE=hidden_gems_test 
  ```

5. To create the necessary databases, run:
   ```bash
   npm run setup-dbs  
   ```
   These files should point to your local PostgreSQL databases for development and testing environments.

6. Populate the development database with initial data by running:
   ```bash
   npm run seed  
   ```
   Ensure that the database is correctly seeded before running any tests.

7. To start the application locally, run:
   ```bash
   npm start  
   ```
   This will start the Express server on your local machine. _Please see `endpoints.json` for all available endpoints_

8. To run the test suite and verify the application’s functionality, run:
   ```bash
   npm test  
   ```
   Tests are run using Jest and Supertest for API endpoint validation. 

 ## **Technology**

- **Node.js**: JavaScript runtime for building the backend.
- **Express**: Web framework for handling routing and HTTP requests.
- **PostgreSQL**: Relational database for storing data.
- **node-postgres (pg)**: PostgreSQL client for Node.js.
- **Jest & Supertest**: For testing the API endpoints.

## Dependencies and Software Requirements
### **Dev Dependencies**
   
- `"husky": "^9.1.6",`
- `"jest": "^29.7.0",`
- `"jest-extended": "^4.0.2",`
- `"jest-sorted": "^1.0.15",`
- `"supertest": "^7.0.0"`
   
### **Dependencies**

- `"cors": "^2.8.5",`
- `"dotenv": "^16.4.5",`
- `"express": "^4.21.0",`
- `"nodemon": "^3.1.7",`
- `"pg": "^8.13.0",`
- `"pg-format": "^1.0.4"`

☺ I hope you enjoy testing my server ☺
