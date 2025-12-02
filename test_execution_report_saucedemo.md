# Test Execution Report – SauceDemo (Swag Labs)

## 1. General information

- Application: SauceDemo (Swag Labs) – demo e-commerce web app  
- URL: https://www.saucedemo.com/  
- Tester: Kamil Półkośnik
- Date: [2025-11-17]  
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
- Passed: **5**  
- Failed: **2**  

Overall result:  
Core business flows (login, cart, checkout) are working functionally as expected.  
However, two scenarios were marked as **failed** due to poor visual presentation of validation/error messages (layout issues visible on the screenshots).

---

## 4. Detailed results

| Scenario ID | Result | Comment                                                                                             | Screenshot                                      |
|-------------|--------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------|
| TS_SD_001   | PASS   | Login with valid user was successful.                                                               | `screenshots/01_login_success.png`             |
| TS_SD_002   | FAIL   | Invalid password is rejected (functional OK), but the red error banner overlaps UI and text is hard to read. | `screenshots/02_login_error.png`               |
| TS_SD_003   | PASS   | Product was added to the cart and counter = 1.                                                      | `screenshots/03_cart_with_product.png`         |
| TS_SD_004   | PASS   | Product was successfully removed from the cart.                                                     | `screenshots/04_cart_empty.png`                |
| TS_SD_005   | PASS   | Checkout completed successfully with valid data.                                                    | `screenshots/05_checkout_success.png`          |
| TS_SD_006   | PASS   | Missing required field is blocked with a clear validation error.                                    | `screenshots/06_checkout_validation_error.png` |
| TS_SD_007   | FAIL   | Access to protected page is correctly blocked, but the error banner is visually cramped/truncated and not very readable. | `screenshots/07_logout_protection.png`         |

> Note: Even though TS_SD_002 and TS_SD_007 behave correctly from a functional perspective,  
> they are treated as **failed** in this cycle due to UX/UI quality issues.

---

## 5. Observations

- The demo application is fast and responsive for the tested desktop flow.  
- Business logic for login, cart and checkout appears consistent and stable.  
- Error/validation banners on the login page:
  - overlap nearby UI elements,
  - have cramped text and are not fully readable on some resolutions,
  - break visual consistency of the otherwise clean login screen.

These UI issues do not block basic usage, but noticeably reduce readability and perceived quality.

---

## 6. Recommendations

- Improve the layout of error/validation banners on the login page:
  - add more spacing/margins so they do not overlap input fields,
  - ensure the full error text is visible without being cut off,
  - verify readability on common screen resolutions.
- Re-test visual presentation of error messages for:
  - invalid credentials (TS_SD_002),
  - unauthorized access to protected pages (TS_SD_007).
- In future test cycles, continue to:
  - extend negative test coverage (boundary values, special characters),
  - perform cross-browser and different viewport-size checks,
  - include dedicated UX / visual review alongside functional testing.

---
