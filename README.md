# WhatsApp Gateway Workshop

A professional pharmacy management system integrated with WhatsApp Gateway for automated communication and transaction tracking.

<p align="center">
  <img src="https://img.shields.io/badge/version-1.0.0-blue.svg" />
  <img src="https://img.shields.io/badge/Laravel-9.x-FF2D20.svg" />
  <a href="LICENSE">
    <img alt="License" src="https://img.shields.io/badge/license-MIT-yellow.svg" target="_blank" />
  </a>
  <a href="https://github.com/reynaldiarya/WhatsApp-Gateway-Workshop/actions">
    <img src="https://codecov.io/gh/reynaldiarya/WhatsApp-Gateway-Workshop/branch/main/graph/badge.svg" />
  </a>
</p>

## Description

WhatsApp Gateway Workshop is a robust management platform designed specifically for pharmacy operations. It bridges the gap between traditional inventory management and modern customer communication by integrating the Fonnte WhatsApp Gateway. The system enables pharmacy staff and management to track medicine inventory, manage transactions, and maintain direct communication with members through automated WhatsApp messaging and template-based responses. It serves as a comprehensive solution for pharmacies looking to digitize their workflow and enhance customer engagement.

## Features

- **WhatsApp Gateway Integration** - Seamless communication using the Fonnte API for automated messaging and real-time webhook handling
- **Role-Based Access Control** - Dedicated dashboards for Management (Admin) and Staff (Pegawai) with specific permission sets
- **Inventory Management** - Comprehensive tracking of medicine stocks, categories, and detailed information
- **Transaction System** - Digital recording of purchases with detailed transaction history and reporting
- **Member CRM** - Manage customer data and link them to specific staff members for personalized service
- **Message Templating** - Create and manage reusable message templates for efficient and consistent customer communication
- **Real-time Webhooks** - Automated processing of incoming messages to route inquiries and updates efficiently

## Tech Stack

- **Backend Framework**: Laravel 9
- **Frontend Engine**: Laravel Mix, Bootstrap, Alpine.js
- **WhatsApp Integration**: Fonnte API
- **Database**: MySQL / MariaDB
- **Authentication**: Laravel built-in Auth (Web-based)
- **Tooling**: Composer, NPM

## Installation

### Prerequisites

- PHP 8.1 or higher
- Composer 2.0 or higher
- Node.js 16 or higher
- MySQL 8.0+ or MariaDB 10.6+

### Steps

1. Clone the repository to your local machine

```bash
git clone https://github.com/reynaldiarya/WhatsApp-Gateway-Workshop.git
cd WhatsApp-Gateway-Workshop
```

2. Install PHP dependencies

```bash
composer install
```

3. Install Node.js dependencies

```bash
npm install
```

4. Set up the environment configuration

```bash
cp .env.example .env
php artisan key:generate
```

5. Configure your database credentials in the `.env` file

6. Run the database migrations and seeders

```bash
php artisan migrate --seed
```

7. Compile frontend assets

```bash
npm run dev
```

8. Start the local development server

```bash
php artisan serve
```

The application will be accessible at `http://localhost:8000`.

## Configuration

The application requires specific database and integration settings in the `.env` file. Ensure the following variables are correctly configured:

| Variable | Description | Example |
|----------|-------------|---------|
| `APP_URL` | Base application URL | `http://localhost:8000` |
| `DB_DATABASE` | Target database name | `whatsapp_gateway_db` |
| `DB_USERNAME` | Database username | `root` |
| `DB_PASSWORD` | Database password | `your_password` |

**Note**: The Fonnte API Token is managed directly within the application's Management Dashboard under the Setting section.

## Usage

### Default Credentials

After running the seeders, you can log in with the following accounts:

- **Management**: `08123456789` / `manajemen1234`
- **Staff**: `081351798490` / `pegawai1234`

### Webhook Integration

To receive incoming WhatsApp messages, configure your Fonnte webhook URL to:
`https://your-domain.com/fonnte-webhook`

### API Interaction

While primarily a web application, it handles incoming POST requests from Fonnte:

**Incoming Message Webhook**
```http
POST /fonnte-webhook
Content-Type: application/json

{
  "sender": "628123456789",
  "message": "Hello, I need to check my medicine status.",
  "target": "628123456780"
}
```

## Project Structure

```text
/
├── app/
│   ├── Http/Controllers/   # Logic for Chat, Medicine, and Transactions
│   ├── Models/             # Database entities (Chat, Medicine, Transaction, Member)
├── config/                 # Application and service configuration
├── database/
│   ├── migrations/         # Schema definitions for management system
│   └── seeders/            # Initial data for users and settings
├── public/                 # Entry point and compiled assets
├── resources/
│   ├── views/              # Blade templates for Management and Staff portals
│   └── js/                 # Frontend logic and components
├── routes/
│   ├── web.php             # Core application routes and webhook endpoint
│   └── api.php             # API-specific definitions
└── webpack.mix.js          # Asset compilation configuration
```

## Scripts / Commands

| Command | Description |
|---------|-------------|
| `composer install` | Install backend dependencies |
| `npm run dev` | Compile assets for development |
| `npm run prod` | Compile and minify assets for production |
| `php artisan migrate` | Execute database migrations |
| `php artisan db:seed` | Seed database with initial data |
| `php artisan serve` | Start the local PHP server |

## Contributing

Contributions are welcome to improve this workshop project.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

<a href="https://github.com/reynaldiarya/WhatsApp-Gateway-Workshop/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=reynaldiarya/WhatsApp-Gateway-Workshop" />
</a>

