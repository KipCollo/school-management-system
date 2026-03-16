# School Management System

A comprehensive web application built with **Laravel** for managing school operations including students, teachers, courses, attendance, grades, and fees.

## Table of Contents

- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Modules](#modules)
- [API](#api)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Multi-role Authentication** — Admin, Teacher, Student, and Parent portals
- **Student Management** — Enroll, track, and manage student records
- **Staff Management** — Teacher and staff profiles, schedules, and assignments
- **Course & Curriculum Management** — Subjects, classes, timetables
- **Attendance Tracking** — Daily attendance for students and staff
- **Grade & Marks Management** — Exam results, report cards, transcripts
- **Fee Management** — Fee structures, payments, and receipts
- **Notice Board** — Announcements and event management
- **Parent Portal** — Parents can view their child's academic progress
- **Reports & Analytics** — Exportable reports in PDF and Excel formats

## Requirements

- PHP >= 8.2
- Composer >= 2.x
- Node.js >= 18.x and npm >= 9.x
- MySQL >= 8.0 or PostgreSQL >= 14
- A web server: Apache or Nginx

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/KipCollo/school-management-system.git
cd school-management-system
```

### 2. Install PHP dependencies

```bash
composer install
```

### 3. Install JavaScript dependencies

```bash
npm install
```

### 4. Set up environment variables

```bash
cp .env.example .env
php artisan key:generate
```

### 5. Configure your database

Edit the `.env` file and update the database credentials:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=school_management
DB_USERNAME=your_db_username
DB_PASSWORD=your_db_password
```

### 6. Run database migrations and seeders

```bash
php artisan migrate --seed
```

### 7. Build front-end assets

```bash
npm run build
```

### 8. Start the development server

```bash
php artisan serve
```

The application will be available at `http://127.0.0.1:8000`.

## Configuration

Key environment variables (see `.env.example` for the full list):

| Variable | Description | Default |
|---|---|---|
| `APP_NAME` | Application name | `School Management System` |
| `APP_ENV` | Environment (`local`, `production`) | `local` |
| `APP_DEBUG` | Enable debug mode | `true` |
| `APP_URL` | Base URL of the application | `http://localhost` |
| `DB_CONNECTION` | Database driver | `mysql` |
| `DB_DATABASE` | Database name | `school_management` |
| `MAIL_MAILER` | Mail driver | `smtp` |
| `QUEUE_CONNECTION` | Queue driver | `database` |
| `CACHE_STORE` | Cache store | `database` |

### Storage

Link the public storage disk:

```bash
php artisan storage:link
```

## Usage

### Default Credentials (after seeding)

| Role | Email | Password |
|---|---|---|
| Admin | admin@school.example | password |
| Teacher | teacher@school.example | password |
| Student | student@school.example | password |
| Parent | parent@school.example | password |

> **Note:** Change all default passwords immediately after the first login.

### Artisan Commands

```bash
# Run migrations
php artisan migrate

# Rollback and re-run all migrations
php artisan migrate:fresh --seed

# Clear all caches
php artisan optimize:clear

# Run the queue worker
php artisan queue:work

# Generate a new admin user (custom command – requires implementation)
php artisan make:admin
```

## Modules

### Admin Dashboard

- Overview statistics: total students, teachers, classes, revenue
- Recent activities and quick actions

### Student Management

- Register new students with personal and guardian details
- Assign students to classes and sections
- View academic history and progress

### Staff Management

- Add teachers and non-teaching staff
- Assign subjects and classes to teachers
- Track leave and payroll (if configured)

### Academic Management

- Create academic years, classes, sections, and subjects
- Build and manage timetables
- Handle examination scheduling

### Attendance

- Mark daily attendance via web interface or bulk import (CSV)
- View attendance reports per student, class, or date range
- Automated absence notifications (email/SMS)

### Grades & Examinations

- Enter marks for continuous assessments and exams
- Auto-calculate grades based on configurable grading scales
- Generate and print report cards

### Fee Management

- Define fee structures per class and academic year
- Record student payments and issue receipts
- Track outstanding balances and send reminders

### Notice Board

- Post school-wide or class-specific announcements
- Schedule events and send email notifications

## API

The application exposes a RESTful JSON API under the `/api/v1` prefix.

Authentication uses **Laravel Sanctum** (token-based).

### Authentication endpoints

```
POST   /api/v1/login
POST   /api/v1/logout
GET    /api/v1/user
```

### Example endpoints

```
GET    /api/v1/students
POST   /api/v1/students
GET    /api/v1/students/{id}
PUT    /api/v1/students/{id}
DELETE /api/v1/students/{id}

GET    /api/v1/teachers
GET    /api/v1/courses
GET    /api/v1/attendance
GET    /api/v1/grades
```

Full API documentation is generated by Scribe and available at `/docs` when `APP_ENV=local`.

## Testing

Run the test suite with PHPUnit:

```bash
php artisan test
```

Run only unit tests:

```bash
php artisan test --testsuite=Unit
```

Run only feature tests:

```bash
php artisan test --testsuite=Feature
```

Generate a coverage report (requires Xdebug or PCOV):

```bash
php artisan test --coverage
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "feat: add your feature"`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request against the `main` branch

Please follow the [PSR-12](https://www.php-fig.org/psr/psr-12/) coding standard and write tests for new functionality.

## License

This project is licensed under the **Apache License 2.0**. See the [LICENSE](LICENSE) file for details.
