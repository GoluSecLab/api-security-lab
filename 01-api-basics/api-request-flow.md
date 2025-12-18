# Day 1 – API Security Foundation

---

## 1. What is an API?

### Simple Definition
An API is a direct communication channel between a client (browser/mobile/tool) and backend services, used to send requests and receive responses.

### Professional Definition
An API (Application Programming Interface) is a communication interface that allows clients to interact directly with backend services, often bypassing UI validations, making it a critical security boundary in modern applications.

### Real-World Example
Banking apps use APIs like:
GET /api/account/balance

to fetch account details from backend systems.

---

## 2. API Request Flow (End-to-End)

Client (Browser / Mobile App / Postman)
↓
Network Layer / Internet
↓
API Gateway / Load Balancer
↓
Authentication Service
↓
Authorization Logic
↓
Business Logic / Microservices
↓
Database / External Services
↓
Response to Client


### Security Note
Each stage in the flow is a potential attack surface:
- Missing validation at business logic layer  
- Weak auth controls  
- Data exposure  
- Rate limiting bypass  
- Role abuse  

---

## 3. Trust Boundaries

### Definition
A trust boundary is a point in the system where the trust level changes.

### Key Trust Boundaries in APIs
1. **Internet → API Gateway**
   - Untrusted traffic entering the system  

2. **API Gateway → Authentication Service**
   - Identity validation  

3. **API → Database / Microservices**
   - Sensitive data and core logic exposed  

### Security Implication
Every trust boundary requires:
- Validation  
- Access control  
- Rate limiting  
- Sanitization  
- Logging  

---

## 4. Why APIs Are High-Risk

### Simple View
APIs expose backend logic directly, without UI controls.  
Attackers can automate requests and extract or manipulate data.

### Professional View
APIs expose business logic and sensitive data directly, making them vulnerable to:
1. Broken Authentication  
2. Broken Authorization  
3. Excessive Data Exposure  
4. Business Logic Abuse  
5. Rate Limiting Bypass  
6. Input Validation Failures  

### Example Risk
A missing auth check can allow:
- Account takeover  
- Data leakage  
- Privilege escalation  

---

## 5. Self-Check Questions (Answered)

### Q1: API bina UI ke risky kyun hai?
API UI validations bypass karta hai aur direct backend expose karta hai, jisse attackers automated malicious requests send kar sakte hain.

### Q2: Ek trust boundary example?
Internet se API Gateway ke beech ka boundary — yahan untrusted traffic enter karta hai.

### Q3: Authentication missing ho jaye to kya risk?
Unauthorized access, data leakage, compliance violations aur account compromise ka risk hota hai.

---

## 6. Day-1 Key Takeaways

- API = direct backend access  
- Har API layer = attack surface  
- Trust boundaries = security control points  
- Risk mindset = AppSec foundation  

---

# End of Day 1
