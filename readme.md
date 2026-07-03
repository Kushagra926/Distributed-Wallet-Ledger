# Distributed Wallet & Ledger System

A production-grade digital wallet backend built with Spring Boot, implementing double-entry bookkeeping to guarantee financial consistency across all transactions — inspired by how
real-world fintech platforms (Razorpay, Cred, Paytm) handle money movement safely at scale.

---

## Overview

This system solves a core fintech engineering problem: **how do you move money between accounts
without ever losing consistency, even under failures, retries, or concurrent requests?**

It implements:
- **Double-entry bookkeeping** — every transaction creates a balanced debit + credit entry
- **Idempotent APIs** — safe to retry without double-charging
- **Automated reconciliation** — nightly batch job to catch and flag discrepancies
- **Resilient external integrations** — circuit breaker + retry for simulated payment gateway calls

---

*(Diagram will be updated with the final service breakdown as implementation progresses)*

---

## Tech Stack

| Category | Technology |
|---|---|
| Language | Java 17 |
| Framework | Spring Boot, Spring Data JPA |
| Database | PostgreSQL |
| Messaging | Apache Kafka |
| Caching | Redis |
| Migrations | Flyway |
| Resilience | Resilience4j (Circuit Breaker, Retry) |
| Testing | JUnit 5, Mockito, Testcontainers |
| Containerization | Docker, Docker Compose |

---

## Key Features

- [ ] Double-entry ledger with atomic debit/credit entries
- [ ] Idempotency key-based transaction API to prevent duplicate charges
- [ ] Wallet top-up, transfer, and withdrawal endpoints
- [ ] Kafka event publishing on transaction state changes (`Initiated`, `Completed`, `Failed`)
- [ ] Spring Batch nightly reconciliation job (ledger vs wallet balance)
- [ ] Circuit breaker + retry for external payment gateway simulation
- [ ] Integration tests with Testcontainers (real PostgreSQL + Kafka)

---

