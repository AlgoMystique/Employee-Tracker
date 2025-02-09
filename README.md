# Employee Tracker: 

A command-line application from scratch to manage a company's employee database, using Node.js, Inquirer, and PostgreSQL.

## Description:
Developers frequently need to create interfaces that allow non-developers to easily view and interact with information stored in databases. These interfaces are called Content Management Systems (CMS).

Employee Tracker is a command-line application that enables business owners to manage their company's employee database efficiently. This application is built using **Node.js**, **Inquirer**, and **PostgreSQL** to provide an easy way to **view, add, and update** employee information.

## Table of Contents:
- [Installation](#installation)
- [Usage](#usage)
- [Database Schema](#database-schema)
- [Features](#features)
- [Walkthrough Video](#walkthrough-video)
- [License](#license)

## Installation:
1. Clone the repository:
   ```
   git clone 
   ```
2. Navigate to the project directory:
   ```
   cd employee-tracker
   ```
3. Install dependencies:
   ```
   npm install
   ```
4. Set up PostgreSQL database:
   - Create a new database in PostgreSQL.
   - Run the provided `schema.sql` and `seeds.sql` files to set up tables and seed initial data.

## Usage:
1. Start the application by running:
   ```
   node index.js
   ```
2. Follow the on-screen prompts to interact with the database.

## Database Schema:
The database consists of three tables:

### department Table
| Column  | Type          | Constraints                        |
|---------|--------------|-----------------------------------|
| id      | SERIAL       | PRIMARY KEY                       |
| name    | VARCHAR(30)  | UNIQUE, NOT NULL                  |

### role Table
| Column        | Type         | Constraints                          |
|--------------|-------------|-------------------------------------|
| id           | SERIAL      | PRIMARY KEY                         |
| title        | VARCHAR(30) | UNIQUE, NOT NULL                    |
| salary       | DECIMAL     | NOT NULL                             |
| department_id| INTEGER     | NOT NULL, REFERENCES department(id) |

### employee Table
| Column      | Type         | Constraints                          |
|------------|-------------|-------------------------------------|
| id         | SERIAL      | PRIMARY KEY                         |
| first_name | VARCHAR(30) | NOT NULL                             |
| last_name  | VARCHAR(30) | NOT NULL                             |
| role_id    | INTEGER     | NOT NULL, REFERENCES role(id)       |
| manager_id | INTEGER     | REFERENCES employee(id)              |

## Features
- **View** all departments, roles, and employees.
- **Add** a department, role, or employee.
- **Update** an employee's role.
- **Interactive prompts** using Inquirer for an intuitive command-line experience.

## Walkthrough Video
A walkthrough video demonstrating the application's functionality can be found at: coming soon..

## License:
This project is licensed under the MIT License.

