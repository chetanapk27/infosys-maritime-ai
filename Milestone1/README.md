## Maritime Freight Portal
### Infosys Springboard Internship 7.0 — Batch 4 | Milestone 1

## 1. Project Overview
The Maritime Freight Portal is a web-based application. It implements user authentication, account registration, password recovery, JWT-based session authentication, and an administrator dashboard.
The portal provides separate interfaces for registered users and administrators, with an emphasis on secure credential handling and access control.

## 2. Features
- User Login: Authenticates registered users.
- User Registration: Allows new users to create accounts with input validation.
- Forgot Password: Supports password recovery through security questions and email OTP verification.
- Password Validation: Enforces password complexity requirements.
- JWT Authentication: Generates and validates JSON Web Tokens for authenticated sessions.
- Login Protection: Implements account lockout after three failed login attempts for 20 minutes.
- User Dashboard: Provides access to the authenticated user's dashboard.
- Admin Dashboard: Displays registered user information, including usernames and email addresses, without displaying password data.
- Secure Credential Management:Uses Google Colab Secrets and environment variables for sensitive configuration values.
- Logout: Allows users to end their authenticated sessions.

## 3. Technologies Used
- Programming Language: Python
- Web Framework: Streamlit
- Database: SQLite
- Authentication: PyJWT
- Password Hashing: bcrypt
- Email Verification: Gmail SMTP and OTP
- Tunnel Service: ngrok
- Development Environment: Google Colab

## 4. Application Modules
Login: Verifies user credentials and establishes an authenticated session using a JWT.
Signup: Registers new users after validating the required fields, email format, and password strength.
Forgot Password: Provides two password recovery methods:
- Security-question verification
- Email OTP verification
User Dashboard: Displays the dashboard after successful authentication.
Admin Dashboard: Provides the administrator with a view of registered user details.

## 5. Security Measures
- Passwords are stored as hashes rather than plaintext.
- JWTs are used to manage authenticated sessions.
- Password complexity and form validation are applied.
- Failed login attempts trigger a temporary account lockout.
- Sensitive configuration values are retrieved from Google Colab Secrets.
- Email credentials and ngrok authentication tokens are not intended to be hardcoded in the submitted notebook.
- The admin dashboard does not display user passwords.

## 6. Prerequisites

Before running the application, ensure that you have:

- A Google account with access to Google Colab
- A Gmail account configured for application-password-based email access
- An ngrok account and authentication token
- The required Python packages

## 7. Configuration
Store the required credentials in Google Colab Secrets. The secret names must match those used by the notebook.

| Secret name | Purpose |
|---|---|
| `JWT_SECRET` | Signs and validates JWTs |
| `EMAIL_ADDRESS` | Sender email address |
| `EMAIL_PASSWORD` | Gmail application password |
| `NGROK_AUTHTOKEN` | Authenticates the ngrok tunnel |

### Ngrok Authentication and Token Setup

Ngrok authentication is used to authorize the ngrok client to create a tunnel between the public internet and the Streamlit application running in Google Colab. In this project, the ngrok authentication token is stored securely in Google Colab Secrets under the name `NGROKAUTHTOKEN`. The application retrieves the token using `userdata.get("NGROKAUTHTOKEN")` and uses it to authenticate the ngrok client before creating a tunnel to port `8501`. Ngrok then generates a public URL through which the user can access the running authentication portal. Storing the token in Colab Secrets instead of hardcoding it in the notebook helps prevent accidental exposure of the credential in the source code.

## How to Sign In and Get Your Ngrok Authentication Token

Follow these steps to obtain the ngrok authentication token and configure it in Google Colab.

1. **Open the ngrok login page:** Visit [https://dashboard.ngrok.com/login](https://dashboard.ngrok.com/login).

2. **Sign in to your account:** Use your registered email and password, or select Google or GitHub sign-in if you used one of these methods to create your account.

3. **Open the Authtoken page:** Visit [https://dashboard.ngrok.com/get-started/your-authtoken](https://dashboard.ngrok.com/get-started/your-authtoken).

4. **Copy the authentication token:** Copy the token displayed on the dashboard. Complete any required account verification if prompted.

5. **Open Google Colab Secrets:** Open your Colab notebook and click the **key icon** in the left sidebar.

6. **Add the token:** Create a secret with the exact name `NGROKAUTHTOKEN` and paste your ngrok authentication token as its value.

7. **Enable notebook access:** Ensure access is enabled for this secret in your notebook.

8. **Run the launch cell:** Execute the setup and launch cell to authenticate ngrok, start the Streamlit application on port `8501`, and generate a public URL.

**Security Note:** Never include your actual ngrok authentication token in your README, source code, screenshots, or public GitHub repository. Store it securely in Google Colab Secrets.

## 8. How to Run
1. Open the submitted notebook in Google Colab.
2. Configure the required secrets in the Colab Secrets panel.
3. Enable notebook access to the configured secrets, if prompted.
4. Run the notebook cells in order.
5. Allow the application to start and obtain the ngrok URL.
6. Open the generated URL in a browser.
7. Test the login, signup, password recovery, user dashboard, and admin dashboard features.
8. Use the logout option to end the session.

## 9. Database
The application uses SQLite to store user account information and related authentication data. The database is created and accessed by the application as configured in the notebook.

The database file is generated or accessed at runtime. Its persistence depends on the execution environment and database configuration.

## 10. Testing
The following application workflows should be tested before submission:
- User registration and input validation
- Successful and unsuccessful login
- Temporary lockout after repeated failed login attempts
- JWT authentication and invalid or expired token handling
- Password recovery using security questions
- Password recovery using email OTP
- User dashboard access
- Admin dashboard access
- Logout and session termination

## 11. Project Scope
This milestone focuses on implementing and validating the portal's authentication, account management, password recovery, and role-specific dashboards. The broader internship project is titled *Agentic AI for Maritime Freight Pricing and Route Optimization*.
