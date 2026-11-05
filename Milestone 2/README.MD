# FreightQuote AI – Milestone 2

## 1. Project Overview

Milestone 2 focuses on extending the FreightQuote AI application by implementing authentication, role-based access control, administrative functionalities, AI Copilot enhancements, and frontend improvements.

The milestone is divided among four team members to support parallel development and integration of different modules.

## 2. Project Objectives

- Implement secure user registration and authentication.
- Introduce JWT-based authentication and password security.
- Implement role-based access control (RBAC).
- Develop administrative management functionalities.
- Enhance the AI Copilot with additional questions and role-aware responses.
- Improve frontend usability, responsiveness, and visual design.

## 3. Technology Stack

- **Backend:** Python, FastAPI
- **Database:** SQLite
- **Authentication:** JWT, bcrypt
- **Frontend:** HTML, CSS, JavaScript
- **Email Service:** Gmail SMTP
- **AI Copilot:** Python-based question-answering and SQL functionality

## 4. Authentication Module&#x20;

The Authentication module focuses on secure user account management. It includes user registration, login, password hashing using bcrypt, JWT-based authentication, OTP-based password recovery, failed-login tracking, account lockout, and profile management.

Users can view their profile details and update their username or password after verifying their current password.

## 5. Testing and Verification

The following authentication functionalities were implemented and tested:

- User registration and database password hashing.
- Successful and unsuccessful login.
- OTP generation and email delivery.
- Password reset functionality.
- Profile information retrieval.
- Username and password updates.
- Login using the updated password.

## 6. Screenshots

Screenshots of the implemented modules and testing results are included in this section.

## 7. Conclusion

Milestone 2 extends the FreightQuote AI application through the development of authentication, access control, administrative management, AI Copilot enhancements, and frontend improvements. The division of responsibilities among team members supports modular development and integration of the different components.

## 8. Team Contributions

The Milestone 2 project work was divided among four team members, with each member responsible for specific modules and implementation tasks.

| Team Member        | Responsibility            | Contributions                                                                                                                                                                                                                   |
| ------------------ | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Chetana P Kulkarni | Backend Authentication    | Users table, signup/login/forgot/reset routes, password hashing, JWT, `user_of()` rewrite, 5-wrong-password lockout, removal of `localuser.py`, and profile routes.                                                             |
| Ankit Kumar        | RBAC and Admin Management | `rbac.py` (`ROLE_MENU`, `ROLE_CAPS`), `menu_for`, `need`, 403 handling on direct page URLs, customer filtering by `customer_id`, admin routes (add, delete, promote, lock, activity log, KPIs), last-admin and self-lock rules. |
| Venu Kumar         | AI Copilot                | 15+ new questions in `analyst.py` / `qa.py`, spelling and wording handling, SQL and row-count display, polite out-of-scope replies, role-aware answers, and tested-questions list.                                              |
| Anshu Bauskar      | User Interface            | Login, signup and forgot-password screens in `app.js`, Profile page, Admin page UI, `style.css` theme, dark mode, mobile layout, loading and error states.                                                                      |

