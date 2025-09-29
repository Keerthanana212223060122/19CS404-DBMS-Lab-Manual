# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:

![ER Diagram]
<img width="695" height="407" alt="dbms111" src="https://github.com/user-attachments/assets/a01b6ee6-1846-4ee4-bb57-e7d09f89e343" />




### Entities and Attributes

| Entity                | Attributes (PK, FK)                                                                   | Notes                                 |
| --------------------- | ------------------------------------------------------------------------------------- | ------------------------------------- |
| Book                  | BookID (PK), Title, Author, Category                                                  | Each book has a unique BookID         |
| Loan                  | LoanID (PK), LoanDate, ReturnDate, FineAmount, BookID (FK), MemberID (FK)             | Loan is linked to a Book and a Member |
| Member                | MemberID (PK), Name, Contact                                                          | Each library member has a unique ID   |
| EventRegistration     | RegistrationID (PK), EventID (FK), MemberID (FK)                                      | Connects members to events            |
| Event                 | EventID (PK), EventName, EventDate, RoomID (FK)                                       | Each event occurs in a room           |
| Speaker               | SpeakerID (PK), Name, Topic                                                           | Speakers present at events            |

### Relationships and Constraints

| Relationship                 | Cardinality | Participation                                 | Notes                                                                   |
| ---------------------------- | ----------- | --------------------------------------------- | ----------------------------------------------------------------------- |
| **Book–Loan**                | 1 : N       | Total on Loan, Partial on Book                | One book can be loaned many times                                       |
| **Member–Loan**              | 1 : N       | Total on Loan, Partial on Member              | One member can borrow many books                                        |
| **Member–EventRegistration** | 1 : N       | Total on EventRegistration, Partial on Member | A member can register for many events                                   |
| **Event–EventRegistration**  | 1 : N       | Total on EventRegistration, Partial on Event  | Each event can have many registrations                                  |
| **Event–Speaker**            | M : N       | Partial                                       | An event can have multiple speakers, a speaker can speak at many events |
| **Event–Room**               | N : 1       | Total on Event, Partial on Room               | Each event is held in exactly one room                                  |


### Assumptions
- One loan = one book + one member.

- One event = one room.

- Events ↔ Speakers are many-to-many.
 
---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
