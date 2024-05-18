Secrets Application
This is a simple web application that allows users to register and log in to view secret content. The application uses Express.js for the server, PostgreSQL for the database, and bcrypt for password hashing.

Features
User registration with hashed password storage
User login with password verification
Simple secret content viewing upon successful login
Technologies Used
Node.js
Express.js
PostgreSQL
bcrypt
body-parser
Prerequisites
Node.js and npm installed
PostgreSQL installed and running
An existing database named secrets in PostgreSQL
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/secrets-app.git
cd secrets-app
Install the dependencies:

bash
Copy code
npm install
Set up the PostgreSQL database:

Create a new PostgreSQL database named secrets.

Create a users table with the following schema:

sql
Copy code
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password VARCHAR(255) NOT NULL
);
Update the database configuration in the index.js file with your PostgreSQL credentials:

javascript
Copy code
const db = new pg.Client({
  user: "your_username",
  host: "localhost",
  database: "secrets",
  password: "your_password",
  port: 5432,
});
Running the Application
Start the PostgreSQL server if it is not already running.

Start the Node.js application:

bash
Copy code
node index.js
Open your browser and navigate to http://localhost:3000 to access the application.

Routes
GET / - Render the home page.
GET /login - Render the login page.
GET /register - Render the registration page.
POST /register - Handle user registration.
POST /login - Handle user login.