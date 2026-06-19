# Master Test Plan - ShopMee E-Commerce Platform

**Project:** ShopMee E-Commerce Platform  
**Version:** v1.4  
**Date:** May 10, 2026  
**Author:** QA Lead / Quality Assurance Department  

---

## 1. Introduction
ShopMee is a next-generation multi-channel e-commerce platform that supports smart product search, cart management, online checkout, and user profile configuration. 

This document outlines the testing strategy, resource allocation, and quality criteria for the release version **v1.4** to ensure optimal stability, data security, and seamless user experience prior to production deployment.

---

## 2. Scope of Testing

### Testing Types & Matrix
| Test Type | Methodology & Approach | Tools |
| :--- | :--- | :--- |
| **Functional Testing** | Black-box testing covering all core business paths (Positive, Negative, Boundary) via Web Browser UI. | Manual Testing |
| **Security Testing** | Vulnerability assessments targeting SQL Injection, CrossSite Scripting (XSS), and cookie token storage. | OWASP ZAP, Burp Suite |
| **API Testing** | End-to-End backend endpoint inspection, checking response status codes (200, 400, 429, 500) and rate-limiting blocks. | Postman |

### 2.1 In-Scope
* **User Registration & Login:** Verification of registration flows, JWT authentication, user role privileges, and security cookie session parameters.
* **Product Search & Detail:** Validation of full-text searching, advanced query filtering, and dynamic content binding for item variants (color, storage).
* **Shopping Cart & Checkout:** Testing item add/remove events, quantity manipulation, discount coupon logic, and invoice breakdown calculations.
* **Payment Gateways:** Validation of asynchronous transaction webhooks integrated with the 3rd-party Stripe API gateway.

### 🔴 2.2 Out-of-Scope
* Business Intelligence (BI) data warehouse reporting inside the Admin Dashboard.
* Load testing exceeding 100,000 concurrent user sessions (allocated to a later phase).

---

## 3. Testing Strategy
The testing workflow follows a hybrid approach combining rigorous structured Manual Testing for business layouts and exploratory UI, along with focused Security and API test beds. 

All identified defects must be logged directly with clear steps to reproduce and mapped against the active [Business Requirements Document (BRD)](./shopmee_brd.md).

---

## 4. Criteria

### 📥 4.1 Entry Criteria
1. Software Requirement Specification (SRS) documentation is formally baselined and signed off.
2. Staging environment deployment (v1.4) is completed and smoke test passes.
3. Source code unit test coverage satisfies a minimum threshold of **> 80%**.

###  4.2 Exit Criteria
1. **100%** of planned critical business path test cases are fully executed.
2. **Zero** open defects categorized as `Critical` or `High` severity.
3. The aggregate test case passing rate is equal to or greater than **95%**.

---

## 5. Resources & Environment
The testing phase is executed by **3 full-time QA Engineers** collaborating with the Project Manager to log, track, and retest issues using Jira Software dashboards.

Môi trường kiểm thử hoạt động chính thức trên nhánh: `Staging-v1.4`.
