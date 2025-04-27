# 📖 Functional Test Case Prompt Library — Core Banking: Savings Bank Deposit

---

## 📌 1️⃣ Account Opening

**Prompt Template:**

> Generate functional test cases for a Savings Bank Deposit account opening process in {{framework}}. Cover:

- Successful account creation
- Duplicate customer check
- Invalid input data
- Missing mandatory fields

**Example:**

> Generate functional test cases for a Java Spring Boot REST API for savings account opening including valid input, existing customer, invalid mobile number, and missing PAN number.

---

## 📌 2️⃣ Deposit Transaction

**Prompt Template:**

> Generate functional test cases for deposit transactions covering:

- Successful deposit
- Deposit to inactive/closed account
- Negative or zero deposit amount
- Deposit exceeding regulatory limits

**Example:**

> Generate functional test cases for deposit transaction posting via API including success, zero amount, negative amount, and transaction to a closed account.

---

## 📌 3️⃣ Interest Calculation

**Prompt Template:**

> Generate functional test cases for interest calculation logic covering:

- Interest on positive balance
- No interest on zero or negative balance
- Interest posting on scheduled date
- Leap year calculations

**Example:**

> Generate functional test cases for a Java service method calculating quarterly interest on savings accounts, covering positive balances, zero balance, and February 29 scenarios.

---

## 📌 4️⃣ Account Closure

**Prompt Template:**

> Generate functional test cases for savings account closure covering:

- Successful closure with zero balance
- Attempted closure with non-zero balance
- Pending transaction blocking closure
- Closure with final interest payout

**Example:**

> Generate functional test cases for an account closure API including successful closure, error for non-zero balance, and auto-interest payout on closure date.

---

## 📌 5️⃣ Mini Statement Retrieval

**Prompt Template:**

> Generate functional test cases for mini statement API covering:

- Retrieval of last 5 transactions
- Empty transaction history
- Unauthorized access attempt
- Invalid account number

**Example:**

> Generate functional test cases for a savings account mini statement endpoint, testing valid retrieval, no transactions, invalid account, and unauthorized access.

---

## 📌 6️⃣ Transaction Reversal

**Prompt Template:**

> Generate functional test cases for deposit transaction reversal covering:

- Valid reversal within allowed timeframe
- Reversal after cutoff not permitted
- Non-existing transaction reversal
- Balance adjustment post-reversal

**Example:**

> Generate functional test cases for deposit reversal functionality, including success within 24 hours, failure beyond allowed period, and error for invalid transaction ID.

---

## 📒 Summary Table

| Functional Area      | Prompt Purpose                           | Example                                 |
| :------------------- | :--------------------------------------- | :-------------------------------------- |
| Account Opening      | New savings account creation             | Valid, duplicate, invalid data          |
| Deposit Transaction  | Handle deposit posting scenarios         | Success, inactive account, zero deposit |
| Interest Calculation | Validate interest accrual logic          | Positive, zero, leap year               |
| Account Closure      | Process account closure validations      | Zero balance, pending transactions      |
| Mini Statement       | Retrieve recent transaction history      | Valid/invalid retrieval                 |
| Transaction Reversal | Reverse posted deposits under conditions | Within allowed time, invalid reversal   |

---

## 📑 Best Practices

- Validate business rules, limits, and boundary values
- Test both positive and negative scenarios
- Include regulatory and compliance-related checks
- Simulate peak load and batch operation scenarios where applicable
- Ensure authorization and access control validations for all APIs
