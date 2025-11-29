# Cental Car Rental System

A PHP-based car rental management system with user and admin interfaces for managing vehicle bookings and rentals.

## Technologies Used

**Backend:**
- PHP (with PDO for database operations)
- MySQL

**Frontend:**
- Bootstrap 5.0.0
- jQuery 3.6.4
- Font Awesome 5.15.4
- Bootstrap Icons

**Libraries:**
- Owl Carousel (carousel functionality)
- WOW.js (scroll animations)
- Animate.css (CSS animations)
- Easing.js (jQuery easing effects)
- Waypoints.js (scroll detection)

## Prerequisites

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Apache/Nginx web server
- PHP extensions: PDO, PDO_MySQL

## Installation

1. Clone or download the project to your web server directory.

2. Create a MySQL database:
   ```sql
   CREATE DATABASE cental_db;
   ```

3. Import the database schema:
   - Locate the SQL file at `database/cental.sql`
   - Import it into your MySQL database using phpMyAdmin, MySQL command line, or your preferred database tool:
     ```bash
     mysql -u root -p cental_db < database/cental.sql
     ```

4. Configure database connection:
   - Open `config/database.php`
   - Update the following constants with your database credentials:
     ```php
     define('DB_HOST', 'localhost');
     define('DB_NAME', 'cental_db');
     define('DB_USER', 'root');
     define('DB_PASS', 'your_password');
     ```

5. Set proper file permissions:
   - Ensure the web server has read access to all files
   - If using file uploads, ensure write permissions on the `img/` directory

6. Access the application:
   - Frontend: `http://localhost/Cental/` (adjust path based on your setup)
   - Admin Panel: `http://localhost/Cental/admin/`

## Default Admin Credentials

**Email:** admin@cental.com  
**Password:** password

**Admin URL:** `admin/index.php` or `admin/`

**Important:** Change the default admin password after first login for security purposes.

## Project Structure

```
Cental/
├── admin/              # Admin panel files
│   ├── index.php       # Admin login page
│   ├── dashboard.php   # Admin dashboard
│   ├── bookings.php    # Manage bookings
│   ├── cars.php        # Manage vehicles
│   ├── users.php       # Manage users
│   └── includes/       # Admin header/footer
├── auth/               # Authentication pages
│   ├── login.php
│   ├── register.php
│   └── logout.php
├── config/             # Configuration files
│   └── database.php    # Database connection settings
├── database/           # Database schema
│   └── cental.sql      # SQL schema file
├── includes/           # Shared includes
│   ├── header.php
│   ├── footer.php
│   └── functions.php
├── user/               # User dashboard
│   └── dashboard.php
├── css/                # Stylesheets
├── js/                 # JavaScript files
├── lib/                # Third-party libraries
└── img/                # Image assets
```

## Database Schema

The database schema is located in `database/cental.sql`. This file contains:

- Database creation script
- Table definitions for:
  - `users` - User accounts (customers and admins)
  - `cars` - Vehicle inventory
  - `bookings` - Rental bookings

To view or modify the schema, open `database/cental.sql` in a text editor or database management tool.

## Features

- User registration and authentication
- Vehicle browsing and search
- Booking management
- Admin dashboard for managing:
  - Vehicles
  - Bookings
  - Users
- Responsive design for mobile and desktop

## Development Notes

- Session management is handled in `includes/functions.php`
- Database connections use PDO with prepared statements
- All user inputs are sanitized using the `sanitize()` function
- Password hashing uses PHP's `password_hash()` and `password_verify()`

## Troubleshooting

**Database Connection Error:**
- Verify database credentials in `config/database.php`
- Ensure MySQL service is running
- Check that the database `cental_db` exists

**Admin Login Not Working:**
- Verify the admin user exists in the database
- Check that the password hash matches (default password: `password`)
- Ensure sessions are enabled in PHP

**Page Not Found Errors:**
- Verify your web server document root is set correctly
- Check that `.htaccess` or server configuration allows PHP execution
- Ensure all file paths are correct relative to your installation directory

## Security Considerations

- Change default admin credentials immediately
- Use strong passwords for database access
- Keep PHP and MySQL updated to latest stable versions
- Regularly review and update dependencies
- Implement HTTPS in production environments
- Review and sanitize all user inputs

## License

This project is proprietary software. All rights reserved.

