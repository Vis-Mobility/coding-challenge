# Flutter Coding Challenge: My Coupons App

## Objective

You will build a simple **"My Offers"** mobile app in Flutter based on the provided UI design.

The app will:
- Display a list of available coupons for the user.
- Show detailed coupon information when a coupon is tapped.
- Allow the user to generate and display a **QR code or barcode** for redemption.
- Connect to a provided backend server to fetch entitlement data.

You will be given a **Swagger/OpenAPI** specification and server for easier API integration.

---

## Business Story

- **Admin** creates and issues entitlements (meal coupons, event tickets, etc.).
- **User** opens their app and sees their available entitlements.
- **Admin** redeems a user's entitlement by scanning a QR code displayed in the user app.

---

## User Flow

1. **Home Screen**:
   - Display all available coupons.
   - Each coupon shows:
     - Logo image
     - Title (e.g., "Starbucks Buy 1 Get 1 Free")
     - Offer details (e.g., "25% Off", "Buy 1 Get 1 Free")
     - Expiry date
   - (Optional) Filtering tabs: All / Food / Shop / Travel / Other.

2. **Coupon Detail Screen**:
   - Show full coupon details:
     - Description
     - Terms & Conditions
     - Validity period
   - Display a **QR code** or **barcode** encoding redemption information.

### Sample Screen Design:
![Sample Screen Design](./sample-screen.png)

---

## Requirements

- Use **Flutter 3.x** or newer.
- Implement two main screens:
  - **Coupon List** (Home Screen)
  - **Coupon Detail** (Coupon Info + QR/Barcode)
- Integrate API to fetch user entitlements dynamically, using the provided Swagger/OpenAPI documentation.
- Generate and show QR code or barcode using a Flutter package.
- Responsive design, close to the provided UI mockup.

---

## Connecting to development server
URL: To be provided
Swagger/OpenAPI: https://{url}/#api

---

## Bonus Features (If Time Allows)

- Implement **filtering** (All / Food / Shop / Travel / Other) functionality.
- Implement **pull-to-refresh** for refreshing the coupon list.
- Add a **loading spinner** when fetching data.
- Implement **error handling** for API failures (e.g., "No Internet", "Server Error").
- Use a proper **state management** library (e.g., `provider`, `riverpod`, `bloc`, `cubit`, etc.).
- Improve the user experience by:
  - Showing expired coupons visually distinct (e.g., grayed out).
  - Showing countdown to expiry (e.g., "3 days left").

---

## Other Requirements

- Code must be **clean, organized, and modular**.
- Suggested folder structure:
  - `/models`
  - `/services` (for API calls)
  - `/screens`
  - `/widgets`
- Use **Dart best practices**.
- Proper separation of concerns between UI, logic, and network layers.
- Include a simple **README** with brief instructions on how to run the project.

---

## Evaluation Criteria

- UI completeness based on the given design.
- Proper API integration using the Swagger/OpenAPI documentation.
- Code readability, maintainability, and architecture.
- Handling loading, empty, and error states gracefully.
- Creativity and thoughtfulness around bonus features.
- Overall polish and user experience.

---

## Notes

- Focus on building a working solution; pixel-perfect design is a bonus but not mandatory.
- You may use public Flutter libraries such as:
  - `qr_flutter` for QR code generation
  - `http` or `dio` for API calls
  - `intl` for date formatting
- You can hardcode `user_id` for testing purposes.
