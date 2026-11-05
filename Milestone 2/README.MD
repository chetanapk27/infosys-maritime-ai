# Authentication Module – FreightQuote AI

## 1. Overview
The Authentication Module provides secure user authentication and account management functionality for the FreightQuote AI application. It is developed using Python and FastAPI, with SQLite for storing user information. The module incorporates password hashing, JWT-based authentication, OTP verification and account security mechanisms.

## 2. Key Features

- **User Registration:** Allows new users to create accounts with username, email and password validation.
- **User Login:** Authenticates users using registered email addresses and passwords.
- **Password Security:** Uses bcrypt hashing with automatically generated salts to protect stored passwords.
- **JWT Authentication:** Generates JSON Web Tokens after successful authentication and validates bearer tokens for protected API requests.
- **Account Lockout:** Temporarily locks accounts after five consecutive unsuccessful login attempts for five minutes.
- **Forgot Password:** Generates a six-digit OTP and sends it to the registered email address using Gmail SMTP.
- **OTP Verification:** Validates OTPs with a five-minute expiration period and prevents reuse after successful password reset.
- **Password Reset:** Updates the password securely using bcrypt hashing.
- **Account Status Validation:** Checks whether an account is active or locked before granting access.

## 3. Files and Their Functions

| File | Description |
|---|---|
| `server.py` | Implements signup, login, JWT validation, OTP generation and password reset APIs. |
| `config.py` | Manages application configuration, database paths, JWT secrets and email credentials. |
| `hardening.py` | Implements security headers, request logging, IP-based rate limiting and error handling. |
| `mailer.py` | Handles email communication through Gmail SMTP. |
| `localuser.py` | Contains the legacy local operator configuration used before the authentication integration. |

## 4. Authentication Workflow

1. A new user submits registration details.
2. The application validates the username, email and password.
3. The password is hashed using bcrypt and stored in the SQLite database.
4. During login, the entered password is verified against the stored hash.
5. After successful authentication, a JWT access token is generated.
6. The frontend sends the token in the Authorization Bearer header for protected API requests.
7. If a user forgets the password, a six-digit OTP is sent to the registered email address.
8. After successful OTP verification, the user can reset the password securely.

## 5. Technologies Used

- Python
- FastAPI
- SQLite
- bcrypt
- PyJWT
- Gmail SMTP
- Python Secrets Module
- Google Colab Secrets
- Environment Variables

## 6. API Endpoints

| HTTP Method | Endpoint | Purpose |
|---|---|---|
| POST | `/api/auth/signup` | User registration |
| POST | `/api/auth/login` | User login |
| POST | `/api/auth/forgot` | Send password reset OTP |
| POST | `/api/auth/reset` | Verify OTP and reset password |
| GET | `/api/me` | Retrieve authenticated user information |

## 7. Security Measures

- Passwords are never stored in plain text.
- bcrypt is used for secure password hashing and verification.
- JWT tokens use the HS256 signing algorithm and have a two-hour expiry.
- Invalid and expired tokens are rejected.
- Account lockout protects against repeated incorrect login attempts.
- OTPs are time-limited and can only be used once.
- API rate limiting helps prevent excessive requests.
- Security headers and request logging improve application protection.
- Sensitive credentials are managed through environment variables or Google Colab Secrets.

## 8. Configuration Requirements

The application uses the following configuration values:

- `JWT_SECRET`
- `EMAIL_ADDRESS`
- `EMAIL_PASSWORD`
- `ADMIN_PASSWORD`

These credentials must be configured securely and must not be exposed in public source code or GitHub repositories.

## 9. Conclusion

The Authentication Module provides a secure mechanism for user registration, login and account management in the FreightQuote AI application. By integrating bcrypt password hashing, JWT-based authentication, OTP-based password recovery and account lockout, the module strengthens application security and protects user accounts. Additional security features such as API rate limiting, request logging and security headers further improve the reliability of the authentication system.
