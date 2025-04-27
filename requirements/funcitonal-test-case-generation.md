# 📖 Functional Test Case Prompt Library

---

## 📌 1️⃣ User Authentication

**Prompt Template:**

> Generate functional test cases for a user authentication module in {{framework}}. Cover:

- Successful login
- Incorrect username/password
- Locked or disabled account
- Expired credentials

**Example:**

> Generate functional test cases for a Java Spring Boot authentication API. Include successful login, failure due to incorrect credentials, locked account, and session expiry.

---

## 📌 2️⃣ Payment Processing

**Prompt Template:**

> Generate functional test cases for payment processing covering:

- Successful transaction
- Insufficient balance
- Invalid card/account details
- Payment timeout

**Example:**

> Generate functional test cases for a core banking payment API, including success, insufficient funds, invalid card, and network timeout.

---

## 📌 3️⃣ Data Validation

**Prompt Template:**

> Generate functional test cases for form submission with:

- Valid input
- Missing required fields
- Invalid formats (email, phone, date)
- Boundary value tests

**Example:**

> Generate functional test cases for a customer registration form with valid input, missing phone number, invalid email format, and max character length checks.

---

## 📌 4️⃣ CRUD Operations

**Prompt Template:**

> Generate functional test cases for CRUD operations:

- Create
- Read
- Update
- Delete

**Example:**

> Generate functional test cases for a Savings Account API covering record creation, fetching details, updating contact info, and account closure.

---

## 📌 5️⃣ Role-Based Access Control (RBAC)

**Prompt Template:**

> Generate functional test cases for RBAC scenarios:

- Access allowed for authorized roles
- Access denied for unauthorized roles
- Admin privileges vs. user privileges

**Example:**

> Generate functional test cases for a core banking application where Admins have full access to transactions and Users can only view statements.

---

## 📌 6️⃣ API Endpoints

**Prompt Template:**

> Generate functional test cases for API endpoints:

- 200 OK
- 400 Bad Request
- 401 Unauthorized
- 404 Not Found

**Example:**

> Generate functional test cases for an Account Balance API covering success, invalid account number, missing authentication, and account not found.

---

## 📌 7️⃣ Batch Processing

**Prompt Template:**

> Generate functional test cases for batch processing:

- Successful execution
- Failure due to bad data
- Timeout or job failure
- Large dataset performance

**Example:**

> Generate functional test cases for end-of-day transaction batch processing in a core banking system covering success, error records, and large data volume.

---

## 📒 Summary Table

| Functional Area     | Prompt Purpose                                        | Example                    |
| :------------------ | :---------------------------------------------------- | :------------------------- |
| User Authentication | Test login and security                               | Login, invalid credentials |
| Payment Processing  | Test transaction handling                             | Payment success/failure    |
| Data Validation     | Validate form input and error handling                | Form validations           |
| CRUD Operations     | Test create, retrieve, update, delete operations      | Account CRUD               |
| RBAC                | Test role-based access controls                       | Admin/User permissions     |
| API Endpoints       | Test REST API responses                               | 200/400/401/404 tests      |
| Batch Processing    | Test batch jobs for success, failure, and performance | EOD transaction batches    |

---

## 📑 Best Practices

- Structure: Define input, expected result, and validation step for each case
- Include boundary, negative, and data-driven tests
- Focus on both functional correctness and error handling
- Maintain traceability with feature or requirement IDs
- Prioritize user-critical workflows first
