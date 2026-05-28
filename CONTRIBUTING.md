# Contributing to Railway App

Thank you for your interest in contributing to the Railway App project! We welcome contributions from everyone. This document provides guidelines and instructions for contributing.

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md) to help maintain a respectful and inclusive community.

## Getting Started

### Prerequisites
- Node.js 14+ installed
- npm or yarn package manager
- A Railway account (for testing deployment)
- Git knowledge

### Setup Development Environment

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/railway-app.git
   cd railway-app
   ```
3. Add upstream remote:
   ```bash
   git remote add upstream https://github.com/BambaSatoru/railway-app.git
   ```
4. Install dependencies:
   ```bash
   npm install
   ```
5. Create your feature branch:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Development Workflow

### Running Locally

1. Create a `.env` file with your environment variables:
   ```
   DATABASE_URL=your_postgresql_url
   PORT=3000
   ```
2. Start the development server:
   ```bash
   npm start
   ```
3. Test the endpoints:
   - Visit `http://localhost:3000/` for the hello route
   - Visit `http://localhost:3000/db` to test database connection

### Making Changes

1. Make your changes to the codebase
2. Test your changes thoroughly
3. Ensure your code follows the existing style and conventions
4. Commit your changes with clear, descriptive messages:
   ```bash
   git commit -m "feat: add new feature" # for new features
   git commit -m "fix: resolve issue" # for bug fixes
   git commit -m "docs: update documentation" # for documentation
   ```

### Commit Message Convention

We follow conventional commits:
- `feat:` for new features
- `fix:` for bug fixes
- `docs:` for documentation
- `style:` for code style changes
- `refactor:` for code refactoring
- `test:` for tests
- `chore:` for maintenance

## Submitting Changes

### Creating a Pull Request

1. Push your branch to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```
2. Go to the [original repository](https://github.com/BambaSatoru/railway-app)
3. Click "New Pull Request"
4. Select your fork and branch
5. Fill in the PR title and description:
   - Clearly describe what changes you made
   - Reference any related issues (e.g., "Closes #123")
   - Explain the motivation for your changes
6. Submit the pull request

### PR Review Process

- Maintainers will review your PR
- Be open to feedback and suggestions
- Make requested changes by pushing new commits
- Once approved, your PR will be merged

## Reporting Issues

### Bug Reports

When reporting bugs, please include:
- A clear, descriptive title
- A detailed description of the issue
- Steps to reproduce the problem
- Expected behavior
- Actual behavior
- Your environment (Node.js version, OS, etc.)
- Screenshots if applicable

### Feature Requests

For feature requests:
- Use a clear, descriptive title
- Provide a detailed description of the proposed feature
- Explain the use case and benefits
- Provide examples if possible

## Project Structure

```
railway-app/
├── index.js          # Main application file
├── package.json      # Project dependencies
├── Procfile          # Procfile for Railway deployment
├── README.md         # Project documentation
├── CONTRIBUTING.md   # This file
├── LICENSE           # License file
└── .env.example      # Example environment variables
```

## Testing

Before submitting a PR:
1. Test all endpoints locally
2. Verify database connections work correctly
3. Check that no errors appear in the console

## Documentation

When contributing:
- Update the README if you're adding new features
- Add comments to complex code sections
- Update this CONTRIBUTING.md if the development process changes

## Additional Resources

- [Railway Documentation](https://docs.railway.app)
- [Express.js Documentation](https://expressjs.com)
- [PostgreSQL Documentation](https://www.postgresql.org/docs)

## Questions?

Feel free to open an issue or discussion if you have questions about the contribution process.

Thank you for contributing! 🚀
