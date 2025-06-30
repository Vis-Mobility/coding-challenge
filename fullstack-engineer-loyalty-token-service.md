# Mini Project: Loyalty Point/Token Service

## Business Context

You are building a small **Loyalty Point/Token Service** to manage reward points or tokens for users across multiple loyalty programs.

The system should support the following user flow:

- **Admin** creates a **Loyalty Program** (e.g., "Wine & Dine", "Frequent Flyer").
- **User** can join one or more loyalty programs.
- **Backend server** calls the **Earn API** asynchronously after a transaction, supplying transaction details to credit points/tokens to the user.
- **User** can view their points/tokens balance for each program.
- **User** can **redeem (burn)** points/tokens for rewards via the **Burn API**.

The system must support:
- Multiple programs per user.
- Flexible earn/burn rules per program (e.g., $100 = 5 tokens in "Wine & Dine", $100 = 1 point in "Frequent Flyer").
- Prevention of duplicate or invalid redemptions.

You will **design** the API specification and the database schema based on this flow before implementing it.

---

## Requirements

### Functional Requirements
- Create and manage **Loyalty Programs** (e.g., "Wine & Dine", "Frequent Flyer").
- Users can join one or more programs.
- Backend can **credit (earn)** points/tokens to users via an async API after a transaction.
- Users can view their points/tokens balance per program.
- Users can **redeem (burn)** points/tokens for rewards.
- Prevent duplicate or invalid redemptions.

### Earn/Burn Rules
- Each program defines its own earn and burn rules (e.g., earn rate, redemption options).
- Earn API must be idempotent (prevent duplicate credits for the same transaction).
- Burn API must check for sufficient balance and mark points/tokens as redeemed.

### Design Deliverables
- **API Specification**:
  - Define REST endpoints (method, path, request/response body, status codes).
- **Database Schema**:
  - Define tables or data models to support Users, Loyalty Programs, User Program Memberships, Earned Points/Tokens, and Redemptions.

---

## Implementation Details

- Use either:
  - **TypeScript** (Node.js/Express, NestJS, or similar)
  - **Python** (FastAPI, Flask, or similar)
- Persistence:
  - In-memory structures are acceptable, but a simple SQLite database or JSON file storage is a bonus.
- Earn API:
  - Designed to be called asynchronously by backend after a transaction.
  - Must accept transaction details and program info.
- Burn API:
  - Allows users to redeem points/tokens for rewards.

---

## Bonus (If time allows)
- Implement **JWT Authentication** for admin and user APIs.
- Use **SQLite** instead of in-memory for storing points/tokens and redemptions.
- **Rate limit** earn or burn attempts (e.g., 5 earn/burn tries per minute per user).
- Mark points/tokens as **redeemed** after successful burn, consider a state machine for point/token states.
- Add **unit tests** for critical logic (e.g., earn/burn rules, idempotency, duplicate check).

---

## Evaluation Criteria
- Completeness and correctness of your **API** and **database** design.
- Code quality: structure, readability, and maintainability.
- Handling of edge cases.
- Extensibility of design to support future loyalty programs.
- Bonus points for additional features, test coverage, or thoughtful architecture.

---

## Notes
- Focus on functionality first — no need to over-engineer.
- Assume simple mobile apps or backend services interact with your service.
- You may use libraries to help with calculations or idempotency.
