# Milestone 2 – Authentication Module

## Overview
This folder contains the authentication and security-related implementation for the FreightQuote AI application. It uses Python, FastAPI, SQLite, bcrypt, JWT and Gmail SMTP to support secure user authentication, password recovery and application security.

## Files and Their Description

### 1. `server.ipynb`
- Implements the FastAPI application and authentication endpoints.
- Provides user registration and login functionality.
- Uses bcrypt to hash passwords and verify login credentials.
- Generates JWT access tokens for authenticated users.
- Validates bearer tokens and checks user account status.
- Implements OTP-based password recovery.
- Locks accounts after five unsuccessful login attempts for five minutes.

### 2. `config.ipynb`
- Manages application configuration and environment variables.
- Configures the SQLite database path.
- Retrieves sensitive credentials from Google Colab Secrets or environment variables.
- Manages JWT secret keys and email configuration.
- Stores application-specific settings.

### 3. `mailer.ipynb`
- Handles email communication using Gmail SMTP.
- Supports sending emails with attachments and optional HTML content.
- Uses Gmail App Password authentication.
- Provides email configuration checking.

### 4. `hardening.ipynb`
- Implements additional application security measures.
- Provides request ID generation and access logging.
- Applies security headers and Content Security Policy.
- Implements IP-based rate limiting for API endpoints.
- Handles server errors without exposing internal tracebacks.
- Provides application metrics and readiness endpoints.

### 5. `localuser.ipynb`
- Contains the legacy local operator configuration.
- Defines a default local user with Admin role.
- Serves as a transitional component for the authentication and role-based access control integration.

## Authentication Features

- User registration with input validation.
- Secure password hashing using bcrypt.
- JWT-based authentication using the HS256 algorithm.
- Bearer token validation.
- Failed-login tracking and temporary account lockout.
- Six-digit OTP generation for password recovery.
- OTP expiration after five minutes.
- Secure OTP comparison and one-time usage.
- Password reset with bcrypt hashing.

## Technologies Used

- Python
- FastAPI
- SQLite
- bcrypt
- PyJWT
- Gmail SMTP
- Google Colab Secrets
- Environment Variables

## Security Configuration

The application uses configuration values such as:

- `JWT_SECRET`
- `EMAIL_ADDRESS`
- `EMAIL_PASSWORD`
- `ADMIN_PASSWORD`

These values must be configured securely using Google Colab Secrets or environment variables. Sensitive credentials should never be committed to GitHub.

## Conclusion

The Authentication Module provides the core user authentication and security functionality for the FreightQuote AI application. It combines password protection, token-based authentication, OTP verification, account lockout and application-level security mechanisms to improve the reliability and security of the application.
