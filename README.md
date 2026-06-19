# ShopMee E-Commerce Platform - QA/Testing Portfolio

Welcome to my Quality Assurance (QA) portfolio repository for the **ShopMee E-Commerce Platform (v1.4)**. This project demonstrates a complete, industry-standard manual testing lifecycle—ranging from analyzing business requirements to designing extensive test cases, executing tests, tracking defects on a simulated Jira board, and reporting metrics.

---

## Quick Links to Project Artifacts
To facilitate a seamless review of my testing deliverables without requiring any external file downloads, please use the direct Markdown links below:

* **Business Requirements & Traceability:** [ShopMee E-Commerce Platform Project/Document/Shopmee_brd.md](ShopMee%20E-Commerce%20Platform%20Project/Document/Shopmee_brd.md)
* **Test Case Repository:** [ShopMe E-Commerce Platform Project/Testcase/shopmee_testcases.md](ShopMe%20E-Commerce%20Platform%20Project/Testcase/shopmee_testcases.md)
* **Defect Tracking & Logging:** [ShopMee E-Commerce Platform Project/Bugs/Shopmee_bug_reports.md](ShopMee%20E-Commerce%20Platform%20Project/Bugs/Shopmee_bug_reports.md)

---

##  Testing Scope & Test Bed
* **Target Build:** ShopMee Web Application v1.4 (Staging Environment)
* **Core Modules Tested:** User Registration & Login, Product Search & Detail, Shopping Cart & Checkout, and Third-Party Payment Gateways (Stripe API simulation).
* **Testing Types Applied:** Functional Testing, UI/UX Testing, Boundary Value Analysis, Equivalence Partitioning, Security Testing (OWASP Top 10 focus), and API Testing.
* **Toolstack utilized:** GitHub, MS Excel, Postman (API inspection), Jira Software (Sprint backlog management simulation).

---

##  Quality Metrics & Execution Summary
During this sprint, **120 handcrafted test cases** were designed and executed, revealing a total of **25 unique defects**.

### 1. Test Case Pass Rate
* **Total Executed:** 120 Test Cases
* **Passed:** 104 Cases (86.67%)
* **Failed:** 11 Cases (9.17%)
* **Blocked:** 5 Cases (4.16%)
* *Note: The overall pass rate of 86.67% failed to meet the 95% threshold defined in the Project Exit Criteria.*

### 2. Defect Severity Breakdown
*  **Critical (4 Bugs):** Major security flaws, including an SQL Injection vulnerability on the Registration Email field and misconfigured API response codes.
*  **High (8 Bugs):** Severe functional breakdowns in Cart recalculations, duplicate order submissions on double-clicking, and web freezes during gateway response delays.
*  **Medium (6 Bugs):** Gaps in API rate-limiting thresholds and product search overlays.
*  **Low (7 Bugs):** Minor responsive layout displacements and typography formatting errors.

---

## 🚨 Final Quality Assessment & Sign-Off Conclusion
### Status: 🔴 NOT READY FOR PRODUCTION
**Rationale:** Although standard features demonstrate baseline stability, the build critically violates the signed-off Exit Criteria due to **4 unresolved Critical vulnerabilities** and **8 open High-severity errors**. These flaws present severe risks to transaction safety and data integrity. 

**Recommendation:** The QA team has blocked the production deployment. Development engineers must prioritize patching data-layer injections and implementing click-debouncing on checkouts for the upcoming **Hotfix v1.4.1** build.
