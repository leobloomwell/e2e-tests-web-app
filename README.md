# Bloomwell Web App – E2E Tests

End-to-end (E2E) test suite for the Bloomwell Patient Web Application, built with Playwright.

The project focuses on critical user flows and auth-related smoke tests to ensure application stability on DEV and STAGING environments.

---

## Scope of Testing

Currently automated flows:

### Authentication (Smoke)
- Login
- Registration (open registration flow)
- Forgot password
- Cookie banner handling (GDPR)

### Planned / Future
- Full registration submission
- Checkout flow
- Payments
- Mobile-specific smoke tests
- CI integration (GitHub Actions)

---

## Environments

| Environment | URL |
|------------|-----|
| DEV | https://app.dev.bloomwell.de |
| STAGING | https://app.staging.bloomwell.de |

---

## Tech Stack

- Playwright
- TypeScript
- Node.js
- dotenv
- Nodemailer (for test reports)

---

## Project Structure


