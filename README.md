# Railway App

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-14+-green.svg)](https://nodejs.org/)

A production-ready Node.js application deployed on [Railway](https://railway.app) with Express.js and PostgreSQL. This project demonstrates modern deployment practices with continuous integration/continuous deployment (CI/CD).

## Table of Contents

- [Features](#features)
- [Demo](#demo)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Deployment](#deployment)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- ✅ **Express.js Backend** - Lightweight and fast web framework
- ✅ **PostgreSQL Integration** - Reliable relational database
- ✅ **GitHub Actions CI/CD** - Automatic deployment on push
- ✅ **Railway Deployment** - Easy cloud deployment platform
- ✅ **Environment Configuration** - Secure environment variable management
- ✅ **Connection Pooling** - Optimized database connections
- ✅ **Error Handling** - Robust error management

## Demo

The application is deployed on Railway and provides two main endpoints:

- **Hello Endpoint**: `GET /` - Returns a welcome message
- **Database Status**: `GET /db` - Returns current database time

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (v14 or higher)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Git](https://git-scm.com/)
- [Railway Account](https://railway.app) (for deployment)

## Installation

### Local Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/BambaSatoru/railway-app.git
   cd railway-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```
   or
   ```bash
   yarn install
   ```

3. **Copy environment variables**
   ```bash
   cp .env.example .env
   ```

4. **Update .env with your values**
   ```
   PORT=3000
   DATABASE_URL=postgresql://user:password@localhost:5432/railway_db
   ```

## Configuration

### Environment Variables

Create a `.env` file in the root directory (see `.env.example` for template):

```env
# Server Configuration
PORT=3000
NODE_ENV=development

# Database Configuration
DATABASE_URL=postgresql://user:password@host:port/database
```

### Railway Setup

1. Create a new project on [Railway](https://railway.app)
2. Add a PostgreSQL plugin
3. Copy the `DATABASE_URL` from the PostgreSQL service
4. Add the following environment variables:
   - `DATABASE_URL`: Your PostgreSQL connection string
   - `PORT`: Set to 3000 (or your preferred port)

## Usage

### Running Locally

```bash
npm start
```

The server will start on `http://localhost:3000` (or your configured port).

You should see:
```
Server running on port 3000
```

### Testing Endpoints

#### Hello Endpoint
```bash
curl http://localhost:3000/
```
Response:
```
Hello from Railway!
```

#### Database Status
```bash
curl http://localhost:3000/db
```
Response:
```json
{
  "time": {
    "now": "2025-05-14T12:34:56.789Z"
  }
}
```

## API Endpoints

### GET /

Simple health check endpoint.

- **URL**: `/`
- **Method**: `GET`
- **Response**: Plain text

```bash
curl http://localhost:3000/
```

### GET /db

Database connectivity test endpoint.

- **URL**: `/db`
- **Method**: `GET`
- **Response**: JSON with current database time

```bash
curl http://localhost:3000/db
```

**Success Response (200):**
```json
{
  "time": {
    "now": "2025-05-14T12:34:56.789Z"
  }
}
```

**Error Response (500):**
```json
{
  "error": "Database connection failed"
}
```

## Deployment

### Deploy to Railway

1. **Connect your GitHub repository**
   - Go to [Railway Dashboard](https://railway.app/dashboard)
   - Click "New Project" → "Deploy from GitHub repo"
   - Select this repository

2. **Configure environment variables**
   - In Railway project settings, add your environment variables
   - Railway will automatically provide `DATABASE_URL` if you add PostgreSQL

3. **Deploy**
   - Railway automatically deploys on every push to your main branch
   - Monitor deployments in the Railway dashboard

### Using GitHub Actions

The project includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that:
- Runs on every push to the main branch
- Tests the build process
- Deploys to Railway automatically

## Project Structure

```
railway-app/
├── index.js              # Main application entry point
├── package.json          # Project dependencies and metadata
├── package-lock.json     # Locked dependency versions
├── Procfile              # Procfile for Railway deployment
├── .env.example          # Example environment variables
├── .gitignore            # Git ignore rules
├── README.md             # This file
├── CONTRIBUTING.md       # Contribution guidelines
├── CODE_OF_CONDUCT.md    # Community code of conduct
├── SECURITY.md           # Security policy
├── CHANGELOG.md          # Version history
├── LICENSE               # MIT License
└── .github/
    └── workflows/        # GitHub Actions workflows
```

## Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository** - Click the fork button
2. **Create a feature branch** - `git checkout -b feature/amazing-feature`
3. **Commit your changes** - `git commit -m 'Add amazing feature'`
4. **Push to the branch** - `git push origin feature/amazing-feature`
5. **Open a Pull Request** - Describe your changes clearly

For detailed guidelines, see [CONTRIBUTING.md](CONTRIBUTING.md)

### Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md) to help keep our community respectful and inclusive.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

### Getting Help

- 📖 Check the [FAQ](#faq) below
- 🐛 Open an [Issue](https://github.com/BambaSatoru/railway-app/issues)
- 💬 Start a [Discussion](https://github.com/BambaSatoru/railway-app/discussions)
- 🔒 For security issues, see [SECURITY.md](SECURITY.md)

### FAQ

**Q: How do I update dependencies?**
```bash
npm update
```

**Q: How do I check for security vulnerabilities?**
```bash
npm audit
```

**Q: Can I deploy to other platforms?**
Yes, this is a standard Node.js/Express application. See the [deployment](#deployment) section for more information.

**Q: How do I debug database connection issues?**
1. Verify `DATABASE_URL` is correct
2. Check database credentials
3. Ensure SSL is enabled if required
4. Check database firewall rules

## Troubleshooting

### Port Already in Use
```bash
# Linux/Mac
lsof -i :3000
kill -9 <PID>

# Windows
netstat -ano | findstr :3000
taskkill /PID <PID> /F
```

### Database Connection Failed
- Verify `DATABASE_URL` format
- Check database server is running
- Ensure credentials are correct
- Check network connectivity

### Dependencies Installation Issues
```bash
rm -rf node_modules package-lock.json
npm install
```

## Roadmap

- [ ] Add authentication
- [ ] Add request logging
- [ ] Add API rate limiting
- [ ] Add unit tests
- [ ] Add API documentation (Swagger/OpenAPI)
- [ ] Add Docker support

## Related Resources

- [Railway Documentation](https://docs.railway.app)
- [Express.js Guide](https://expressjs.com/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Node.js Best Practices](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)

## Acknowledgments

- [Express.js](https://expressjs.com/) - Web framework
- [PostgreSQL](https://www.postgresql.org/) - Database
- [Railway](https://railway.app) - Deployment platform
- [GitHub Actions](https://github.com/features/actions) - CI/CD platform

---

**Made with ❤️ by BambaSatoru**

If you found this helpful, please consider giving it a ⭐ star!
