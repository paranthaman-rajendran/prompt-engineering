# 📖 Prompt Library — Code Generation & JUnit Testing Best Practices

---

## 📌 1️⃣ Code Generation with Best Practices

**Prompt Template:**

> Generate a {{language/framework}} service class following clean code principles:

- Use descriptive method and variable names
- Implement input validations and error handling
- Avoid hardcoded values (use constants/config)
- Follow single responsibility principle
- Use logging for critical operations

**Example:**

> Generate a Java Spring Boot service class to process fund transfers with input validations, balance checks, transaction logging, and exception handling.

---

## 📌 2️⃣ JUnit Test Generation with Mocking (90%+ Coverage)

**Prompt Template:**

> Generate JUnit test cases for a {{language/framework}} service class {{className}} covering positive, negative, and edge scenarios using Mockito. Target 90%+ code coverage and mock external dependencies like repositories, APIs, and utility classes.

**Example:**

> Generate JUnit 5 test cases for `FundTransferService` class covering successful transfer, insufficient balance, account not found, and null input scenarios. Mock `AccountRepository` and `TransactionLogger` dependencies.

---

## 📌 3️⃣ Mocking External Dependencies

**Prompt Template:**

> Generate JUnit tests with Mockito for {{className}} by mocking {{dependencies list}} and injecting them into the class using `@InjectMocks` and `@Mock` annotations.

**Example:**

> Generate JUnit tests for `LoanApprovalService` by mocking `LoanRepository`, `NotificationService`, and `EligibilityRuleEngine`.

---

## 📌 4️⃣ Code Coverage Validation

**Prompt Template:**

> Suggest additional test cases for {{className}} to achieve 90%+ code coverage based on the existing code. Focus on uncovered conditional branches and exception handling blocks.

**Example:**

> Suggest additional test cases for `TransactionService` to cover null input scenarios, invalid account types, and exception catch blocks for database errors.

---

## 📌 5️⃣ Summary Prompt Library Table

| Task                  | Prompt Purpose                                       | Example Prompt                                          |
| :-------------------- | :--------------------------------------------------- | :------------------------------------------------------ |
| Code Generation       | Service classes with clean code and best practices   | `Generate a service class with validations and logging` |
| JUnit Test Generation | Tests with positive/negative scenarios using Mockito | `Generate JUnit 5 tests for FundTransferService`        |
| Mocking Dependencies  | Mock external dependencies for unit testing          | `Mock dependencies in LoanApprovalService`              |
| Coverage Validation   | Identify missing tests for 90%+ code coverage        | `Suggest extra test cases for TransactionService`       |

---

## 📑 Best Practices Reference

- Follow **Clean Code** principles: meaningful names, small functions, single responsibility
- Always include **input validations and null checks**
- Use **Mockito** for dependency mocking
- Include **positive, negative, edge case, and exception scenario tests**
- Achieve **90%+ code coverage** by testing all branches and exception handlers
- Use `@BeforeEach` for test setup and `@AfterEach` for teardown if needed
- Avoid hardcoded values — use constants/configurable parameters
- Use structured, clear, and consistent logging practices

---
