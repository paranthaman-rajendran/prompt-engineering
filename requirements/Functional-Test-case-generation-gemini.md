# Prompt Library Template: Functional Test Case Generation

## Feature: Core Banking - Savings Account Deposit

**Objective:** To provide a standardized prompt structure for generating functional test cases (positive and negative) for the savings account deposit feature using Generative AI.

---

### Core Prompt Template

**Instructions:**
Replace the bracketed placeholders `[...]` with specific details relevant to _your_ application's savings deposit functionality before submitting this prompt to an AI tool (like ChatGPT or Gemini). Providing specific details about rules, limits, and the access channel will significantly improve the quality and relevance of the generated test cases.

**Prompt:**

```text
Generate functional test cases for the **Savings Account Deposit** feature accessed via **[Specify Channel, e.g., Online Banking Portal, Mobile App, ATM, Teller Application]**.

**Feature Description:**
The feature enables a **[Specify User Role, e.g., Customer, Bank Teller]** to deposit funds into a designated savings account.
-   **Key Inputs Required:** Target Savings Account Number, Deposit Amount, Currency ([Specify Default/Allowed Currency, e.g., USD, INR]), Deposit Method ([Specify Method if relevant for the channel, e.g., Cash Deposit, Cheque Deposit, Internal Transfer from Linked Account]).
-   **Core System Validation Rules:**
    -   Target Account Number must be a valid account number existing in the core banking system.
    -   Target Account must be identified as a 'Savings' type account.
    -   Target Account status must be **[Specify Allowed Status(es), e.g., 'Active', 'New - Deposits Allowed']**. Deposits should be rejected for statuses like **[Specify Rejected Status(es), e.g., 'Closed', 'Frozen', 'Inactive', 'Dormant - No Deposits']**.
    -   Deposit Amount must be a positive numerical value (greater than zero).
    -   [Add any other crucial validation rules, e.g., Currency must match the account's designated currency, Cheque number must be valid format if applicable, Source account must have sufficient funds for internal transfers].
-   **Business Limits & Constraints:**
    -   Minimum deposit amount allowed per transaction: **[Specify Amount and Currency, e.g., $1.00 USD]**
    -   Maximum deposit amount allowed per transaction: **[Specify Amount and Currency, e.g., $10,000.00 USD via Mobile App]**
    -   Maximum cumulative deposit amount allowed per day for this account/customer: **[Specify Amount and Currency, e.g., $25,000.00 USD]**
    -   [Add any other relevant limits, e.g., limits based on customer KYC level, restrictions on specific deposit methods].

**Request:**
Generate a comprehensive set of functional test cases covering both **positive (successful deposit)** and **negative (failed deposit/error condition)** scenarios based *strictly* on the rules and limits provided above.

**Desired Output Format:**
Present the test cases clearly in a Markdown table using these columns:
-   **Test Case ID:** (Use a logical prefix, e.g., SD_DEP_[ChannelAbbreviation]_XXX)
-   **Type:** (Positive / Negative)
-   **Test Case Title:** (A brief, descriptive summary of the test objective)
-   **Preconditions:** (Necessary state before starting the test, e.g., Account status, existing balance, daily deposit total so far)
-   **Test Steps:** (Clear, numbered steps to execute the deposit attempt)
-   **Test Data:** (Specific values for inputs: Account Number, Amount, Currency, Method, etc.)
-   **Expected Result:** (The precise outcome anticipated: Successful deposit confirmation message, updated account balance, transaction record created, specific error message displayed, transaction rejected, no balance change)

**Specific Scenarios to Cover:**

**1. Positive Test Cases (Success Scenarios):** Ensure coverage for:
    -   Depositing a standard, valid amount well within all limits.
    -   Depositing exactly the minimum allowed amount per transaction.
    -   Depositing exactly the maximum allowed amount per transaction.
    -   Making a deposit that brings the cumulative daily total exactly to the daily limit.
    -   [Add any other specific success conditions relevant to your implementation, e.g., Deposit into a 'New - Deposits Allowed' status account].

**2. Negative Test Cases (Failure/Error Scenarios):** Ensure coverage for *each* rule and limit violation, including:
    -   Attempting deposit with an invalid or non-existent account number.
    -   Attempting deposit into an account with a status explicitly listed as rejected (e.g., 'Closed', 'Frozen').
    -   Attempting deposit into an account type other than 'Savings' (e.g., Loan Account, Credit Card).
    -   Attempting to deposit zero amount.
    -   Attempting to deposit a negative amount.
    -   Attempting to deposit an amount *below* the minimum transaction limit.
    -   Attempting to deposit an amount *above* the maximum transaction limit.
    -   Attempting a deposit that would *exceed* the maximum cumulative daily deposit limit (e.g., deposit $5,000 when $22,000 has already been deposited today against a $25,000 limit).
    -   [Add any other specific failure conditions from your rules, e.g., Mismatched currency, Invalid cheque details, Insufficient funds in source account for internal transfer].

Generate approximately **[Specify Number, e.g., 5-8]** distinct positive test cases and **[Specify Number, e.g., 8-12]** distinct negative test cases, ensuring each negative case targets a specific rule or limit violation.


#Example Usage (Filled Template for Online Banking Deposit via Transfer)(This demonstrates how you would fill the template)

Prompt:Generate functional test cases for the **Savings Account Deposit** feature accessed via **Online Banking Portal**.

**Feature Description:**
The feature enables a **Customer** to deposit funds into a designated savings account using an **Internal Transfer from a Linked Checking Account**.
-   **Key Inputs Required:** Target Savings Account Number (selected from user's accounts), Source Checking Account Number (selected from user's linked accounts), Deposit Amount, Currency (**INR** - fixed for this example).
-   **Core System Validation Rules:**
    -   Target Account Number must be a valid account number belonging to the customer.
    -   Target Account must be identified as a 'Savings' type account.
    -   Target Account status must be **'Active'**. Deposits should be rejected for statuses like **'Closed', 'Frozen', 'Dormant - No Deposits'**.
    -   Source Checking Account must be valid, linked, and have status 'Active'.
    -   Source Checking Account must have sufficient available balance (including any overdraft limits, if applicable - assume standard balance check for this prompt).
    -   Deposit Amount must be a positive numerical value (greater than zero).
-   **Business Limits & Constraints:**
    -   Minimum deposit amount allowed per transaction: **₹100.00 INR**
    -   Maximum deposit amount allowed per transaction: **₹200,000.00 INR**
    -   Maximum cumulative deposit amount allowed per day via Online Banking internal transfers: **₹500,000.00 INR**

**Request:**
Generate a comprehensive set of functional test cases covering both **positive (successful deposit)** and **negative (failed deposit/error condition)** scenarios based *strictly* on the rules and limits provided above.

**Desired Output Format:**
Present the test cases clearly in a Markdown table using these columns:
-   **Test Case ID:** (Use prefix SD_DEP_WEB_XXX)
-   **Type:** (Positive / Negative)
-   **Test Case Title:**
-   **Preconditions:**
-   **Test Steps:**
-   **Test Data:**
-   **Expected Result:**

**Specific Scenarios to Cover:**

**1. Positive Test Cases (Success Scenarios):** Ensure coverage for:
    -   Depositing ₹50,000 into an active savings account from an active checking with sufficient funds.
    -   Depositing exactly ₹100.00.
    -   Depositing exactly ₹200,000.00.
    -   Making a deposit of ₹100,000 when ₹400,000 has already been deposited today (reaching daily limit exactly).

**2. Negative Test Cases (Failure/Error Scenarios):** Ensure coverage for *each* rule and limit violation, including:
    -   Attempting deposit selecting a Target Account that is 'Frozen'.
    -   Attempting deposit selecting a Target Account that is not 'Savings' type (e.g., a Loan account listed).
    -   Attempting deposit when the Source Checking Account has insufficient funds (e.g., balance ₹500, attempt deposit ₹1000).
    -   Attempting to deposit ₹0.00.
    -   Attempting to deposit -₹100.00.
    -   Attempting to deposit ₹50.00 (below min limit).
    -   Attempting to deposit ₹200,001.00 (above max transaction limit).
    -   Attempting a deposit of ₹100,000 when ₹450,000 has already been deposited today (exceeding daily limit).

Generate approximately **6** distinct positive test cases and **8** distinct negative test cases, ensuring each negative case targets a specific rule or limit violation.
Usage Notes:Be Specific: The accuracy and usefulness of the AI's output directly depend on the precision of the rules, limits, and context you provide in the filled template.Review & Augment: Treat the AI-generated cases as a strong starting point. A human tester must review them for correctness, completeness, and logical flow. Add any nuanced scenarios or edge cases missed by the AI based on deep domain knowledge.One Feature Per Prompt: Keep the prompt focused on a single, well-defined feature or sub-feature for best results.Iterate: If the first set of generated cases isn't quite right, refine the details in your prompt (clarify rules, add more constraints
```
