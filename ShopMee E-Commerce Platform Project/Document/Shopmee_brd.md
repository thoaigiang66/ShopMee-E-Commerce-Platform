ShopMee E-Commerce Platform - Business Requirements Document (BRD)

This document outlines the core business and functional requirements for **ShopMee v1.4**. As part of the QA engineering workflow, these requirements serve as the foundation for test case design and validation criteria.


Business Requirements Matrix

| Req ID | Requirement Name | Category | Description | Business Value / Priority |
| :--- | :--- | :---: | :--- | :--- |
| **BRD-REQ-001** | Secure User Onboarding | Functional | Allow new users to sign up via valid email verification. Ensure rigorous input sanitization to guard database layers against malicious query injections. | **Critical** - Core acquisition funnel and data security. |
| **BRD-REQ-002** | Session Management Protection | Security | Establish user authentication using encrypted JWT tokens. Enforce strict server-side HTTP cookie configurations (HttpOnly & Secure flags) to mitigate client-side exploitation. | **High** - Prevents session hijacking and account takeovers. |
| **BRD-REQ-003** | Brute-Force & Flood Prevention | Security | Implement automated rate-limiting gateways across public entry API forms (e.g., Forgot Password, OTP requests) to block credential stuffing and resource starvation. | **High** - Ensures resource availability and limits platform spam. |
| **BRD-REQ-004** | Dynamic Variant Synchronization | Functional | Display dynamic pricing grids on the product layout page. The platform must dynamically render updated pricing matrices based on user variant inputs (e.g., storage capacity shifts). | **High** - Directly impacts checkout revenue transparency. |
| **BRD-REQ-005** | Real-Time Cart Recalculation | Functional | Ensure the shopping cart service listens to line-item changes. Modifying item counts must instantly trigger recalculations of subtotal, applied tax pools, and voucher rules. | **High** - UX consistency and checkout accuracy. |
| **BRD-REQ-006** | Graceful Out-of-Stock Handling | Functional | Gracefully manage instances where selected items drop to 0 units in active carts. Prevent layout breaks and present intuitive alternative paths instead of system exceptions. | **High** - Retains consumer trust and prevents interface crashes. |
| **BRD-REQ-007** | Idempotent Transaction Submission | Functional | Protect the core checkout endpoint against rapid multiple-click actions. Temporarily disable checkout controls post-submission to stop duplicate order creations. | **Critical** - Mitigates duplicate multi-charging database anomalies. |
| **BRD-REQ-008** | Resilient Gateway Timeout Management | Functional | Establish error-catching thresholds for external checkout processing loops (Stripe API). Gracefully handle communication latencies without wiping data states. | **High** - Prevents order states from dropping into data voids. |

---

## QA Traceability Matrix 
*Để chứng minh hiệu quả của quá trình kiểm thử, dưới đây là cách các lỗi (Defects) được phát hiện dựa trên tài liệu yêu cầu ban đầu:*

* 🎯 **BRD-REQ-001** ➔ Bị vi phạm bởi [🐛 BUG-001: SQL Injection in Registration](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-002** ➔ Bị vi phạm bởi [🐛 BUG-002: Session cookie missing flags](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-003** ➔ Bị vi phạm bởi [🐛 BUG-003: No rate-limiting on Forgot Password](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-004** ➔ Bị vi phạm bởi [🐛 BUG-004: Product variant price not updating](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-005** ➔ Bị vi phạm bởi [🐛 BUG-005: Cart price not recalculating](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-006** ➔ Bị vi phạm bởi [🐛 BUG-006: Cart crashes when stock is 0](./Bugs/shopmee_bug_reports.md)
* 🎯 **BRD-REQ-007** ➔ Bị vi phạm bởi [🐛 BUG-007: Duplicate orders via multi-clicks](./Bugs/shopmee_bug_reports.md)
