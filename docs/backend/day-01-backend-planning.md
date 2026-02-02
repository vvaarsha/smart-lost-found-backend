\# Backend – Day 1 Planning \& Requirement Analysis



\## Project: Smart Lost \& Found System



\*\*Role:\*\* Member 2 – Backend \& Database Developer

\*\*Day:\*\* Day 1 (Requirement Analysis \& Planning)

\*\*Goal:\*\* Complete backend clarity before starting any code



---



\## 1. Purpose of Day 1



The purpose of Day 1 is to understand the system from a \*\*backend perspective\*\* and convert the problem statement into:



\* Clear backend responsibilities

\* Defined system actors

\* Permission rules

\* Backend modules

\* API-level thinking

\* Security and anti-fraud rules



No coding is done on Day 1. This day focuses entirely on planning.



---



\## 2. Problem Understanding (Backend View)



In a Smart Lost \& Found System:



\* Users lose items and report them

\* Other users find items and report them

\* The system must match lost and found items using AI

\* False claims must be prevented



The backend acts as:



\* The \*\*central controller\*\* of data

\* The \*\*security layer\*\*

\* The \*\*decision-making layer\*\* between frontend, AI, and database



---



\## 3. High-Level System Flow



```

User → Frontend → Backend → Database

&nbsp;                       ↓

&nbsp;                      AI Service

&nbsp;                       ↓

&nbsp;                    Backend → Frontend → User

```



The backend:



\* Receives all requests

\* Validates permissions

\* Stores and retrieves data

\* Communicates with AI

\* Sends safe responses to frontend



---



\## 4. System Actors



\### 4.1 Normal User (Owner)



\* Register and login

\* Report lost items

\* Receive match notifications

\* Submit claim for matched item



\### 4.2 Finder



\* Register and login

\* Report found items

\* Cannot see owner identity

\* Cannot claim items



\### 4.3 Admin



\* View all data

\* Approve or reject claims

\* Block fake or suspicious users

\* Override AI decisions if needed



\### 4.4 AI Service



\* Receives image or metadata

\* Returns similarity score

\* Cannot directly modify database



---



\## 5. Permission Matrix



| Action            | User | Finder | Admin |

| ----------------- | ---- | ------ | ----- |

| Register / Login  | Yes  | Yes    | Yes   |

| Report Lost Item  | Yes  | No     | Yes   |

| Report Found Item | Yes  | Yes    | Yes   |

| View Own Items    | Yes  | Yes    | Yes   |

| Claim Item        | Yes  | No     | No    |

| Approve Claim     | No   | No     | Yes   |

| Block User        | No   | No     | Yes   |



These rules will later be enforced using Spring Security.



---



\## 6. Backend Module Breakdown



\### 6.1 Authentication Module



\* User registration

\* Login

\* Password hashing

\* JWT token generation



\### 6.2 Item Management Module



\* Lost item reporting

\* Found item reporting

\* Item listing and filtering



\### 6.3 AI Matching Module



\* Send item data to AI service

\* Receive similarity score

\* Store match results



\### 6.4 Claim \& Verification Module



\* Accept ownership proof

\* Validate answers

\* Manage claim status



\### 6.5 Notification Module



\* Notify users on match

\* Notify users on claim status change



\### 6.6 Admin Module



\* Claim approval

\* User blocking

\* System monitoring



---



\## 7. API-Level Thinking (Text Only)



\### Authentication APIs



\* Register a new user

\* Login user and return token



\### Item APIs



\* Save lost item details

\* Save found item details

\* Get items reported by a user



\### AI APIs



\* Send lost and found item data for matching

\* Receive confidence score



\### Claim APIs



\* Submit ownership proof

\* Approve or reject claim



\### Notification APIs



\* Fetch notifications for a user



---



\## 8. Data Flow \& Anti-Fraud Logic



Anti-fraud measures planned at backend level:



\* Passwords are hashed

\* JWT required for all secured APIs

\* Claims are allowed only after AI match

\* Ownership verification questions are mandatory

\* Low AI confidence automatically rejects claim

\* Admin approval required for valuable items



Frontend cannot bypass these checks.



---



\## 9. Backend Rules \& Constraints



1\. Passwords must never be stored in plain text

2\. Users cannot access other users' private data

3\. Claims are never auto-approved

4\. AI confidence threshold is mandatory

5\. Admin has final authority



---



\## 10. Day 1 Deliverables



By the end of Day 1, the backend developer must have:



\* Actor and permission table

\* Backend module breakdown

\* Text-based API list

\* System flow understanding

\* Security and anti-fraud rules



This document serves as the foundation for all backend development.



---



\## 11. Viva Reference Statement



> "On Day 1, I analyzed system requirements, identified actors and permissions, planned backend modules and APIs, and defined security rules to prevent false claims before implementation."



---



\*\*Status:\*\* Day 1 Completed

\*\*Next Step:\*\* Day 2 – Environment Setup \& Project Initialization



