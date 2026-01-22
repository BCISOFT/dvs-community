# Security Policy

## Reporting a Vulnerability

We take the security of DevSpaces seriously. If you believe you have found a security vulnerability, please report it to us as described below.

**Please do NOT report security vulnerabilities through public GitHub issues.**

### How to Report

Send an email to **security@devspaces.cloud** with:

1. **Description** of the vulnerability
2. **Steps to reproduce** or proof of concept
3. **Impact assessment** - what could an attacker do?
4. **Your contact information** for follow-up

### What to Expect

- **Acknowledgment**: Within 48 hours
- **Initial assessment**: Within 5 business days
- **Resolution timeline**: Depends on severity, typically 30-90 days

### Safe Harbor

We consider security research conducted in good faith to be authorized. We will not pursue legal action against researchers who:

- Make a good faith effort to avoid privacy violations and disruptions
- Only access data necessary to demonstrate the vulnerability
- Report the vulnerability promptly
- Do not exploit the vulnerability beyond demonstration

## Supported Versions

| Version | Supported |
|---------|-----------|
| 0.2.x   | Yes       |
| < 0.2   | No        |

## Security Best Practices

When using DevSpaces:

- Keep DevSpaces updated to the latest version
- Use strong passwords for database credentials
- Don't expose development environments publicly without authentication
- Regularly rotate API keys and credentials
- Review your `.env` files before sharing projects

## Known Limitations

DevSpaces development environments are designed for **local development only**. They should not be used in production without additional security hardening.
