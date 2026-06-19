# Requirements Traceability Matrix (RTM) - ShopMee v1.4

The Requirements Traceability Matrix (RTM) ensures that every business requirement is mapped directly to a functional spec, technical architecture component, corresponding test cases, and discovered defects. This guarantees 100% test coverage and full visibility.

---

## Traceability Mapping Matrix

| Business Req ID | Functional Spec ID | Technical Components | Test Case ID | Linked Bug ID | Verification Status |
| :--- | :--- | :--- | :--- | :---: | :--- |
| **BRD-REQ-001** | SRS-AUTH-01 | `AuthService.ts` / `RegisterController` | TC-REG-012, TC-REG-015 | [BUG-001](./Bugs/shopmee_bug_reports.md) | **Failed** - Blocked by SQL Injection |
| **BRD-REQ-002** | SRS-AUTH-04 | `SessionManager` / `CookieConfig` | TC-AUTH-044, TC-AUTH-045 | [BUG-002](./Bugs/shopmee_bug_reports.md) | **Failed** - Missing Security Flags |
| **BRD-REQ-003** | SRS-SEC-09 | `RateLimiterMiddleware` / `RedisStore` | TC-API-089, TC-API-090 | [BUG-003](./Bugs/shopmee_bug_reports.md) | **Failed** - Rate limit bypass |
| **BRD-REQ-004** | SRS-PROD-22 | `ProductDetailComponent` / `VariantService` | TC-UI-112, TC-UI-114 | [BUG-004](./Bugs/shopmee_bug_reports.md) |**Failed** - Price sync lag |
| **BRD-REQ-005** | SRS-CART-05 | `CartCalculationEngine` / `PricingContext` | TC-CART-031, TC-CART-032 | [BUG-005](./Bugs/shopmee_bug_reports.md) |**Failed** - Totals miscalculated |
| **BRD-REQ-006** | SRS-CART-11 | `InventoryEventListener` / `ActiveCartCheck` | TC-CART-056 | [BUG-006](./Bugs/shopmee_bug_reports.md) | **Failed** - Runtime NullPointer crash |
| **BRD-REQ-007** | SRS-CHKT-03 | `CheckoutSubmissionHandler` / `DebounceFilter` | TC-CHKT-081, TC-CHKT-082 | [BUG-007](./Bugs/shopmee_bug_reports.md) | **Failed** - Double-click anomaly |
| **BRD-REQ-008** | SRS-PAY-07 | `StripeGatewayService` / `WebhookReceiver` | TC-PAY-003, TC-PAY-004 | [BUG-019](./Bugs/shopmee_bug_reports.md) | **Failed** - Delayed gateway blackhole |

---

## Summary of Matrix Insights
* **Total Business Requirements Tracked:** 8
* **Test Case Coverage Rate:** 100% (All requirements have at least 1-2 assigned test cases)
* **Current Execution Status:** 0 Passed | 8 Failed (Blocked by corresponding unresolved defects logged in Jira Backlog)
