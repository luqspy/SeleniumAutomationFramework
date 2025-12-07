## OrangeHRM Automation Framework
A complete Hybrid Test Automation Framework built using Selenium WebDriver + Java, supporting UI Testing, API Testing, Database Verification, Selenium Grid execution, Jenkins CI/CD, and Docker-based parallel testing environments.

This project demonstrates industry-level automation architecture following best practices such as Page Object Model (POM), TestNG Listeners, Data-Driven Testing, centralized utilities, and scalable execution with Selenium Grid + Jenkins Pipeline.

## Tech Stack
Java 21

- Selenium WebDriver 4

- TestNG (with custom @Listeners + RetryAnalyzer)

- Maven build & dependency management

- Apache POI for reading Excel test data

- Rest-Assured for API Testing

- MySQL JDBC for DB Validation

- Log4j2 for advanced logging

- ExtentReports 5 for interactive HTML reports

## Framework Capabilities
**Page Object Model (POM)**

Each application page has:

Encapsulated locators
Reusable Actions (ActionDriver)
Centralized business functions

**Action Driver Layer**

A wrapper class for Selenium actions:

1. click()
2. enterText()
3. isDisplayed()
4. compareText()
5. scrollToElement()
6. captureScreenshot()
Ensures clean, readable, reusable test code.

**Data-Driven Testing**

1. Excel-powered inputs (TestData.xlsx)
2. TestNG DataProviders
3. Easy multi-data scenario coverage

**API Testing**

1. GET & POST requests
2. JSON extraction
3. Status code validation
4. Integrated with Extent Reports

**Database Assertions**

1. MySQL connection utility
2. SQL result validation inside UI tests
3. Cross-check UI employee data with DB values

**Logging & Reporting**

1. Log4j2 console + file logging
2. Separate app.log & error.log
3. Rich Extent HTML reports with:
  a) Screenshots
  b) Steps
  c) Pass/Fail logs
  d) Thread-safe reporting for parallel execution

**Parallel Cross-Browser Execution**
Powered by TestNG + Selenium Grid:
  1. Chrome, Firefox, Edge nodes
  2. Parallel test execution (parallel="tests")
  3. ThreadLocal WebDriver for thread-safety

**Dockerized Selenium Grid**
Using docker-compose.yml:
  1. Launch Selenium Hub + Chrome, Firefox, Edge nodes
  2. Supports massively parallel UI testing
  3. Zero manual driver management

**CI/CD Integration with Jenkins**
Complete Jenkinsfile pipeline:
  1. Checkout code from GitHub
  2. Start Selenium Grid via Docker
  3. Run Maven Build + Tests
  4. Publish Extent Report
  5. Email notifications for success/failure
  6. Archive artifacts + test results

## Project Structure

```
src
 ├── main
 │    ├── java
 │    │    └── com.orangehrm
 │    │         ├── actiondriver
 │    │         ├── base
 │    │         ├── listeners
 │    │         ├── pages
 │    │         └── utilities
 │    └── resources
 │         ├── config.properties
 │         ├── log4j2.xml
 │       
 │
 ├── test
 │    ├── java
 │    │    └── com.orangehrm.test
 │    │         ├── LoginPageTest
 │    │         ├── HomePageTest
 │    │         ├── ApiTest
 │    │         ├── DBVerificationTest
 │    │         ├── DummyClass & DummyClass2
 │    └── resources
 │         ├── testng.xml
 │         ├── testdata/TestData.xlsx
 │        
 │
docker/
 └── docker-compose.yml
```
## Run Full CI/CD Pipeline in Jenkins
The Jekinsfile supports:
      1. Start Docker Selenium Grid
      2. Checkout project
      3. Parallel UI/API/DB tests
      4. Store reports
      5. Email build status.

To trigger:
  1. Create a Pipeline Job
  2. Point Jenkins to your GitHub repo
  3. Jenkins automatically picks up the Jenkinsfile
   
## Acknowledgements
Inspired by industry best practices and scalable automation architecture patterns.

