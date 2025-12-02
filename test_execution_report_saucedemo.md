# Test Execution Report – SauceDemo (Swag Labs)

## 1. General information

- Application: SauceDemo (Swag Labs) – demo e-commerce web app  
- URL: https://www.saucedemo.com/  
- Tester: [Your Name]  
- Date: [2025-12-02]  
- Environment: Public demo environment (desktop browser, e.g. Chrome)

---

## 2. Scope

This test cycle covers basic happy-path and a few negative scenarios for:

- Login
- Adding/removing products from the cart
- Checkout with valid and invalid data
- Logout and access to protected pages

Covered scenarios (referenced from `test_scenarios_saucedemo.md`):

- TS_SD_001 – Successful login with valid user  
- TS_SD_002 – Login with invalid password  
- TS_SD_003 – Add single product to cart  
- TS_SD_004 – Remove product from cart  
- TS_SD_005 – Checkout with valid data  
- TS_SD_006 – Checkout with missing required data  
- TS_SD_007 – Logout and access to protected page  

---

## 3. Summary

- Total test scenarios executed: **7**  
- Passed: **7**  
- Failed: **0**  
- Overall result:  
  Basic flows are working as expected on the tested browser and environment.  
  No critical or major issues were found during this test cycle.

---

## 4. Detailed results

| Scenario ID | Result | Comment                                              | Screenshot                                      |
|-------------|--------|------------------------------------------------------|-------------------------------------------------|
| TS_SD_001   | PASS   | Login with valid user was successful.                | `screenshots/01_login_success.png`             |
| TS_SD_002   | PASS   | Invalid password was rejected with a clear error.    | `screenshots/02_login_error.png`               |
| TS_SD_003   | PASS   | Product was added to the cart and counter = 1.       | `screenshots/03_cart_with_product.png`         |
| TS_SD_004   | PASS   | Product was successfully removed from the cart.      | `screenshots/04_cart_empty.png`                |
| TS_SD_005   | PASS   | Checkout completed successfully with valid data.     | `screenshots/05_checkout_success.png`          |
| TS_SD_006   | PASS   | Missing required field blocked with validation error.| `screenshots/06_checkout_validation_error.png` |
| TS_SD_007   | PASS   | After logout, protected page was not accessible.     | `screenshots/07_logout_protection.png`         |

> Note: Screenshot filenames can be adjusted to match the actual files you save.

---

## 5. Observations

- The demo application is fast and responsive for the tested desktop flow.  
- Error messages for invalid login and missing checkout data are short, visible and easy to understand.  
- The UI is simple and helps to follow the main purchase flow without confusion.  

No obvious UI defects or blocking issues were observed during this short test cycle.

---

## 6. Recommendations

- Extend test coverage with more negative scenarios (special characters, very long input values, boundary values).  
- Add cross-browser testing (e.g. Firefox, Edge, Safari) and different viewport sizes in future test cycles.  
- Consider adding exploratory testing sessions focused on:  
  - sorting/filtering products,  
  - price calculations and tax display,  
  - behavior under unstable network conditions.

---
