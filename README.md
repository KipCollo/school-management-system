# School Management System

A comprehensive school management system built with Laravel, designed to streamline administrative tasks, manage students, teachers, courses, and more.

## Features

- **Student Management** – Enrol, track, and manage student records
- **Teacher Management** – Assign teachers to courses and manage their profiles
- **Course & Class Management** – Create and organise courses, classes, and schedules
- **Attendance Tracking** – Record and report student attendance
- **Grade Management** – Enter, calculate, and publish student grades
- **Fee Management** – Track student fee payments and generate invoices
- **Role-based Access Control** – Separate dashboards for admins, teachers, students, and parents

## Requirements

- PHP >= 8.2
- Composer
- Node.js >= 18 & npm
- A supported database (MySQL, PostgreSQL, or SQLite)

## Getting Started

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/KipCollo/school-management-system.git
   cd school-management-system
   ```

2. **Install PHP dependencies**

   ```bash
   composer install
   ```

3. **Install JavaScript dependencies**

   ```bash
   npm install
   ```

4. **Set up your environment file**

   ```bash
   cp .env.example .env
   php artisan key:generate
   ```

5. **Configure your database** in `.env`, then run migrations:

   ```bash
   php artisan migrate --seed
   ```

6. **Build frontend assets**

   ```bash
   npm run build
   ```

7. **Start the development server**

   ```bash
   php artisan serve
   ```

   Visit `http://localhost:8000` in your browser.

### Development

Run the Vite development server for hot-reloading:

```bash
npm run dev
```

### Testing

```bash
php artisan test
```

## Project Structure

```
app/
├── Http/Controllers/   # Request handlers
├── Models/             # Eloquent models
└── Providers/          # Service providers
database/
├── factories/          # Model factories for testing
├── migrations/         # Database schema migrations
└── seeders/            # Database seeders
resources/
├── css/                # Stylesheets
├── js/                 # JavaScript source files
└── views/              # Blade templates
routes/
├── web.php             # Web routes
└── console.php         # Artisan console routes
tests/
├── Feature/            # Feature tests
└── Unit/               # Unit tests
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'Add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

## License

This project is open-sourced software licensed under the [MIT license](LICENSE).
