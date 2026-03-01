# UI Automation Framework

A Selenium-based UI automation testing framework built with Java, Cucumber (BDD), and Gradle. Tests are written against [saucedemo.com](https://www.saucedemo.com) and cover core e-commerce workflows such as login, add-to-cart, and checkout.

## Table of Contents

- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Running Tests](#running-tests)
- [Test Reports](#test-reports)
- [Test Coverage](#test-coverage)
- [Technologies](#technologies)

## Project Structure

```
UI_Automation/
├── app/                          # Main test module
│   └── src/
│       ├── main/java/
│       │   ├── pages/            # Page Object Models (LoginPage, CheckoutPage, AddtoCartPage)
│       │   └── utilities/        # Helper utilities (Excel, Database)
│       └── test/java/
│           ├── features/         # Cucumber feature files
│           ├── runners/          # TestRunner configuration
│           └── stepdefinitions/  # Step definitions for BDD scenarios
├── utilities/                    # Shared utilities module
├── list/                         # Additional shared module
├── buildSrc/                     # Custom Gradle convention plugins
└── settings.gradle               # Multi-project build configuration
```

## Prerequisites

- **Java 11+**
- **Gradle 8.10.2** (or use the included Gradle wrapper — no installation required)
- A supported browser (Chrome is recommended; WebDriverManager handles driver setup automatically)

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/Waleed-Ahmad20/UI_Automation.git
   cd UI_Automation
   ```

2. Verify your Java installation:
   ```bash
   java -version
   ```

3. All other dependencies (including the browser driver) are managed automatically by the build.

## Running Tests

Use the Gradle wrapper so no local Gradle installation is required.

**Run all tests:**
```bash
./gradlew test
```

**Run the `app` module tests only:**
```bash
./gradlew :app:test
```

> On Windows, replace `./gradlew` with `gradlew.bat`.

## Test Reports

Allure is integrated for rich HTML reporting.

Test results are written to `app/build/allure-results/` during a test run.

To open the Allure report (requires the [Allure CLI](https://docs.qameta.io/allure/#_installing_a_commandline)):
```bash
allure serve app/build/allure-results
```

Cucumber HTML reports are generated to `target/cucumber-reports/`.

## Test Coverage

| Feature | Scenarios |
|---------|-----------|
| **Login** | Valid login with multiple user credentials (Scenario Outline) |
| **Add to Cart** | Add a product and verify cart item count |
| **Checkout** | End-to-end checkout flow from product page to order confirmation |

## Technologies

| Tool / Library | Version | Purpose |
|----------------|---------|---------|
| Java | 11+ | Primary language |
| Gradle | 8.10.2 | Build & dependency management |
| Selenium | 4.7.2 | Browser automation |
| WebDriverManager | 5.3.1 | Automatic browser driver management |
| Cucumber | 7.11.0 | BDD test framework |
| JUnit 5 | 5.9.2 | Test runner |
| TestNG | 7.4.0 | Additional test support |
| Allure | 2.21.0 | Test reporting |
| Apache POI | 5.2.3 | Excel data utilities |
| MySQL Connector | 8.0.29 | Database utilities |
| Jedis | 4.2.3 | Redis client support |
