# Security Policy

## Supported Versions

Currently, all versions of the Railway App are supported with security updates. When a new major version is released, the previous major version will receive security updates for 6 months.

## Reporting a Vulnerability

If you discover a security vulnerability, please do not open a public issue. Instead, please email us or open a private security advisory.

### Steps to Report:

1. **Do not** publicly disclose the vulnerability
2. Contact the maintainers with:
   - Description of the vulnerability
   - Steps to reproduce the issue
   - Potential impact
   - Suggested fix (if available)

3. Allow 48 hours for an initial response
4. We will work with you to:
   - Verify and understand the vulnerability
   - Develop and test a fix
   - Release a patched version
   - Provide you with credit (if desired)

## Security Best Practices

When deploying this application:

### Environment Variables
- Never commit `.env` files to version control
- Use Railway's environment variable management
- Rotate `DATABASE_URL` credentials regularly
- Use strong, unique passwords for database access

### Database Security
- Enable SSL connections to PostgreSQL
- Use strong passwords for database users
- Restrict database access to application IP addresses
- Keep PostgreSQL updated

### Application Security
- Keep dependencies updated: `npm audit` and `npm update`
- Review security advisories regularly
- Use HTTPS in production (Railway handles this automatically)
- Implement rate limiting for production
- Add input validation for all endpoints

### Deployment
- Use environment variables for sensitive data
- Never log sensitive information
- Monitor application logs for suspicious activity
- Keep Node.js runtime updated

## Dependency Updates

We use npm to manage dependencies. To check for vulnerabilities:

```bash
npm audit
npm audit fix
```

Dependencies are updated regularly to receive security patches.

## Known Issues

Currently, there are no known security issues.

## Contact

For security concerns, please reach out to the maintainers privately.
