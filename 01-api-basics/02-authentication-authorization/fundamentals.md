# Day 2 – API Authentication & Authorization Fundamentals

---

## 1. Authentication vs Authorization

### Simple Definitions
**Authentication**: User kaun hai? (identity check)  
**Authorization**: User kya kar sakta hai? (access permission check)  

### Professional Definition
Authentication verifies identity using credentials or tokens, while authorization determines access rights to resources based on roles, attributes, or ownership.

---

## 2. Real-World Example

### Authentication
User email + password verify hota hai → token generate hota hai.

### Authorization
User sirf apne data tak access kare, doosre user ka nahi.

**If authorization fails → IDOR risk**  
Example:  
GET /api/user/105 → ALLOWED
GET /api/user/106 → MUST BE DENIED


## 3. API Authentication Models

### 1️⃣ API Key
Simple static value → access mil jata hai  
**Risk:** Key leak = system compromise

### 2️⃣ JWT (JSON Web Token)
Self-contained identity + claims  
Format:
HEADER.PAYLOAD.SIGNATURE


Example payload:
{
"id": 245,
"role": "admin",
"exp": 1738479200
}

yaml
Copy code

Strengths: stateless, scalable  
Weaknesses: leak = identity theft

### 3️⃣ OAuth 2.0
Enterprise-grade login flow  
Used by Google, Facebook, Microsoft  

---

## 4. Authorization Models

### RBAC (Role-Based Access Control)
User → Role → Permissions

### ABAC (Attribute-Based Access Control)
User + resource + context = decision

### Object-Level Access Control
User own resources only  
IDOR failures hotspot

---

## 5. Where APIs Fail in Real World

| Failure Area | Impact |
|-------------|--------|
| No auth | Open exposure |
| Weak auth | Account takeover |
| Missing authZ | IDOR breach |
| Role bypass | Privilege escalation |
| JWT not validated | Token poisoning |
| No expiry | Session hijack |
| Key reuse | Full compromise |

---

## 6. Attacker Thinking (No hacking)

Attackers test:
- Authentication bypass
- Authorization gaps
- Role misconfigurations
- Object ID manipulation
- Token tampering
- Replay abuse
- Rate limit gaps

---

## 7. Self-Check Questions (Answered)

### Q1: Authentication vs Authorization difference?
Authentication identity validate karta hai. Authorization permission enforce karta hai.

### Q2: JWT kyon popular hai?
JWT stateless, scalable, fast aur identity + claims store karta hai.

### Q3: IDOR risk kab hota hai?
Jab object-level access control missing ho, aur user doosre user ka resource access kar sake.

### Q4: API key leak ka kya effect hai?
Key leak → attacker full API functionality access kar sakta hai → data breach.

---

## 8. Key Takeaways (Interview Value)

- AuthN + AuthZ difference is critical  
- Most API breaches = authorization failure  
- JWT validation mandatory  
- IDOR = silent high-impact vulnerability  
- OAuth = secure but complex  
- RBAC/ABAC define enterprise security boundaries  

---

# End of Day 2
