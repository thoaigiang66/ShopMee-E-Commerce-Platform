# Jira Backlog & Defect Tickets - ShopMee v1.4

This document represents the active project backlog and defect tracking lifecycle modeled inside Jira Software for the **ShopMee v1.4 sprint**. It showcases the relationship between user stories and identified bugs.

---

## Scrum Backlog & Bug Tickets Matrix

| Issue Key | Issue Type | Summary | Component/Module | Priority | Status | Description Summary (Jira Syntax) |
| :--- | :---: | :--- | :--- | :---: | :---: | :--- |
| **SM-101** | `Story` | Implement User Registration input validation | User Registration | High | `Done` | As a platform administrator, I want registration text inputs sanitized so that malicious structural database payloads are blocked before execution. |
| **SM-412** | `Bug` | CRITICAL: SQL Injection exposure in Registration Email field | User Registration | Highest | `To Do` | **Bug Description:** Inputting raw structural database text constructs triggers unhandled execution sequences.<br>**Steps to Reproduce:** 1. Open `/register` 2. Fill Email field with SQL payload 3. Click Register.<br>**Actual Result:** Full query engine log data prints straight to the UI display. |
| **SM-102** | `Story` | Configure secure cookie attributes for User JWT sessions | Login | High | `Done` | As a user, I want my active session token hidden from cross-site scripts so that my account credentials cannot be extracted via client-side code. |
| **SM-413** | `Bug` | HIGH: Session cookie missing mandatory HttpOnly/Secure flags | Login | High | `To Do` | **Bug Description:** The backend authorization cookie token exposes read parameters to the document DOM tree.<br>**Expected Result:** Token attributes must restrict context access strictly to raw server-bound wire protocols. |
| **SM-103** | `Story` | Enforce API Rate-Limiting thresholds on public endpoints | Forgot Password | Medium | `Done` | As a security engineer, I need volume limits established across unauthenticated public entry API forms to prevent brute-force attacks. |
| **SM-414** | `Bug` | MEDIUM: Rate-limiting bypass via multi-threaded header flooding | Forgot Password | Medium | `To Do` | **Bug Description:** Flooding public API controllers with parallel request pipelines bypasses standard memory-stored rate threshold increments. |
| **SM-104** | `Story` | Dynamic price grid recalculation for product variants | Product Detail | High | `Done` | As a customer, I want the displayed price updated dynamically when I toggle options like storage size or color. |
| **SM-415** | `Bug` | HIGH: Variant selection changes fail to update display price grid | Product Detail | High | `To Do` | **Bug Description:** Toggling product variations modifies the selection state values, but the text elements rendering price points fail to sync up. |
| **SM-105** | `Story` | Implement real-time state listeners for shopping cart totals | Shopping Cart | High | `Done` | As a user, I want my cart invoice total automatically recalculated when item counts change. |
| **SM-416** | `Bug` | HIGH: Quantity adjustments inside cart fail to trigger subtotal updates | Shopping Cart | High | `To Do` | **Bug Description:** Mutating active item volume states via increment inputs pushes changes to local cache but fails to invoke the recalculation engine. |
| **SM-106** | `Story` | Graceful out-of-stock validation during active cart checkouts | Shopping Cart | High | `Done` | As a system operator, I want active customer checkouts guarded against mid-session zero-stock anomalies so that execution failures are intercepted gracefully. |
| **SM-417** | `Bug` | HIGH: Active cart viewing triggers 500 NullPointer when stock falls to 0 | Shopping Cart | High | `To Do` | **Bug Description:** If a product stock reaches zero while a different session holds it inside an unsubmitted view, reloading causes an immediate server crash. |
| **SM-107** | `Story` | Engineer single-submission boundaries for payment events | Checkout | High | `Done` | As a user, I want rapid clicks on order buttons filtered out so that my linked credit card accounts do not encounter duplicate accidental charges. |
| **SM-418** | `Bug` | HIGH: Double-tap order execution generates duplicate database records | Checkout | High | `To Do` | **Bug Description:** Rapidly double-clicking the checkout submit action processes distinct simultaneous transaction tokens down the wire, leading to duplicate account charges. |
| **SM-108** | `Story` | Establish error-catching frameworks for third-party endpoints | Payment | High | `Done` | As a customer, I expect network connectivity issues or third-party processor drops handled cleanly so that my cart selection remains populated for retries. |
| **SM-419** | `Bug` | HIGH: Payment gateway response delays freeze web interface states | Payment | High | `To Do` | **Bug Description:** Simulating 30s delays across external endpoints results in unhandled blank screen states and flushes the user's active session local cache records. |
