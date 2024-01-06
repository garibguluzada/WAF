# Web Application Firewall (WAF) Project

This project is a Web Application Firewall (WAF) designed to protect against common web application vulnerabilities. The WAF is implemented in a Flask-based web application that includes protection against SQL injection, cross-site scripting (XSS), and path traversal attacks. The backend code also logs login attempts, including the IP addresses making requests.

## Table of Contents
- [Features](#features)
- [Getting Started](#getting-started)
- [Vulnerabilities and Protections](#vulnerabilities-and-protections)
- [Logging](#logging)
- [Frontend](#frontend)
- [Running the Application](#running-the-application)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Login System:** Provides a secure login system with protection against common web vulnerabilities.
- **CSRF Protection:** Implements CSRF protection to prevent cross-site request forgery attacks.
- **SQL Injection Prevention:** Utilizes parameterized queries to prevent SQL injection attacks.
- **XSS Protection:** Sanitizes user input to prevent cross-site scripting attacks.
- **Path Traversal Protection:** Guards against path traversal attacks by validating input.

## Getting Started
To get started with the WAF project, follow these steps:

### Setting up the Database
1. Install MySQL server: [MySQL Downloads](https://dev.mysql.com/downloads/)
2. Create a new MySQL database and user for the WAF project. Replace `<database-name>`, `<user-name>`, and `<password>` with your desired values.
    ```sql
    CREATE DATABASE <database-name>;
    CREATE USER '<user-name>'@'localhost' IDENTIFIED BY '<password>';
    GRANT ALL PRIVILEGES ON <database-name>.* TO '<user-name>'@'localhost';
    FLUSH PRIVILEGES;
    ```
3. Configure the database settings in the `get_db()` function of `app.py` with the created database, user, and password.


1. Clone the repository: `git clone <repository-url>`
2. Install the required dependencies: `pip install -r requirements.txt`
3. Configure the database settings in the `get_db()` function of `app.py`.
4. Run the application: `python app.py`

## Vulnerabilities and Protections
The WAF project protects against the following vulnerabilities:

1. **SQL Injection:**
   - Utilizes parameterized queries to prevent SQL injection attacks.
   - Blocks specific SQL keywords and patterns used in injection attempts.

2. **XSS (Cross-Site Scripting):**
   - Sanitizes user input using the `bleach` library to prevent XSS attacks.
   - Blocks script tags and other potentially harmful HTML content.

3. **Path Traversal:**
   - Implements a regular expression pattern to detect and block path traversal attempts.

## Logging
The application logs login attempts, including the following details:

- Username
- Status Code (Success or Failure)
- IP Address

The login logs can be viewed in the admin panel.

## Frontend
The frontend consists of a login page (`index.html`) with CSRF protection, form validation, and error handling. The login page provides feedback on invalid input and displays error messages.

## Running the Application
To run the application, execute the following command:
Visit http://localhost:5000 in your web browser to access the login page.

License
This project is licensed under the MIT License.

```bash
python app.py
