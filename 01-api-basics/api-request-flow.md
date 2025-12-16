Day 1 – API Security Foundation
1️⃣ API Definition
Simple Definition

API ek direct communication channel hai jo client (browser, mobile app, tool) ko backend services se baat karne deta hai.

Professional Definition

An API (Application Programming Interface) is a communication interface that allows clients to interact directly with backend services, often bypassing UI-level validations, making it a critical security boundary in modern applications.

Example

A banking mobile app uses an API like:

GET /api/account/balance


to fetch user balance directly from backend services.

2️⃣ API Request Flow (End-to-End)

Client (Browser / Mobile App / Postman)
        ↓
Internet / Network Layer
        ↓
API Gateway / Load Balancer
        ↓
Authentication Service (Token Validation)
        ↓
Authorization Logic (Access Control)
        ↓
Business Logic / Microservices
        ↓
Database / External Services
        ↓
Response sent back to Client

Security Insight

Har arrow ek attack surface hai

Agar kisi layer pe validation miss ho jaye → security risk create hota hai

3️⃣ Trust Boundaries

Definition

Trust Boundary wo point hota hai jahan system ka trust level change hota hai.

Key Trust Boundaries in APIs

Internet → API Gateway

Risk: Untrusted users sending malicious requests

API → Authentication Service

Risk: Token bypass / weak validation

API → Database / Microservices

Risk: Unauthorized data access, injection, logic abuse

Security Principle

Har trust boundary pe authentication, authorization, validation, logging aur rate-limiting hona chahiye.

4️⃣ Why APIs are High-Risk

Simple Explanation

APIs ka koi UI nahi hota

Direct backend access hota hai

Attackers automation se easily abuse kar sakte hain

Professional Explanation

APIs expose business logic and sensitive data directly, making them vulnerable to:

Broken Authentication

Broken Authorization (IDOR)

Excessive Data Exposure

Business Logic Abuse

Rate Limiting Bypass

Example Risk

Agar token validation weak ho → attacker doosre user ka data access kar sakta hai.

5️⃣ Self-Check Questions (Answered)

Q1. API bina UI ke risky kyun hai?

API UI validations bypass karta hai aur direct backend logic expose karta hai, jisse attackers easily malicious requests send kar sakte hain.

Q2. Ek trust boundary ka example do

Internet se API Gateway ke beech ka boundary — kyunki yahan untrusted traffic system me enter karta hai.

Q3. Agar authentication miss ho jaye to kya risk hai?

Unauthorized access, data leakage, account takeover aur compliance violations ka risk hota hai.
