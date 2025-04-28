# Mini Project: Entitlement Service

## Business Context

You are building a small **Entitlement Service** to manage rewards like meal coupons or event tickets for users.

The system should support the following user flow:

- **Admin** creates an **Entitlement Type** (e.g., "Lunch Coupon", "Event Entry Pass").
- **Admin** issues an **Entitlement Instance** to specific users.
- **User** can check and view their entitlements in the user app.
- **Admin** redeems an entitlement by **scanning a QR code** from the user's app via the redemption app.

The redemption must be:
- **Time-constrained** (valid during a window).
- **Location-constrained** (valid only at/near a specific place).
- **Duplicate redemption must be prevented**.

You will **design** the API specification and the database schema based on this flow before implementing it.

---

## Requirements

### Functional Requirements
- Create and manage **Entitlement Types** (templates like "Meal Coupon", "Concert Ticket").
- Issue **Entitlement Instances** to users based on Entitlement Types.
- Users must be able to view their available entitlements.
- Admins must be able to **redeem** entitlements by scanning a QR code shown in the user app.

### Redemption Rules
- Redemption must happen:
  - **Within valid time window** start and end timestamps, time of day, day of week, etc.
  - **Within a specified location radius** (geofencing).
  - You may want to make the redemption rule very flexible i.e. using expression language or jsonLogic or rule engine
- Once redeemed, an entitlement **cannot be redeemed again**.

### Design Deliverables
- **API Specification**:
  - Define REST endpoints (method, path, request/response body, status codes).
- **Database Schema**:
  - Define tables or data models to support Entitlement Types, Entitlement Instances, Users, and Redemptions.

---

## Implementation Details

- Use either:
  - **TypeScript** (Node.js/Express, NestJS, or similar)
  - **Python** (FastAPI, Flask, or similar)
- Persistence:
  - In-memory structures are acceptable, but a simple SQLite database or JSON file storage is a bonus.
- Geolocation:
  - Implement a simple distance check (e.g., haversine formula).

---

## Bonus (If time allows)
- Implement **JWT Authentication** for admin and user APIs.
- Use **SQLite** instead of in-memory for storing entitlements and redemptions.
- **Rate limit** redemption attempts (e.g., 5 redemption tries per minute per user).
- Mark entitlement as **redeemed** after successful redemption, it will be even better to have a state machine to manage the states.
- Add **unit tests** for critical logic (e.g., location check, time check, duplicate check).

---

## Evaluation Criteria
- Completeness and correctness of your **API** and **database** design.
- Code quality: structure, readability, and maintainability.
- Handling of edge cases.
- Extensibility of design to support future entitlement types.
- Bonus points for additional features, test coverage, or thoughtful architecture.

---

## Notes
- Focus on functionality first — no need to over-engineer.
- Assume simple mobile apps (user app and redemption app) interact with your service.
- You may use libraries to help with geolocation or time calculations.
