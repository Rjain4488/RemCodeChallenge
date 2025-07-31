# 🧪 Test Plan: RemCodeChallenge Web Application

**Repository:** https://github.com/Rjain4488/RemCodeChallenge  
**Author:** Rishabh Jain  
**Date:** July 2025

---

## ✅ 1. Objective: What is Being Tested

This test strategy is designed for validating both **UI functionality** and **backend API endpoints** of the RemCodeChallenge application. The goal is to ensure the core user journey — especially authentication and basic CRUD operations — work as expected without regressions.

---

## 📌 2. Test Coverage Areas

| Layer           | Areas Covered                                      | Type              |
|----------------|----------------------------------------------------|-------------------|
| UI (Frontend)   | Login functionality, Home page load, Error states | UI Automation     |
| API (Backend)   | User authentication, GET/POST operations           | API Integration   |
| Functional      | Positive and negative test cases                   | Functional Tests  |
| Non-functional  | Basic performance and error handling               | Edge Case Testing |

---

## 🛠 3. Tools Used & Why

| Tool           | Purpose                                | Reason for Choice                            |
|----------------|----------------------------------------|----------------------------------------------|
| **Playwright** | UI and API automation                  | Fast, reliable, supports both UI + API tests |
| **Node.js**    | Test runner environment                | Compatible with Playwright                   |
| **VSCode**     | Code development and debugging         | Lightweight and efficient                    |
| **GitHub Actions** (optional) | CI integration                | For future automated test execution          |

---

## ▶️ 4. How to Run the Tests

### Pre-requisites:
- Node.js (v18+)
- Chrome/Edge (Playwright installs its own browsers by default)

### Steps to run tests locally:

```bash
# Clone the repository
git clone https://github.com/Rjain4488/RemCodeChallenge.git
cd RemCodeChallenge

# Install dependencies
npm install

# Install Playwright browsers
npx playwright install

# Run all tests
npx playwright test
```

### To view the HTML report after test run:

```bash
npx playwright show-report
```

---

## ⚠️ 5. Assumptions & Limitations

- The app is assumed to be in a **stable state**, i.e., accessible and functional for login and API operations.
- Test credentials (if any) should be managed securely (e.g., using `.env` files).
- Tests currently focus on **happy path and basic negative cases**. More extensive edge case handling and performance testing are outside the current scope.
- This test suite assumes **frontend and backend are running locally or deployed** in a known environment. Adjust base URL accordingly in the test config.
