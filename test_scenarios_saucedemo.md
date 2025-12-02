# Test Scenarios – SauceDemo (Swag Labs)

Application under test: https://www.saucedemo.com/  
Scope: Basic login, product list, cart and checkout flow.

## TS_SD_001 – Successful login with valid user

**Goal:** Verify that a user with valid credentials can log in.  
**Preconditions:**  
- Valid user account exists (e.g. `standard_user`).

**High-level steps:**
1. Open SauceDemo login page.
2. Enter valid username.
3. Enter valid password.
4. Click "Login".

**Expected result:**
- User is redirected to the products page (inventory).
- No error messages are shown.

---

## TS_SD_002 – Login with invalid password

**Goal:** Verify that login is rejected with invalid password.  
**Preconditions:**  
- Valid username is known.

**High-level steps:**
1. Open login page.
2. Enter valid username.
3. Enter invalid password.
4. Click "Login".

**Expected result:**
- Login is rejected.
- Clear error message is displayed near the login panel.
- User stays on the login page.

---

## TS_SD_003 – Add single product to cart

**Goal:** Verify that a user can add one product to cart.  
**Preconditions:**
- User is logged in and on the products page.

**High-level steps:**
1. Click "Add to cart" for any product.
2. Check the cart icon in the header.
3. Open cart page.

**Expected result:**
- Cart icon shows "1" item.
- Cart page displays the selected product.

---

## TS_SD_004 – Remove product from cart

**Goal:** Verify that user can remove product from cart.  
**Preconditions:**
- At least one product is already in the cart.

**High-level steps:**
1. Open cart page.
2. Click "Remove" on the product.
3. Observe the cart content.

**Expected result:**
- Product disappears from the cart list.
- Cart icon is updated (0 or empty).

---

## TS_SD_005 – Checkout with valid data

**Goal:** Verify that user can successfully complete checkout with valid data.  
**Preconditions:**
- User is logged in.
- At least one product is in cart.

**High-level steps:**
1. Open cart page.
2. Click "Checkout".
3. Fill in all required fields (first name, last name, postal code).
4. Continue to order overview.
5. Click button to finish/complete the order.

**Expected result:**
- Order is completed successfully.
- User sees confirmation screen.

---

## TS_SD_006 – Checkout with missing required data

**Goal:** Verify validation when user leaves required fields empty.  
**Preconditions:**
- User is logged in.
- At least one product is in cart.

**High-level steps:**
1. Open cart page.
2. Click "Checkout".
3. Leave one or more required fields empty.
4. Click "Continue".

**Expected result:**
- Checkout is not continued to the next step.
- A clear validation error message is displayed for missing data.

---

## TS_SD_007 – Logout and access to protected page

**Goal:** Verify that logged-out user cannot access protected pages.  
**Preconditions:**
- User is logged in and on products page.

**High-level steps:**
1. Log out from the application.
2. Try to access products or cart page using direct URL / browser history.

**Expected result:**
- User is redirected to login page.
- Protected content is not visible.
