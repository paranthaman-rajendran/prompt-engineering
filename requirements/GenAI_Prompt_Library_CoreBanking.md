# 📚 GenAI Prompt Library — Core Banking Application

---

## 📖 How to Use:

- Replace bracketed placeholders `{{like this}}` with actual requirements.
- Mix and match prompt templates or tweak examples as needed.
- Use with ChatGPT, Genini AI, or other GenAI tools.

---

## 📌 1️⃣ Requirements Gathering & Analysis

**Prompt Template:**

> Generate user stories and acceptance criteria for a core banking application module to {{feature description}}. Ensure the stories cover {{key aspects like security, usability, or performance}}.

**Example:**

> Generate user stories and acceptance criteria for a core banking application module to manage customer KYC verification. Ensure the stories cover data validation, regulatory compliance, and error handling.

---

## 📌 2️⃣ Solution Design & Architecture

**Prompt Template:**

> Suggest a high-level architecture for a core banking application module to {{feature description}}. Include recommendations for {{microservices/monolith, database, message queues, API gateways, security components}}.

**Example:**

> Suggest a high-level architecture for a core banking application module to process loan disbursement requests. Include recommendations for microservices structure, database, MQ integration, and authentication setup.

---

## 📌 High-Level Architecture for Loan Disbursement Module

### Microservices Structure

- **Loan Disbursement Service**: Handles loan disbursement requests, calculates disbursement amounts, and updates loan statuses.
- **Customer Service**: Manages customer data and ensures customer eligibility.
- **Notification Service**: Sends notifications (e.g., SMS, email) to customers upon successful disbursement.
- **Audit Service**: Logs all disbursement transactions for compliance and auditing purposes.

### Database

- Use a **relational database** (e.g., PostgreSQL, MySQL) for structured data like customer details, loan records, and transaction history.
- Implement **database partitioning** to handle large volumes of loan data efficiently.
- Use **NoSQL databases** (e.g., MongoDB) for unstructured data like customer documents.

### Message Queue (MQ) Integration

- Use a message queue system like **RabbitMQ** or **Apache Kafka** for asynchronous communication between services.
- Example use cases:
  - Loan Disbursement Service publishes a message after processing a request.
  - Notification Service subscribes to the message queue to send notifications.
  - Audit Service subscribes to log transaction details.

### Authentication Setup

- Implement **OAuth 2.0** for secure authentication and authorization.
- Use **JWT (JSON Web Tokens)** for stateless authentication between services.
- Integrate with an **Identity Provider (IdP)** like Keycloak or Okta for centralized user management.

### Additional Recommendations

- Use an **API Gateway** (e.g., Kong, AWS API Gateway) to manage and secure API traffic.
- Implement **circuit breakers** (e.g., using Resilience4j) to handle service failures gracefully.
- Use **containerization** (e.g., Docker) and orchestration (e.g., Kubernetes) for scalability and fault tolerance.

---

## 📌 3️⃣ Application Development

### Backend

**Prompt Template:**

> Generate a {{language/framework}} REST API endpoint to {{functionality}}. The API should handle {{validations/error handling/security checks}}.

**Example:**

> Generate a Java Spring Boot REST API endpoint to fetch account balance details based on customer ID and account number. The API should handle input validations, error handling for invalid accounts, and secure token-based authentication.

### Frontend

**Prompt Template:**

> Create a {{framework/library}} UI component to {{display/collect data}} for {{feature/module}}. Include form validations and error states.

**Example:**

> Create a ReactJS UI component to display a transaction history table for a customer, including filters for date range and transaction type, and handle empty and error states.

---

## 📌 4️⃣ Testing

**Prompt Template:**

> Generate unit and integration test cases for a {{language/framework}} function that {{functionality}}. Include test scenarios for {{edge cases and error handling}}.

**Example:**

> Generate JUnit test cases for a Java method that calculates interest for a fixed deposit account based on deposit amount, tenure, and rate of interest. Include test cases for zero, negative, and high-value deposits.

---

## 📌 5️⃣ Deployment & CI/CD

**Prompt Template:**

> Create a {{CI/CD tool}} pipeline configuration to build, test, and deploy a {{application type}} to {{environment/platform}}. Include rollback and health check steps.

**Example:**

> Create a Jenkins pipeline configuration to build, test, and deploy a core banking microservice to a Kubernetes cluster. Include rollback and health check steps post-deployment.

---

## 📌 6️⃣ Maintenance & Monitoring

**Prompt Template:**

> Suggest a monitoring and alerting setup for a {{application type}} running on {{platform}}. Include metrics for {{response time, error rate, resource usage}}.

**Example:**

> Suggest a monitoring and alerting setup for a core banking transaction processing service running on Kubernetes. Include metrics for transaction success rate, latency, error codes, and memory/CPU usage.

---

## 📌 7️⃣ Documentation

**Prompt Template:**

> Generate API documentation in {{format like OpenAPI/Swagger}} for a {{language/framework}} REST endpoint to {{functionality}}.

**Example:**

> Generate OpenAPI documentation for a Java Spring Boot REST endpoint to retrieve mini statements for a savings account, including query parameters and response schema.

---

## 📒 Summary: SDLC Phase vs Prompt Template

| SDLC Phase             | Prompt Purpose                         | Template Available |
| :--------------------- | :------------------------------------- | :----------------- |
| Requirements           | User stories, acceptance criteria      | ✅                 |
| Design                 | Architecture suggestions               | ✅                 |
| Development (Backend)  | Backend APIs, validation logic         | ✅                 |
| Development (Frontend) | UI components, validation handling     | ✅                 |
| Testing                | Unit, integration, and edge case tests | ✅                 |
| Deployment             | CI/CD pipelines, deployment configs    | ✅                 |
| Monitoring             | Monitoring and alerting setup          | ✅                 |
| Documentation          | API and technical documentation        | ✅                 |
