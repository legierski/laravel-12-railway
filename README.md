# Laravel 12 Railway Template

[![Deploy on Railway](https://railway.com/button.svg)](https://railway.com/deploy/laravel-12-php-84-mysql-84?referralCode=r8uelI)

A clean Laravel 12 template with Docker (Laravel Sail) configured for consistent local development and Railway deployment.

## Features

- Laravel 12 with PHP 8.4
- Laravel Sail for local Docker development
- MySQL 8.4 database
- Railway deployment configuration
- HTTPS URL forcing for production environments

## Quick Start

### Local Development

```bash
# Clone the repository
git clone <your-repo-url>
cd laravel-12-railway

# Generate application key
php artisan key:generate

# Start Docker containers
./vendor/bin/sail up -d

# Run migrations
./vendor/bin/sail artisan migrate

# Visit http://localhost
```

### Railway Deployment

1. Push to GitHub
2. Create new Railway project
3. Connect to GitHub repository
4. Add environment variables:
   - `APP_KEY` (generate with `php artisan key:generate --show`)
   - `APP_ENV=production`
   - `APP_URL=https://your-app.up.railway.app`
5. Deploy automatically via GitHub pushes

## Environment Variables

Copy `.env.example` to `.env` and configure:

- **Local**: Uses MySQL via Docker
- **Railway**: Set production environment variables in Railway dashboard

## Docker Services

- **app**: Laravel application (PHP 8.4, nginx)
- **mysql**: MySQL 8.4 database

## Commands

```bash
# Local development
./vendor/bin/sail up -d    # Start containers
./vendor/bin/sail down     # Stop containers
./vendor/bin/sail artisan  # Run artisan commands
./vendor/bin/sail composer # Run composer commands
./vendor/bin/sail npm      # Run npm commands

# Testing
./vendor/bin/sail test
```

## Deployment

Railway automatically deploys when you push to your connected GitHub repository. The `railway.toml` configuration uses the same Docker setup as local development.